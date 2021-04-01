You've created the connector, tested it, and now you'll learn how to use it in a canvas app.


## Create Canvas App ##

1. First of all, create a blank canvas app. Go to the `Create` menu at the left-hand side and click the `Canvas app from blank` panel.

    ![Create Power Apps][image-01]

1. When a modal pops up, give the name, **Inventory**, to the `App name` field and leave the format as default. Then click the `Create` button.

    ![Create Power Apps Modal][image-02]

1. Navigate the `Data` menu to add the custom connector. You will see nothing in the Data pane.

    ![Data Pane][image-03]

1. Click the `Add data` button and enter inventory in the search box, and you will see the `InventoryManager` custom connector.

    ![Custom Connector Search][image-04]

1. Click the `InventoryManager` connector, and you will see the `InventoryManagement` connection.

    ![Connection Added][image-05]

1. Your custom connector is successfully added to your Power Apps. Navigate to the `Insert` menu at the top and click `Button` to add a button control onto the canvas.

    ![Add Button][image-06]

1. While `Button1` is selected, choose the property value to **OnSelect** and enter the function formula below. `InventoryManagement` represents the custom connector and `getapiwarehouselocations()` represents an API endpoint. The `warehouses` collection stores the result that the `getapiwarehouselocations()` function returns.

    ```powerappsfl
    ClearCollect(warehouses, InventoryManagement.getapiwarehouselocations())
    ```

    ![Add Formula][image-07]

1. Click `Gallery` and select the `Vertical` control.

    ![Add Vertical Gallery][image-08]

1. Once the `Vertical` control is added, it asks the data source.

    ![Vertical Gallery Added][image-09]

1. Select the `warehouses` collection declared above. Then the `Vertical` control changes below because the `warehouses` collection currently contains nothing.

    ![Vertical Gallery Data Source Mapped][image-10]

1. While holding your `Alt` key on Windows (or `Option` key on Mac), click the `Button` button, and you will see the list of warehouse locations showing up in the `Vertical` control.

    ![Custom Connector Result in Vertical Gallery][image-11]

You have successfully included the custom connector into your Power Apps app.


[image-01]: ../media/08-use-custom-connector-in-powerapps-01.png
[image-02]: ../media/08-use-custom-connector-in-powerapps-02.png
[image-03]: ../media/08-use-custom-connector-in-powerapps-03.png
[image-04]: ../media/08-use-custom-connector-in-powerapps-04.png
[image-05]: ../media/08-use-custom-connector-in-powerapps-05.png
[image-06]: ../media/08-use-custom-connector-in-powerapps-06.png
[image-07]: ../media/08-use-custom-connector-in-powerapps-07.png
[image-08]: ../media/08-use-custom-connector-in-powerapps-08.png
[image-09]: ../media/08-use-custom-connector-in-powerapps-09.png
[image-10]: ../media/08-use-custom-connector-in-powerapps-10.png
[image-11]: ../media/08-use-custom-connector-in-powerapps-11.png
