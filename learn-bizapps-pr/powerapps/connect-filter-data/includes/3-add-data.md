1. In a new browser tab, navigate to [make.powerapps.com](https://make.powerapps.com/?azure-portal=true).

1. Select **Dataverse/Data** and then select **Tables**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the navigation pane with Dataverse and Tables highlighted.](../media/tables.png)](../media/tables.png#lightbox)

1. Choose your **Expense Report** table.
   > [!Tip]
   > You may need to change the view to custom tables.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the list of tables with Expense Report highlighted.](../media/expense-report.png)](../media/expense-report.png#lightbox)

1. Once there, select the **Data** tab. It should say you have no records. Select the **Data** drop-down on the ribbon and select **Edit data in Excel**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Expense Report table's Data tab with the Data menu expanded to show the Edit data in Excel option.](../media/edit-data.png)](../media/edit-data.png#lightbox)

Once Excel loads, you'll need to **Enable Editing** and ensure you're signed in to the correct tenant by checking the logged-in user in the right-hand editing pane.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of PowerApps with the logged-in user highlighted.](../media/user.png)](../media/user.png#lightbox)

Afterward, you can edit the sheet like you would any other Excel sheet. The data connector panel on the right will pop up options and information for various fields, such as a date picker for your arrival and departure date fields. The Traveler field can also be chosen here.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Excel spreadsheet with the data connector panel to the right.](../media/excel.png)](../media/excel.png#lightbox)

After filling in the Trip Destination, Arrival Date, Departure Date, and Traveler, you can select **Publish** to push your changes to Dataverse. Feel free to add a few more rows of data with different users since we'll be filtering based on that field. Don't worry about Report Status right now. Choice fields can be difficult to edit this way, so we'll wait until we can edit in the canvas app for that one.

> [!NOTE]
> If you do not have any users in your User table, follow the above steps to populate that table first.

Once you publish, go back into Dataverse and refresh your data. You should now see the data you added in Excel.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Expense Report table with the Refresh data button highlighted.](../media/refresh.png)](../media/refresh.png#lightbox)
