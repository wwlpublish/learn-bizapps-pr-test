The premium **HTTP with Azure AD** connector is used to fetch resources from various Web services, authenticated by **Azure Active Directory (Azure AD),** or from an on-premise web service.

> [!div class="mx-imgBorder"]
> [![Screenshot of the H T T P with Azure Active Directory connector.](../media/http-azure.png)](../media/http-azure.png#lightbox)

The connector does not have any triggers and hence it needs another connector like **Microsoft Forms** connector, **SharePoint** connector or manually trigger the flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Triggers view with no triggers message.](../media/triggers.png)](../media/triggers.png#lightbox)

The following are the only two actions currently available.

> [!div class="mx-imgBorder"]
> [![Screenshot of the currently available actions.](../media/azure-actions.png)](../media/azure-actions.png#lightbox)

The **Get web resource** is used to retrieve web resources by issuing an HTTP GET request.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Get web resource field.](../media/get-web-resoure.png)](../media/get-web-resoure.png#lightbox)

The Invoke an HTTP request is used to access data from an endpoint using one of the known HTTP verbs like **GET, DELETE, PATCH, POST & PUT.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Invoke a H T T P request fields.](../media/invoke-http.png)](../media/invoke-http.png#lightbox)

Current known issues and limitations are:

-   The connector encodes the request body into base64 encoding, hence it should be used to call backend services that expect the request body in this format. You cannot use this connector to call a backend service that expects the request body in raw binary format.

-   If you get an error similar to **{ "error": { "code": "Forbidden", "message": "" } }**, it could be because this connector has a limited set of scopes. If your scenario requires something more advanced, please use the HTTP connector or create a custom connector.

The throttling limit for the **API** calls per connection is **100 calls** for every **60 seconds**.

An example is invoking an HTTP request to **Microsoft Graph** to get user information.

> [!div class="mx-imgBorder"]
> [![Screenshot example of an H T T P request to Microsoft Graph.](../media/invoke-http-request.png)](../media/invoke-http-request.png#lightbox)
