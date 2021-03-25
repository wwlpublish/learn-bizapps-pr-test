When you configure an action on a custom connector, you can also configure parameters. These are configured either by importing an OpenAPI definition or a sample request. Regardless of the approach used, the list of parameters is fixed and when that action is used the maker will be presented with the static list of the parameters as defined by the connector. For many scenarios, this is appropriate because the list parameters are fixed and don't vary. In some cases, the parameters that should be presented for input are variable. The following are the most common use cases:

-   List of parameters varies based on a type such as a category or a type of invoice.

-   The state of the record could determine which parameters can be changed. for example, a shipped order could have different parameters available than a non-shipped order.

-   The parameter list could be trimmed by security.

-   A common action implementation across a few different data types. For example, API may implement Create action that applies to accounts, contacts, orders, invoices. Input parameters will be defined by the object type the maker selects.

Custom connectors support these scenarios by allowing you to configure dynamic schema OpenAPI extensions. When configured, the custom connector runtime will call an operation to retrieve the schema that defines which parameters should be visible for that given action. The schema data can include other options such as the display name and description for the parameter.

In our Contoso Invoicing API example, after importing the OpenAPI definition, our action looked like the following when used in a Power Automate flow:

> [!div class="mx-imgBorder"]
> [![Screenshot showing the action without any extensions configured.](../media/action-example.png)](../media/action-example.png#lightbox)

The above image shows parameters that aren'tt relevant for adding a purchase order invoice versus a non-purchase order invoice. Also, not all of the invoice fields are valid input for the invoice creation. For example, createDate is a field set by the API and shouldn't be part of the user input. After implementing dynamic values for the invoice type ID and dynamic schema for the other parameters here's what the action looks like:

> [!div class="mx-imgBorder"]
> [![Screenshot of the custom connector action with purchase order field visible.](../media/dynamic-values-implemented-example.png)](../media/dynamic-values-implemented-example.png#lightbox)

As the maker changes the invoice type from purchase order to non-purchase,  order the purchase order parameter is hidden or shown as appropriate.

The custom connector runtime supports two different extensions that can be used to configure dynamic schema. They both accomplish the same end goal with one being version one and the other being version 2. The x-ms-dynamic-schema extension is version 1 and x-ms-dynamic-properties is version 2. If you need to support older flows using your action, you can configure both versions on your custom connector. If you only support new flows, you can configure the x-ms-dynamic-properties extension only.

## API support

For you to configure dynamic schema, the underlying API must provide support by defining the operation that returns the schema. If API doesn't already have a suitable action, and you don't have the ability to modify the API or request the changes, you might not be able to implement dynamic schema.

The operation that returns the schema can take one or more parameters that are passed from the custom connector runtime. These parameters can be constants or can represent other data collected on the action card. That can be used by the API to filter the list of parameters that are returned as part of the schema. In our example above, Invoice type is passed as a parameter to the operation to get the dynamic schema.

The response from the operation used for dynamic schema must be a valid JSON (JavaScript Object Notation) schema. The following is an example of what Contoso API GetInvoiceSchema returns:

> [!div class="mx-imgBorder"]
> [![Screenshot showing the output from the API get dynamic schema operation.](../media/return-example.png)](../media/return-example.png#lightbox)

Notice the following key points about the content:

-   Type must be provided and is used to identify the parameter data type.

-   Summary and description are used in the Power Automate designer to identify the parameters to the maker.

-   The x-ms-visibility extension property can be provided to indicate where you believe this parameter should always be shown (value "important") or if a user action is required to reveal it to the maker for example, click on Advanced link on a flow card (value "advanced"). Since this is retrieved dynamically, it can vary depending on the context information available

-   The required array provides the list of any required parameters.

## Configuring the dynamic schema extension

To configure the x-ms-dynamic-schema or the x-ms-dynamic-properties extensions you must directly edit the custom connector's OpenAPI definition. Currently there's no custom connector designer support for editing these values.

In our example, the following is how AddInvoice parameter configuration looked after importing the OpenAPI definition provided by the API:

> [!div class="mx-imgBorder"]
> [![Screenshot of the swagger editor before editing.](../media/add-invoice-parameter.png)](../media/add-invoice-parameter.png#lightbox)

In the above example, it shows that add invoice takes a CreateInvoiceRequest object as input. The properties are defined by a referenced #/definitions/Invoice, which is a shared definition of all the invoice properties.

To implement the call to the dynamic schema extension, we're going to replace the properties with our configured extension.

> [!div class="mx-imgBorder"]
> [![Screenshot of the swagger editor after editing.](../media/configured-extension.png)](../media/configured-extension.png#lightbox)

Now instead of having a hard-coded list of properties the GetInvoiceSchema operation will be called to get the list based on the parameter typeId.

By implementing dynamic schema on your custom connector, you can make it clear to the maker which parameters need to be used for the action.