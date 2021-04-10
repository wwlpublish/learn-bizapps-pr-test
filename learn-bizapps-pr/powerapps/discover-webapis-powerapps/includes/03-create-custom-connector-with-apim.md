In this exercise you're going to create a custom connector by exporting an API from Azure API Management.

In the VanArsdel fusion development scenario, Maria needs to display warehouse locations in her Power Apps application. Kiana and her development team have built several web APIs one of which returns the warehouse locations.

The web APIs are served through [Azure API Management][az apim], which has the ability to create custom connectors for any web APIs it hosts. With the custom connector, Maria's Power Apps app will be able to call the warehouse location API in Azure API Management.

> [!NOTE]
> If you want to use Azure API Management and Power Apps throughout the exercises in this module you will need to follow a couple of steps.
> 
> The first is to download the web API files from GitHub and provision and deploy them to API Management using the instructions included in the README file.
> 
> The second is Power Apps requires either a Microsoft 365 license or a free trial. Learn more about your licensing options. [Microsoft products include Microsoft Power Apps and Power Automate][pa pricing].


## Export a web API from API Management to a custom connector ##

1. You need a subscription key in order for Power Apps to access any web API hosted in API Management. Go to the `Subscriptions` blade, click the three dots (`...`) and select the `Show/hide keys` menu.

    ![Subscription Blade][image-01]

1. Then, copy the subscription key from either `Primary key` or `Secondary key`.

    ![Copy Subscription Key][image-02]

1. To generate a custom connector from Azure API Management, go to the `APIs` blade and select an appropriate API under the `All APIs` section. In the screenshot, it's **Inventory Management**. Then, you will be able to see the API for the warehouse locations.

    ![Inventory Management APIs on API Management][image-03]

1. Click the three dots (`...`), and you will see the context menu. Select the `Export ⬇️` menu.

    ![API Export Menu on API Management][image-04]

1. Click the `Power Apps and Power Automate` panel at the right bottom corner.

    ![API Export Screen on API Management][image-05]

1. Choose your Power Apps environment for the custom connector to publish and give the display name, **InventoryManager**. Then click the `Export` button at the bottom.

    ![Export API to Power Apps][image-06]

The inventory management APIs have been exported to Power Apps.


## Create a connection to the custom connector ##

You need to create a connection to the custom connector in order to use it. Generally speaking, creating the connection requires authentication to the web APIs.

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


[image-01]: ../media/03-create-custom-connector-with-apim-01.png
[image-02]: ../media/03-create-custom-connector-with-apim-02.png
[image-03]: ../media/03-create-custom-connector-with-apim-03.png
[image-04]: ../media/03-create-custom-connector-with-apim-04.png
[image-05]: ../media/03-create-custom-connector-with-apim-05.png
[image-06]: ../media/03-create-custom-connector-with-apim-06.png
[image-07]: ../media/03-create-custom-connector-with-apim-07.png
[image-08]: ../media/03-create-custom-connector-with-apim-08.png
[image-09]: ../media/03-create-custom-connector-with-apim-09.png
[image-10]: ../media/03-create-custom-connector-with-apim-10.png
[image-11]: ../media/03-create-custom-connector-with-apim-11.png
[image-12]: ../media/03-create-custom-connector-with-apim-12.png
[image-13]: ../media/03-create-custom-connector-with-apim-13.png
[image-14]: ../media/03-create-custom-connector-with-apim-14.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts
[az cli install]: https://docs.microsoft.com/cli/azure/install-azure-cli
[pa]: https://powerapps.microsoft.com/
[pa cp]: https://powerapps.microsoft.com/communityplan/?azure-portal=true
[pa pricing]: https://docs.microsoft.com/powerapps/administrator/pricing-billing-skus

[artifacts]: https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/fusion-developers/artifacts.zip
