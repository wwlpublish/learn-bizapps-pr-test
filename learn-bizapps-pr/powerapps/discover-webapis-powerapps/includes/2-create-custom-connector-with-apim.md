:::row:::
  :::column span="4":::
    Crystal is a full-stack developer and software architect specializing in C# and .NET. She has written and designed many of Green Leaf's applications but is getting stretched thin by all the new requests. Crystal is familiar with Power Apps at a high-level and is eager to learn how she can use her existing skills to empower Citizen Developers.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Crystal][meet crystal]
  :::column-end:::
:::row-end:::


Crystal and her development team have built Web APIs for inventory management, which is served through [Azure API Management][az apim]. She wants to create a custom connector by exporting it to Power Apps so that Maria can directly use it on her Power Apps without needing to know about API Management.


> QUESTION: Do we provide a pre-built APIM instance here so that learners can visually walk through the process? To avoid dependency on the previous module, what could be the best way to provide context about APIM here?

## Export Custom Connector from API Management ##

Here are the inventory management API details hosted by API Management.

In order to access API Management from Power Apps, you should have a subscription key. Go to the `Subscriptions` blade, click the three dots (`...`) and select the `Show/hide keys` menu.

![Subscription Blade][image-01]

Then, copy the subscription key from either `Primary key` or `Secondary key`.

![Copy Subscription Key][image-02]

To generate a custom connector from Azure API Management, go to the `APIs` blade and select **Green Leaf Inventory Management** under the `All APIs` section. Then, you will be able to see the list of APIs.

![Inventory Management APIs on API Management][image-03]

Click the three dots (`...`), and you will see the context menu. Select the `Export ⬇️` menu.

![API Export Menu on API Management][image-04]

Click the `Power Apps and Power Automate` panel at the right bottom corner.

![API Export Screen on API Management][image-05]

Choose your Power Apps environment for the custom connector to publish and give the display name, **InventoryManager**. Then click the `Export` button at the bottom.

![Export API to Power Apps][image-06]

The inventory management APIs have been exported to Power Apps.


## Create Connection to Custom Connector ##

Although you created the custom connector, in order to use it, you should create a connection to the custom connector. Generally speaking, creating the connection requires authentication to the APIs.

> ** What's the difference between connector and connection?**
> 
> A connector defines contracts&ndash;what APIs look like and how you can connect to APIs. It doesn't actually connect you to the APIs. On the other hand, a connection knows the connection details how you connect to the APIs, including authentication details. Power Apps use the connection to communicate with APIs through the connector.

After logging into [Power Apps][pa] dashboard, open the `Data` blade and click the `Custom Connectors` menu on the left-hand side. Then, click the `➕` button on the right-hand side.

![New Custom Connector][image-07]

> **NOTE**:
> 
> The following part is based on the current bug of the custom connector created from API Management. We should update this part once this bug is fixed.


### ⬇️⬇️⬇️ Bug Workaround Part Begin ⬇️⬇️⬇️ ###

When a pop-up modal shows up, you will only see two buttons&ndash;`Cancel` and `Create`. Close the modal by clicking the `Cancel` button.

![New Custom Connector Pop-up Modal Bug Workaround][image-08]

This time, click the `🖋` button on the right-hand side to update the connector.

![Update Custom Connector][image-09]

Click the `2. Security` tab, and you will see all fields are greyed out, which are unmodifiable.

![Custom Connector Security Tab Fields Unmodifiable][image-10]

Click either the `🖋 Edit` button, and you will see all the fields become modifiable. Then click the `Definition →` button at the right bottom corner.

![Custom Connector Security Tab Fields Modifiable][image-11]

At the `Definition` tab, leave everything unchanged and click the `✅ Update connector` button on the right-hand side. Once the custom connector is updated, you will see the message, `✅ Custom connector has been successfully updated` at the top of the screen.

![Custom Connector Definition Tab][image-12]

Go back to the `Custom Connectors` menu and click the `➕` button on the right-hand side again.

![New Custom Connector Bug Workaround][image-07]

### ⬆️⬆️⬆️ Bug Workaround Part End ⬆️⬆️⬆️ ###

When a pop-up modal shows up, you will see the API Key field. Enter the API key copied at the beginning of this unit. Then click the `Create` button.

![New Custom Connector Pop-up Modal][image-13]

Go to the `Connections` menu, and you will see the new connection has been created.

![New Connection][image-14]

You have completed creating a custom connector for inventory management.


## Key Takeaways ##

After this unit, you are now able to:

* Create a custom connector from Azure API Management by exporting the APIs,
* Know the differences between a connector and a connection, and
* Create a connection of the custom connector by providing authentication details.


[meet crystal]: ../media/meet-crystal.png

[image-01]: ../media/2-create-custom-connector-with-apim-01.png
[image-02]: ../media/2-create-custom-connector-with-apim-02.png
[image-03]: ../media/2-create-custom-connector-with-apim-03.png
[image-04]: ../media/2-create-custom-connector-with-apim-04.png
[image-05]: ../media/2-create-custom-connector-with-apim-05.png
[image-06]: ../media/2-create-custom-connector-with-apim-06.png
[image-07]: ../media/2-create-custom-connector-with-apim-07.png
[image-08]: ../media/2-create-custom-connector-with-apim-08.png
[image-09]: ../media/2-create-custom-connector-with-apim-09.png
[image-10]: ../media/2-create-custom-connector-with-apim-10.png
[image-11]: ../media/2-create-custom-connector-with-apim-11.png
[image-12]: ../media/2-create-custom-connector-with-apim-12.png
[image-13]: ../media/2-create-custom-connector-with-apim-13.png
[image-14]: ../media/2-create-custom-connector-with-apim-14.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts

[pa]: https://powerapps.microsoft.com/
