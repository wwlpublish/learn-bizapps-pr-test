There are hundreds of prebuilt connectors available to connect Power Apps to Microsoft and non-Microsoft services. However, you may want to communicate with services that are not available as prebuilt connectors, like the VanArsdel's Inventory Management web API. [Custom connectors][az cuscon] address this by allowing you to create a connector with its own actions, including invoking a web API hosted in Azure API Management.

![Custom Connector Overview][image-01]


## Web APIs behind Azure API Management ##

Crystal and her team built the web APIs for the inventory management system. As the inventory management system consists of many different web APIs, they need to be controlled within a central place, called [Azure API Management][az apim].

Suppose she only wants to expose the web API for warehouse locations. In this case, Azure API Management is a perfect choice to open only that API, by setting various policies. To learn more about Azure API Management, check out this learn module, [Integrate Open API-enabled Web API with Azure API Management through Visual Studio][az learn apim].


## Creating a Custom Connector ##

You are to create a custom connector from Azure API Management so that a Power Apps app developer can directly use it without having to know where the web APIs are, or care about how they work. Azure API Management offers a feature that generates a custom connector by exporting it.

![Creating Custom Connector from API Management][image-02]

Once the custom connector is generated, you can see it on the Power Apps page. You will learn how to export an API like below, in the following unit.

![Custom Connector on Power Apps][image-03]


## Connector vs Connection ##

As custom connector is a wrapper around a web API, it allows Power Apps to communicate with the web API. However, the custom connector itself does nothing unless you create a connection for it.

* The **connector** knows the web API's host and operation details.
* The **connection** knows the credentials and the **connector**'s reference to communicate with the web API.

![Connector vs Connection][image-04]


[image-01]: ../media/02-what-are-custom-connectors-01.png
[image-02]: ../media/02-what-are-custom-connectors-02.png
[image-03]: ../media/02-what-are-custom-connectors-03.png
[image-04]: ../media/02-what-are-custom-connectors-04.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts
[az cuscon]: https://docs.microsoft.com/connectors/custom-connectors/
[az learn apim]: https://docs.microsoft.com/learn/modules/integrate-openapi-enabled-web-api-with-apim-and-visual-studio/
