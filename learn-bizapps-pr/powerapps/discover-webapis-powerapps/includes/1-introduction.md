Connectors are the core of Power Apps that connect as many resources as they can. Power Apps provides you with hundreds of connectors to access resources inside and outside your organization. However, not all connectors can cover your organization's business scenarios. If your organization has business-specific APIs, you should consider custom connectors that bridge between Power Apps and the APIs.

Green Leaf Heating and Air Conditioning, or Green Leaf for short, is a full-service heating and air conditioning contractor. The core of Green Leaf's business involves sending field technicians to customers' houses to install and repair all brands of heating and air conditioning equipment.

Green Leaf's business has grown exponentially over the past year. Along with that growth has come friction in scaling core business applications.

:::row:::
  :::column span="4":::
    Maria works in inventory management and makes sure Green Leaf runs like a well-oiled machine. She verifies the warehouse has enough parts and, if not, orders more using a legacy system that Crystal wrote. But more than that – she performs audits on the inventory, checks with vendors for the best prices, and other inventory supply management tasks.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Maria][meet maria]
  :::column-end:::
:::row-end:::

Maria has been studying up on Power Apps in her spare time. She believes that Power Apps excels at enabling business professionals to develop applications, which are easy to create and deploy. She wants to build a Power App with existing Web APIs through a custom connector.

:::row:::
  :::column span="4":::
    Crystal is a full-stack developer and software architect specializing in C# and .NET. She has written and designed many of Green Leaf's applications but is getting stretched thin by all the new requests. Crystal is familiar with Power Apps at a high level and is eager to learn how she can use her existing skills to empower Citizen Developers.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Crystal][meet crystal]
  :::column-end:::
:::row-end:::


Crystal and her development team have built Web APIs for inventory management, which is served through [Azure API Management][az apim]. She expects that Maria will be able to build a Power App through a custom connector with Azure API Management.


## What Is a Custom Connector? ##

While Power Apps offer hundreds of connectors to connect to Microsoft and non-Microsoft services, you may want to communicate with services that are not available as prebuilt connectors like Inventory Management. [Custom connectors][az cuscon] address this scenario by allowing you to create a connector with its own actions.

![Custom Connector Overview][image-01]


## Learning Objectives ##

After completing this module, you will be able to:

* Build a custom connector that handles requests to Web APIs and responses from them.


## Prerequisites ##

* Familiarity with the concept of Web API (or HTTP API). Custom connectors use Web APIs to send and receive data.


[meet crystal]: ../media/meet-crystal.png
[meet maria]: ../media/meet-maria.png

[image-01]: ../media/1-introduction-01.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts
[az cuscon]: https://docs.microsoft.com/connectors/custom-connectors/
