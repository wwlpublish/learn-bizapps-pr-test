You can import data into your Microsoft Dataverse database in bulk from Microsoft Excel or CSV files. 

Every table has required columns that must exist in your input file. We recommend that you create a template. A template will save you time and effort. First, export data from the table. You'll use the same file (updated with your data) to import data into the table.

## Create a file template
You can do a one-time data export from a standard table or a custom table, and you can export data from more than one table at a time. If you export data from more than one table, each table is exported into its own Microsoft CSV file. In this example, you'll see how to export the **Pet** table but remember you could select several tables to export if you would like.

1. On [powerapps.com](https://make.powerapps.com/), in the left navigation pane, expand **Data**, select **tables**, select **Data** at the top, and then select **Export data**.
2. Select the **Pet** table, and then select **Export data**.
3. After the export is finished, select **Download exported data**, and save the file.

## Copy data into your template
When you add data to a template file, you must make sure the data is unique. You can use either *primary keys* or *alternate keys*.

1. Open the CSV file that you created in the previous section.
2. Add at least one new row of data but you only need to add information to the following columns below.

    - **Appointment date**
    - **Breed**
    - **Pet Name**
    - **Species**

    ![Example of adding new row of data](../media/add-new-row.png)

3. Save the file. 

## Import the file
1. In the left navigation pane, expand **Data**, and then select **tables**.
2. Select the **Pet** table, select the drop down arrow next to Get Data, and then select **Get data from Excel**.
3. Click **Upload** and select the file that you just updated and saved from the previous section.
4. After the file is uploaded, click **Map columns**.
5. Set the following Pet columns Source values to **None**.

    - **Import Sequence Number**
    - **Owning Business Unit**
    - **Pet**
    - **Status Reason Value**
    - **Status Value**
    - **Time Zone Rule Version Number**
    - **UTC Conversion Time Zone Code**
    - **Version Number**
 
    ![Screenshot example of Pet columns Source values.](../media/mapping-fields.png)

6. In the upper right, click **Save changes**.

    ![Screenshot example of a Mapping status column and Import button for a successful upload.](../media/mapping-warning.png)

    You will notice under Mapping status, it states "Mapping warnings exist". The reason for this mapping status is because we set some of the columns to None or Not. This is fine because we didn't want to include those columns so this warning can be ignored. 

7. In the upper right, click **Import**.

    After the data has been successfully imported, you'll see the total number of inserts and updates. Now let's go take a quick look at the imported data

8. On the left, select **tables**.
9. Select the **Pet** table.
10. On the table designer toolbar, select **Data**.

Notice that the Account column is empty, this is because when you updated the Excel export file and update columns you were not instructed to update this column. The reason you were not instructed to update the Account column is because you cannot set a lookup value when importing data from Excel, this must be done from Power Apps.