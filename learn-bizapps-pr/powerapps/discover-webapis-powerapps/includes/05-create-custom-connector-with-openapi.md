In this exercise you'll learn how to create a custom connector from an OpenAPI document.

> [!NOTE]
> To complete this exercise, you may need to sign up for the [Power Apps Community Plan][pa cp].


## Create Custom Connector from OpenAPI Document ##

There are several ways of creating a custom connector for Power Apps. This time, you will create one using the OpenAPI document. Suppose you have an `openapi.json` document and API access key provided by the professional development team.

1. After logging into [Power Apps][pa] dashboard, open the `Data` blade and click the `Custom Connectors` menu on the left-hand side. Then, click the `➕ New custom connector` button at the right-top corner and select the `Import an OpenAPI file` menu.

    ![Many Ways Creating Custom Connector][image-01]

1. When a pop-up modal appears, give the name, **InventoryManager**, to the `Connector name` field and click the `Import` button to import the OpenAPI document, `openapi.json`. Then, click the `Continue` button.

    ![OpenAPI File Import][image-02]

1. As the OpenAPI document has everything you need to create the custom connector, click the `✅ Create connector` button at the right-top corner.

    ![Custom Connector General Tab Create Connector][image-03]

1. Once the custom connector is created, you will see the message, `✅ Custom connector has been successfully created` at the top of the screen.

    ![Custom Connector General Tab Connector Created][image-04]

1. Click the `Custom Connectors` menu on the left-hand side of the page, and you will see the custom connector created. The `➕` button at the right-hand side.

    ![New Custom Connector][image-05]

1. When a pop-up modal shows up, you will see the API Key field. Enter the API key handed from the professional development team. Then click the `Create` button.

    ![New Custom Connector Pop-up Modal][image-06]

1. Go to the `Connections` menu, and you will see the new connection has been created.

    ![New Connection][image-07]

You have completed creating a custom connector for inventory management.


[image-01]: ../media/05-create-custom-connector-with-openapi-01.png
[image-02]: ../media/05-create-custom-connector-with-openapi-02.png
[image-03]: ../media/05-create-custom-connector-with-openapi-03.png
[image-04]: ../media/05-create-custom-connector-with-openapi-04.png
[image-05]: ../media/05-create-custom-connector-with-openapi-05.png
[image-06]: ../media/05-create-custom-connector-with-openapi-06.png
[image-07]: ../media/05-create-custom-connector-with-openapi-07.png

[pa]: https://powerapps.microsoft.com/
[pa cp]: https://powerapps.microsoft.com/communityplan/?azure-portal=true
