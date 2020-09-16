In this exercise, you will work with external data in your canvas app.

You will need to download the [spreadsheet](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-apps/shape-data/shape-data-learn.zip) to complete this exercise. Select download once the link opens. Extract the Excel spreadsheet and upload the spreadsheet to your own OneDrive.

**Add a Data Source**

1. Sign into [Power Apps](https://powerapps.microsoft.com/).

2.  Create a new Power Apps Canvas app from blank and call it
    *ExternalData.* Select the **Tablet** format.

3.  Make sure you have added the Excel sheet (link above) to your
    OneDrive.

4.  On the **Insert** tab, select **Gallery**, and then select the
    option for a vertical gallery.

5.  In the properties pane on the right, select the drop-down menu for
    the **Data source** property.

6.  In the Search box, type **OneDrive for Business** and select
    **OneDrive for Business** from the list. You could have also
    expanded Connectors and scrolled through all the available
    connectors until you found the **OneDrive for Business** connector.

7.  Select **+ Add a connection**.

8.  At the bottom of **OneDrive for Business**, click **Connect**.

9.  When prompted to **Choose an Excel file,** navigate to where you
    stored the Excel file you downloaded in Step 3 and select it.

10. Check the **Items** table and then click **Connect**.

You have connected to your **Excel** table in **OneDrive for Business**,
and you can display the data in the gallery control.

**Display and interact with your data in a gallery**

1.  Click on the gallery you have added.

2.  In the properties pane on the right, select the drop-down menu for
    the **Layout** property.

3.  Select the **Image, title, subtitle, and body** layout.

4.  In the properties pane on the right, select the Edit button for the
    **Fields** property and set the following points:

    -   **Body1**: Description

    -   **Image2**: Image

    -   **Subtitle2**: UnitPrice

    -   **Title2**: Name

5.  Click the X towards the right of **Data** to exit

6.  On the gallery, click on the price in the first row.

7.  In the formula bar, make sure Text is Selected and type the
    following:

    ```powerappsfl
    "$" & ThisItem.UnitPrice
    ```
8.  On the gallery, click on the image in the first row

9.  In the properties pane on the right, select the drop-down menu for
    the **Image Position** property

10. Select **Fill** and you will see that the image now fills up the
    space.

You have now configured and interacted with the data in your gallery.

**Moving data between collections and data sources**

1.  On the **Insert** tab, select **Button** and position your button
    underneath your gallery.

2.  Change the text on the button to **Add to Collection**

3.  Click on the button, and in the formula bar, replace false with this expression:

    ```powerappsfl
    Collect(ItemsCollection, Items)
    ```
    
    **ItemsCollection**: Refers to the Collection name

    **Items**: Refers to the Data Source name

    **Collect**: Will copy all records from the **Items** into the **ItemsCollection** collection

4.  Run the app. Click the button. Stop running the app.

5.  On the **View** tab, select **Collections** and then select **ItemsCollection**. You will then see that all records from **Items** data source has been added into the **ItemsCollection** collection.

 **Now we will explore other functions that can be used with Collections**

1.  On the **Insert** Tab, select **New Screen** and then click on
    **Blank**

2.  On the **Insert** Tab, select **Data Table** and position it next to
    the gallery.

3.  In the formula bar, make sure Items is selected and then enter the
    following expression:

     ![screenshot of item collection formula](../media/item-collection.png)

    This means that the Data Source for the table is the
   **ItemsCollection** collection and not the **Items** table in the Excel sheet.

4.  In the properties pane on the right, select the **Edit fields**
    button for the **Fields** property.

5.  Click **+ Add field**

6.  Select all available fields and then click **Add**

7.  Click the X towards the right of **Data** to exit

8.  On the **Insert** tab, select **Button** and position your button
    underneath your table. Repeat this process four times.

9.  Change the text on all four buttons to**: Add Column, Drop Column, Show
    Column, Rename Column** respectively.

10. Select the **Add Column** button.

11. Update the formula bar to this expression:

    ```powerappsfl
    ClearCollect(AddCollection, AddColumns(ItemCollection, "Revenue", UnitPrice * UnitSold))
    ```

    Here, we have created a new collection called *AddCollection, which
copies all data from the *ItemsCollection* collection but in addition--we use the *AddColumns* function to add a new column called *Revenue, which is calculated as UnitPrice * UnitsSold.

12. Select the **Drop Column** button.

13. Update the formula bar to this expression:

    ```powerappsfl
    ClearCollect(DropCollection, AddColumns(ItemCollection, "Revenue", UnitPrice * UnitSold))
    ```
    Here, we have created a new collection called *DropCollection, which
copies all data from the *ItemsCollection* collection but in addition--we use the *DropColumns* function to remove the UnitPrice Column.

14. Select the **Rename Column** button.

15. Update the formula bar to this expression:

    ```powerappsfl
    ClearCollect(RenameCollection, RenameColumns(ItemCollection, "Name", UnitPrice * UnitSold))
    ```
    Here, we have created a new collection called *RenameCollection, which
copies all data from the *ItemsCollection* collection but in addition--we use the *RenameColumns* function to rename the *Name* column to
*Product.*

16. Select the **Show Column** button.

17. Update the formula bar to this expression:

    ```powerappsfl
    ClearCollect(ShowCollection, ShowColumns(ItemCollection, "Name"))
    ```
    Here, we have created a new collection called *ShowCollection*, which
copies all data from the *ItemsCollection* collection but in addition--we use the *ShowColumns* function to only show the *Name* column.

18. Run the app. Click all four buttons. Stop running the app.

19. On the **View** tab, select **Collections** and then select each of
    the additional collections you have created to see what effect the
    functions had.

**Work with the Patch function**

1.  On the **Tree View** panel on the left, go back to the first screen
    by clicking on **Screen 1**.
    ![screenshot of tree view gallary.](../media/tree-view.png)

2.  On the **Insert** tab, select **Label** and then rename label to
    *Name*. Then position the label next to the gallery.

3.  Repeat the same step above but this time, rename the label to *New
    Description.*

4.  On the **Insert** tab, select **Input** and then select **Text
    Input.** Repeat this step and position both Text Inputs next to the
    labels made above **.** Your screen should now look like this:
   
    ![screenshot of final output.](../media/screen-output.png)

5.  On the **Insert** tab, select **Button** and position your button
    underneath your Labels. Change text on Button to *Update.*

6.  Click the Text Input next to the *Name* label.

7.  In the formula bar, make sure you have the **Default** property 
    selected and then change the expression to the following:

    ![screenshot of default property expression.](../media/default-property.png)

    This will display the **Name** property of the Date Source record
whenever you select it in the gallery. You can test this by running the
application, clicking on each item in the gallery and seeing that the
text in the input changes upon each click.

8.  Repeat steps 6 and 7 for the Text Input next to the New Description
    label. The formula bar expression will look like this:

    ![screenshot of default gallary expression.](../media/default-gallary.png)

9.  Select the **Update** button.

10. Update the formula bar to this expression:

    ```powerappsfl
    Patch(Items,First(Filter(Items, Name = TextInput1.Text)), { Description: TextInput2,Text })
    ```
    
Let's recap what we've done.

**Patch** - Allows us to *modify* or create a record in your data source.

**First(Filter**...) - We use this to filter the data source by Name.  The name is from the Text Input named TextInput1. If you have  renamed your Text Input, then you would need to update the expression  accordingly.

Once the matching record is found, it updates the description based on  what you have written in the *New Description* text input.

Test this by running the application. Select one of the items in the gallery and edit the description. Select **Update**. The description in the gallery change to the new description.
