Connectors are the core of Power Apps that connect as many resources as they can. Power Apps provides you with hundreds of connectors to access resources inside and outside your organisation. However, not all connectors can cover your organisation's business scenarios. If your organisation has APIs that are business-specific, you should consider custom connectors that bridge between Power Apps and the APIs.

Green Leaf Heating and Air Conditioning, or Green Leaf for short, is a full service heating and air conditioning contractor. The core of Green Leaf's business involves sending field technicians to customers’ houses to install and repair all brands of heating and air conditioning equipment.

Green Leaf's business has grown exponentially over the past year. Along with that growth has come friction in scaling core business applications.

:::row:::
  :::column span="4":::
    Maria works in inventory management and makes sure Green Leaf runs like a well-oiled machine. She verifies the warehouse has enough parts and if not orders more using a legacy system that Crystal wrote. But more than that – she performs audits on the inventory, checks with vendors for the best prices, and other inventory supply management tasks.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Maria](../../shared/media/maria.png)
  :::column-end:::
:::row-end:::

Maria has been studying up on Power Apps in her spare time. She believes that Power Apps excels at enabling business professionals develop applications that are easy to create and deploy. She wants to build a Power App with existing Web APIs through a custom connector.


## What Is a Custom Connector? ##

While Power Apps offer hundreds of connectors to connect to Microsoft and non-Microsoft services, you may want to communicate with services that are not available as prebuilt connectors like Inventory Management. [Custom connectors][az cuscon] address this scenario by allowing you to create a connector with its own actions.

![Custom Connector Overview][image-01]


## Learning Objectives ##

After completing this module, you will be able to:

* Build a custom connector that handles requests to Web APIs and responses from them.


## Prerequisites ##

* Familiarity with the concept of Web API (or HTTP API). Custom connectors use Web APIs to send and receive data.


[image-01]: https://picsum.photos/seed/1-introduction-01.png/300/300

[az cuscon]: https://docs.microsoft.com/connectors/custom-connectors/
