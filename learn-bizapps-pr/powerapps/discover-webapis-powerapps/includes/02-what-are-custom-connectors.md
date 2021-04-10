There are hundreds of prebuilt connectors available to connect Power Apps to Microsoft and non-Microsoft services. However, you may want to communicate with a service that is not available as a prebuilt connector, for example the VanArsdel inventory management web API. [Custom connectors][az cuscon] bridge this gap by allowing you to create a connector with its own actions, including invoking a web API hosted in Azure API Management from a Power Apps application.

![Custom Connector Overview][image-01]


## Web APIs behind Azure API Management ##

Kiana and her team built the web APIs for the inventory management system and iterated on them over time. The system is complex and consists of many different APIs. Kiana's team decided to use [Azure API Management][az apim] to control and administer the web APIs from a central place.

Kiana's team often uses Azure API Management's ability to expose specific web APIs publicly, but not others, by setting various policies. To learn more about Azure API Management, check out this Learn module, [Integrate Open API-enabled Web API with Azure API Management through Visual Studio][az learn apim].


## Creating a custom connector ##

You can create a custom connector by exporting it from Azure API Management. This allows the Power Apps app developer to use the custom connector, and thus the web API, without having to know the web API's address or how it works.

![Creating Custom Connector from API Management][image-02]

Once the custom connector is generated, you can see it on the Power Apps page. You will learn how to export an API like shown below, in the following unit.

![Custom Connector on Power Apps][image-03]


## Connector vs. connection ##

A custom connector is a wrapper around a web API, it allows Power Apps to communicate with the web API. However, the custom connector itself does nothing unless you create a connection for it.

* The **connector** knows the web API's host and operation details.
* The **connection** knows the credentials and has a reference to the **connector** facilitate to communication with the web API.

![Connector vs Connection][image-04]


[image-01]: ../media/02-what-are-custom-connectors-01.png
[image-02]: ../media/02-what-are-custom-connectors-02.png
[image-03]: ../media/02-what-are-custom-connectors-03.png
[image-04]: ../media/02-what-are-custom-connectors-04.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts
[az cuscon]: https://docs.microsoft.com/connectors/custom-connectors/
[az learn apim]: https://docs.microsoft.com/learn/modules/integrate-openapi-enabled-web-api-with-apim-and-visual-studio/
