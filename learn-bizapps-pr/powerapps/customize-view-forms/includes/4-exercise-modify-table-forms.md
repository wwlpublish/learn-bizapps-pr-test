In this exercise, you will modify the main form for **LocationTable**. To begin, sign in to Power Apps and then follow these steps:

1. From Power Apps, on the main menu, expand **Dataverse** and then select **Tables**.

1. Search for **LocationTable** that you created in the previous module. You can search for it by selecting **Custom** and then typing **location** in the search bar.

1. Select **LocationTable** and then select **Forms**. Find and select the **Main** information form to navigate to the forms design experience.

1. Add the **Owner** (a Dataverse standard field that identifies the user who created the record in the table) to the **Header** section of the table by dragging the **Owner** field and then dropping it to the upper right of the header.

1. Add the fields that a user will enter for locations in the **General** section of the form. Select the **Table columns** icon on the right, which will show the different fields in **LocationsTable**. Drag the fields and then drop them into the **General** section. Put the fields in the following order:

    1. **LocationId**

    1. **LocationName**

    1. **LocationCountry**

1. Set the **LocationId** field to be **Read-only**. Select the **LocationId** field, and on the right under **Properties**, select the **Read-only** checkbox.

1. To complete the changes, select **Publish** in the upper right.

    Now, you will test your form and create a few location records.

1. Select **Back** in the upper left to return to the table's menu.

1. Select **Data** to show the records view of the table.

1. Select the **+ Add record** button in the upper left to navigate to a new main form. This form should resemble the one that you customized in the previous steps.

1. Enter a new location and provide the following details:

    - **LocationName** - Contoso Main Factory

    - **LocationCountry** - Choose **USA** from the dropdown menu

