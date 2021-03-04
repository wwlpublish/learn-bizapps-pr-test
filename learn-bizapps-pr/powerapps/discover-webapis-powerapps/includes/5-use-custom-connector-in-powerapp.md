:::row:::
  :::column span="4":::
    Maria works in inventory management and makes sure Green Leaf runs like a well-oiled machine. She verifies the warehouse has enough parts and if not orders more using a legacy system that Crystal wrote. But more than that – she performs audits on the inventory, checks with vendors for the best prices, and other inventory supply management tasks.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Maria](../../shared/media/maria.png)
  :::column-end:::
:::row-end:::

Maria now has got a custom connector up and running, for inventory management. She wants to use the connector in her Power App.


## Create Canvas App ##

First of all, create a blank canvas app. Go to the `Create` menu at the left-hand side and click the `Canvas app from blank` panel.

![Create Power App][image-01]

When a modal pops up, give the name, **Inventory**, to the `App name` field and leave the format as default. Then click the `Create` button.

![Create Power App Modal][image-02]

In order to add the custom connector, navigate the `Data` menu. You will see nothing in the Data pane.

![Data Pane][image-03]

Click the `Add data` button and enter inventory in the search box, and you will see the `InventoryManager` custom connector.

![Custom Connector Search][image-04]

Click the `InventoryManager` connector, and you will see the `GreenLeafInventoryManagement` connection.

![Connection Added][image-05]

Your custom connector is successfully added into your Power Apps. Navigate to the `Insert` menu at the top and click `Button` to add a button control onto the canvas.

![Add Button][image-06]

While `Button1` is selected, choose the property value to **OnSelect** and enter the function formula below. `GreenLeafInventoryManagement` represents the custom connector and `getapifactorylocation()` represents an API endpoint. The `factories` collection stores the result that the `getapifactorylocation()` function returns.

```powerappsfl
ClearCollect(factories, GreenLeafInventoryManagement.getapifactorylocation())
```

![Add Formula][image-07]

Click `Gallery` and select the `Vertical` control.

![Add Vertical Gallery][image-08]

Once the `Vertical` control is added, it asks the data source.

![Vertical Gallery Added][image-09]

Select the `factories` collection declared above. Then the `Vertical` control changes below, because the `factories` collection currently contains nothing.

![Vertical Gallery Data Source Mapped][image-10]

While holding your `Alt` key on Windows (or `Option` key on Mac), click the `Button` button, and you will see the list of factory locations showing up in the `Vertical` control.

![Custom Connector Result in Vertical Gallery][image-11]

You have successfully included the custom connector into your Power Apps.


## Key Takeaways ##

After this unit, you are now able to:

* Create a blank canvas app,
* Add a custom connector to the app,
* Add controls to the canvas,
* Assign a formula to a control, and
* Call an API through the custom connector and render the result to the control.


[image-01]: ../media/5-use-custom-connector-in-powerapp-01.png
[image-02]: ../media/5-use-custom-connector-in-powerapp-02.png
[image-03]: ../media/5-use-custom-connector-in-powerapp-03.png
[image-04]: ../media/5-use-custom-connector-in-powerapp-04.png
[image-05]: ../media/5-use-custom-connector-in-powerapp-05.png
[image-06]: ../media/5-use-custom-connector-in-powerapp-06.png
[image-07]: ../media/5-use-custom-connector-in-powerapp-07.png
[image-08]: ../media/5-use-custom-connector-in-powerapp-08.png
[image-09]: ../media/5-use-custom-connector-in-powerapp-09.png
[image-10]: ../media/5-use-custom-connector-in-powerapp-10.png
[image-11]: ../media/5-use-custom-connector-in-powerapp-11.png
