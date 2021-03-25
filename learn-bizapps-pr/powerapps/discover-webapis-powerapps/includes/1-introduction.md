While devloping a Power App, you may find out you need to call a web API created by a high-code development team in your organization. Power Apps have already provided you with hundreds of *connectors* to access resources inside and outside your organization. However, there is no built-in connector for you to call web APIs that your organization has developed. This situation brings about you have to create a custom connector to fill the gap between Power Apps and web APIs.

You've met the team at Green Leaf Heating and Air Conditioning, or Green Leaf for short, and learned a bit about the issues they currently have with their Field Inventory Management System.

Crystal is a professional developer, and Maria is an inventory management specialist who has been learning Power Apps. They are working together as a Fusion Development team to create a Power App that helps manage inventory. Their first task is to display a list of their warehouse locations. The warehouse locations will be fetched from a web API and displayed in a Power App.


## What Is a Custom Connector? ##

While Power Apps offer hundreds of connectors to connect to Microsoft and non-Microsoft services, you may want to communicate with services that are not available as prebuilt connectors like Inventory Management. [Custom connectors][az cuscon] address this scenario by allowing you to create a connector with its own actions.

![Custom Connector Overview][image-01]


## Learning Objectives ##

After completing this module, you will be able to:

* Build a custom connector that handles requests to web APIs and responses from them.


## Prerequisites ##

* Familiarity with the concept of web API (or HTTP API). Custom connectors use web APIs to send and receive data.


[meet crystal]: ../media/meet-crystal.png
[meet maria]: ../media/meet-maria.png

[image-01]: ../media/1-introduction-01.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts
[az cuscon]: https://docs.microsoft.com/connectors/custom-connectors/