1. Select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the General tab in the Location table, showing the Location ID, Location Name, and Location Country fields completed.](../media/16-location-table.png)](../media/16-location-table.png#lightbox)

### Modify the main form for TypeofAccidentTable

Sign in to Power Apps and then follow these steps to modify the main form for **TypeofAccidentTable**:

1. From Power Apps, on the main menu, expand **Dataverse** and then select **Tables**.

1. Search for **TypeofAccidentTable** that you created in the previous module. You can search for it by selecting **Custom** and then typing **typeofaccident** in the search bar.

1. Select the table and then select **Forms**. Find and select the **Main** information form to navigate to the forms design experience.

1. Add the **Owner** (a Dataverse standard field that identifies the user who created the record in the table) to the **Header** section of the table by dragging the **Owner** field and dropping it to the upper right of the header.

1. Add the fields that a user will enter for the type of accidents in the **General** section of the form. Select the **Table columns** icon on the right, which will show the different fields in **TypeofAccidentsTable**. Drag the fields and then drop them in the **General** section. Put them in the following order:

    1. **TypeofAccidentId**

    1. **AccidentName**

    1. **AccidentSeverity**

1. Set the **TypeofAccidentId** field to be read-only. Select the **TypeofAccidentId** field, and on the right under **Properties**, select the **Read-only** checkbox.

1. To complete the changes, select **Publish** in the upper right.

    Now, you will test your form and create a type of accident record.

1. Select **Back** in the upper left to return to the table's menu.

1. Select **Data** to show the records view of the table.

1. Select the **+ Add record** button in the upper left to navigate to a new main form. This form should resemble the one that you customized in the previous steps.

1. Enter a new type of accident and provide the following details:

    - **AccidentName** - Slip and Fall

    - **AccidentSeverity** - Select **2** from the dropdown menu

1. Select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the General tab with the Type of Accident ID, Accident Name, and Accident Severity fields completed.](../media/17-accident-table.png)](../media/17-accident-table.png#lightbox)

### Modify the main form for the AccidentTable

The process for modifying the **AccidentTable** form is the same as the previous processes. The difference with this one is that you will create a **one-column tab** in the **General** area to group the general accident information fields. Then, you will create another **one-column tab** in the **General** area to group the manager fields. Also, you will add a subgrid so that users can add employees that were involved in a particular accident.

1. From Power Apps, on the main menu, expand **Dataverse** and then select **Tables**.

1. Search for **AccidentTable** that you created in the previous module. You can search for it by selecting **Custom** and then typing **accident** in the search bar.

1. Select the table and then select **Forms**. Find and select the **Main** information form to navigate to the forms design experience.

1. Add the **Owner** to the **Header** section of the table by dragging the **Owner** field and then dropping it to the upper right of the header.

1. Add the fields that a user will enter for new accident records in the **General** section of the form. Select the **Table columns** icon on the right, which will show the different fields in **AccidentTable**. Drag the fields and then drop them into the **General** section. Put them in the following order:

    1. **AccidentId**

    1. **LocationId**

    1. **AccidentTypeId**

    1. **AccidentDate**

    1. **AccidentDescription**

1. Set the **AccidentId** field to be **Read-only**. Select the **AccidentId** field, and on the right under **Properties**, select the **Read-only** checkbox.

1. Select the **LocationId** field, and on the right under **Properties**, change the **Default view** from **LocationTable Lookup View** to **Active LocationTables**.

1. The **Show all views** checkbox will automatically clear. For this exercise, you want that option enabled, so select the checkbox. Two checkboxes are under the **Default view** dropdown menu: **Allow users to change view** and **Show all views**. Select both checkboxes.

1. Repeat the previous steps for the **AccidentTypeId** field and then set the **Default view** to **Active TypeofAccidentTables**.

1. Select the **Components** section and then select the **1-column tab** option to add a new tab in the **General** section.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Components section with layout options for column tabs and sections.](../media/18-components.png)](../media/18-components.png#lightbox)

1. In the **Properties** pane, for the **Label**, enter **Manager Review**. For the **Name**, enter **ManagerReview**. (Essentially, the name is the same for both; however, because the **Label** is what shows on the view, it should have a space. The **Name** field is a unique field that is used for referencing, so generally it's best to avoid spaces for the name.)

1. Add the following fields to the new tab:

    - **ManagerReviewed**

    - **ManagerComments**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Manage Review section with Label and Name display options highlighted.](../media/19-manage-review.png)](../media/19-manage-review.png#lightbox)

1. On the form, select the **General** tab.

1. From the left navigation menu, select the **Components** section, select **Subgrid**, and then select the **Show related records** checkbox.

1. Find **EmployeesTable** and then select **Active Employees** as the **Default view**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Subgrid layout options selected for Table and Default View.](../media/20-subgrid-views.png)](../media/20-subgrid-views.png#lightbox)

1. Select **Done** to add the subgrid. You should see it at the bottom of the form.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the subgrid views table and default view option menu with the Involved Employees label highlighted.](../media/21-involved-employees.png)](../media/21-involved-employees.png#lightbox)

1. Give the subgrid a more meaningful name. In the **Label** field under **Properties**, enter **Involved Employees**.

1. Select **Publish** to complete the form.

    Now, you can test your form and create a new accident record.

1. Select **Back** in the upper left to return to the table's menu.

1. Select **Data** to show the records view of the table.

1. Select the **+ Add record** button in the upper left to navigate to a new main form. This form should resemble the one that you customized in the previous steps.

1. Enter a new accident record and provide the following details:

    - **LocationId** - From the dropdown menu, select **Contoso Main Factory**

        > [!NOTE]
        > If you press the **Enter** key while you're on the dropdown menu, it will reveal the location names instead of their IDs.

    - **AccidentTypeId** - From the dropdown menu, select **Slip and Fall**

    - **AccidentDate** - 1/1/2021

    - **AccidentDescription** - Enter **Two employees fell because of wet floor in the main room.**

1. Select **Save**.

1. After the record is saved, the subgrid should appear, where you can add the involved employees.

1. Select **Add Existing Employee**, then press **Enter** in the **Look for records** box to reveal the employee names. Select **Adele Vance** and **Cameron White** from the list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Employee Tables list in the Lookup Records section, showing records for employee id 1001 and 1002.](../media/22-records.png)](../media/22-records.png#lightbox)

1. Select **Add** to add the employee names.

1. You might need to select **Refresh** for the names to show in the list.

1. Select **Save** to complete the process.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a list of Involved Employees.](../media/23-involved-employees.png)](../media/23-involved-employees.png#lightbox)
