In order to use Web APIs in Power Apps, you should create a custom connector. There are several ways creating the custom connector.

![Many Ways Creating Custom Connector][image-01]

This time, you are going to use [Azure API Management][az apim] to create a custom connector.


## APIs on API Management ##

Here is the inventory management API details hosted by API Management.

![Inventory Management APIs on API Management][image-02]

In order to access to API Management from outside, you should have a subscription key. Go to the `Subscriptions` blade, click the three dots (`...`) and select the `Show/hide keys` menu.

![Subscription Blade][image-03]

Then, copy the subscription key from either `Primary key` or `Secondary key`.

![Copy Subscription Key][image-04]


## Create Custom Connector Directly from API Management ##

After logging into [Power Apps][pa] dashboard, open the `Data` blade and click the `Custom Connectors` menu at the left-hand side. Then, click the `➕ New custom connector` drop down menu at the right top corner and select the `Create from Azure Service (Preview)` menu.

![New Custom Connector][image-05]

When a modal is open, enter the following information:

* Give **InventoryManager** to Connector name.
* Select your Azure subscription.
* Choose **API Management** as Azure service.
* Select the API Management instance, **apim-greenleaf-wus2**, for the inventory management.
* Choose the API name, **green-leaf-inventory-management**, from the selected API Management instance.

Then, click the `Continue` button.

![Custom Connector Details][image-06]

At the General information section, confirm `Scheme`, `Host` and `Base URL` values whether they are identified from the API management above. Then, click the `Security ➡️` button.

![General Information][image-07]

At the Security section, confirm `API Key` as the authentication type, `API Key` as the Parameter label, `Ocp-Apim-Subscription-Key` as the Parameter name and `Header` as the Parameter location, identified from the API Management above. Then, click the `Definition ➡️` button.

![Security][image-08]

At the Definition section, leave them all as they are and click the `✅ Create connector` button at the right top corner.

![Definition][image-09]

You just created a new custom connector. Make sure your new custom connector is of name, `InventoryManagement`.


## Test Custom Connector ##




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

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts

[pa]: https://powerapps.microsoft.com/
