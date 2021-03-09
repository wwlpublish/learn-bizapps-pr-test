A polling trigger is an implementation that regularly calls your REST API service and checks for new data. Once the platform determines that new data is available, the trigger fires and passes the new data collected to a cloud flow or a Logic Apps workflow.

The following diagram provides a basic process flow of how a polling trigger acquires new data.

> [!div class="mx-imgBorder"]
> [![Diagram of the basic process flow for a polling trigger.](../media/polling-trigger-flow.png)](../media/polling-trigger-flow.png#lightbox)

A polling trigger starts by retrieving the data and setting a state. It then periodically checks for updates by requesting all the data since the last state update. Once new data is retrieved, the new state is set, and the process continues. The API needs to be able to return the data incrementally, based on a parameter value. Power Automate or Azure Logic Apps maintain the state, so the API don't have any special state management requirements.

Unlike a webhook trigger, there's no setup or tear down requirements, and the processing can be stopped at any time. The simplicity of the requirements is one of the main advantages of the polling trigger.

## API requirements

A polling trigger only requires an API to have a data retrieval method that can filter the data using a query string parameter. There must also be a way to extract the next value of the parameter from the returned data. The implementation can be provided either by a dedicated or an existing action method.

For example, consider an online store implementation where orders have ever increasing order numbers. The store API may include a method *ListOrders* that returns orders created in the store.

1.  *ListOrders* returns the orders sorted by order number in descending order. That way the highest order number belongs to the first order in the list.

1.  *ListOrders* accepts a query string parameter to retrieve the orders where the order number is greater than the parameter value.

These two qualities allow the action to be used as a polling trigger. The platform can extract the highest order number from the returned data and pass it as a parameter into the next request. Effectively, the method will "select all orders created since the last one".

## Implementation

Polling trigger is created using a wizard in Power Automate. The process includes the following steps:

1.  Define HTTP request that will be used to retrieve the data.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the HTTP request definition form.](../media/request-details.png)](../media/request-details.png#lightbox)

    The query string of the request includes the **fromWidget** parameter. That enables pre-generation of the parameter definition. This parameter ensures that the data returned is incremental, that is "return all widgets created since the one specified by the parameter".

1.  Change parameter visibility to Internal. That prevents the user from making any changes to this parameter used only internally by the connector.

1.  Define the data returned by the service. This data should include the property to be used as the value for **fromWidget** in the consecutive requests. 

	> [!div class="mx-imgBorder"]
	> [![Screenshot showing the import from a sample.](../media/data-value.png)](../media/data-value.png#lightbox)

    In this example, the property is called **ID**.

1.  Complete Trigger configuration: select the query parameter, define a value or expression returning a value, and collection that contains the trigger data.

	> [!div class="mx-imgBorder"]
	> [![Screenshot of the complete trigger configuration details.](../media/trigger-confirmation-complete.png)](../media/trigger-confirmation-complete.png#lightbox)

    In this example:

    -   **fromWidget** is selected as the query parameter that will receive the value extracted from the lab results.

    -   Expression **@{triggerBody().widgets[0].id}** extracts the current highest widget ID. Since the returned collection is sorted in the descending ID value, extracting the value from the first element guarantees that it's the highest current ID.

    -   @triggerBody().widgets define the data collection.

Parameters need to be extracted and processed, and this transformation can only be implemented using a connector policy. That's why the polling trigger configuration is stored as a policy template separate from the OpenAPI connector definition. One of the implications is that it's not possible to manually edit all of the polling trigger configuration in the Swagger editor.

One of the limitations you need to be aware of is that the trigger body itself can't be an array. For example, consider a method *ListOrders* that returns the following data:

```json
[
  {"value" : 42.00, "id" : "2", ... },
  {"value" : 10.00, "id" : "1", ... }
]
```

This trigger body won't be processed, and the trigger will generate an error in the Power Automate flow or Logic Apps workflow at run time.

Instead, the method needs to return a property that contains the array of the records, for example:

```json
{
  "orders": [
    { "value" : 42.00, "id" : "2", ... },
    { "value" : 10.00, "id" : "1", ... }
  ]
}  
```

This data structure can be used as part of the polling trigger implementation.

## Batch processing

Like the webhook trigger, the polling trigger is defined by **x-ms-trigger** extension to OpenAPI. The value defined by a polling trigger is a **batch** indicating that the method will return an array rather than an individual object as in a webhook response.

```yaml
  /trigger/ListInvoices:
    post:
      x-ms-trigger: batch
```
This happens because it's possible to have multiple records returned from a single call to the service. When a polling trigger is used in Power Automate or Logic Apps, the trigger **Split On** setting allows you to configure the processing mode.

> [!div class="mx-imgBorder"]
> [![Screenshot of the settings dialog for poll options.](../media/settings-invoice-created.png)](../media/settings-invoice-created.png#lightbox)

Splitting of the incoming array into the multiple parallel executions is done for performance reasons. Each instance of the cloud flow in this scenario will receive a since object. If the Split On option isn't set, a single instance of the cloud flow will receive an array of values.

Polling triggers are easier to define than the webhook triggers, however they're less granular and often less performant. The decision to build and use one type of the triggers or another is driven by service API's features, structure, and functionality.

The following video shows the polling trigger.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyYqC/]