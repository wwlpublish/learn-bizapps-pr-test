The **Premium HTTP** connection is built-in Power Apps and Power Automate and is provided by Microsoft.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Premium H T T P connector.](../media/http-connector-icon.png)](../media/http-connector-icon.png#lightbox)

The HTTP connector provides the users the option to connect to a service or a data source that a direct connector is not available for. The connection can be made as a **GET, PUT, POST, PATCH, and DELETE** method. It uses a **Uniform Resource Identifier (URI)** to connect.

> [!div class="mx-imgBorder"]
> [![Screenshot of the connection with method list.](../media/method.png)](../media/method.png#lightbox)

Basic, Client Certificate, Active Directory OAuth and Raw are the authentication options provided as shown in the image below.

> [!div class="mx-imgBorder"]
> [![Screenshot of the authentication options available.](../media/http-autentication.png)](../media/http-autentication.png#lightbox)

An example of using an HTTP connector is making a connection to **Microsoft Graph** to gather user information. As the below screenshots show, you use the **GET** method, URI to grap.microsoft.com and the **Active Directory OAuth** authentication to get the desired information in a secure manner.

> [!div class="mx-imgBorder"]
> [![Screenshot example of the H T T P connector making a connection to Microsoft Graph.](../media/graph-http.png)](../media/graph-http.png#lightbox)

There is also **HTTP + Swagger.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the H T T P + Swagger Endpoint U R L.](../media/http-swagger.png)](../media/http-swagger.png#lightbox)

Swagger allows you to describe the structure of your API so that you can get the desired data and receive it in a format that can be manipulated easily.
