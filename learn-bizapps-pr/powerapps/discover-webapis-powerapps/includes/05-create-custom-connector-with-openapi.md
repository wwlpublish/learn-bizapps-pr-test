Maria has been studying up on Power Apps in her spare time. She believes that Power Apps excels at enabling business professionals to develop applications, which are easy to create and deploy. She also wants to build a Power App with existing web APIs through a custom connector. As Crystal's team is fully stretched and unable to create the custom connector for Maria, she needs to create the custom connector for the inventory management by herself. Fortunately, Crystal has provided Maria with an OpenAPI document and API key for authentication.


## Create Custom Connector from OpenAPI Document ##

There are several ways of creating a custom connector from Power Apps. This time, you will create the one using the OpenAPI document because you have the OpenAPI document file.

After logging into [Power Apps][pa] dashboard, open the `Data` blade and click the `Custom Connectors` menu on the left-hand side. Then, click the `➕ New custom connector` button at the right-top corner and select the `Import an OpenAPI file` menu.

![Many Ways Creating Custom Connector][image-01]

When a pop-up modal appears, give the name, **InventoryManager**, to the `Connector name` field and click the `Import` button to import the OpenAPI document, `openapi.json`. Then, click the `Continue` button.

![OpenAPI File Import][image-02]

As the OpenAPI document has everything you need to create the custom connector, click the `✅ Create connector` button at the right-top corner.

![Custom Connector General Tab Create Connector][image-03]

Once the custom connector is created, you will see the message, `✅ Custom connector has been successfully created` at the top of the screen.

![Custom Connector General Tab Connector Created][image-04]

Click the `Custom Connectors` menu on the left-hand side of the page, and you will see the custom connector created. The `➕` button at the right-hand side.

![New Custom Connector][image-05]

When a pop-up modal shows up, you will see the API Key field. Enter the API key copied at the beginning of this unit. Then click the `Create` button.

![New Custom Connector Pop-up Modal][image-06]

Go to the `Connections` menu, and you will see the new connection has been created.

![New Connection][image-07]

You have completed creating a custom connector for inventory management.


## Key Takeaways ##

After this unit, you are now able to:

* Create a custom connector from the OpenAPI document, and
* Create a connection of the custom connector by providing authentication details.


[image-01]: ../media/05-create-custom-connector-with-openapi-01.png
[image-02]: ../media/05-create-custom-connector-with-openapi-02.png
[image-03]: ../media/05-create-custom-connector-with-openapi-03.png
[image-04]: ../media/05-create-custom-connector-with-openapi-04.png
[image-05]: ../media/05-create-custom-connector-with-openapi-05.png
[image-06]: ../media/05-create-custom-connector-with-openapi-06.png
[image-07]: ../media/05-create-custom-connector-with-openapi-07.png

[pa]: https://powerapps.microsoft.com/
