You can import data, in bulk, from Microsoft Excel or comma-separated values (CSV) files into your Common Data Service (CDS) for Apps database.

Every entity has required fields that must exist in your input file. We recommend that you create a template. A template will save you time and effort. First, export data from the entity. You'll use the same file (updated with your data) to import data into the entity.

## Create a file template
You can do a one-time data export from a standard entity or a custom entity, and you can export data from more than one entity at a time. If you export data from more than one entity, each entity is exported into its own Microsoft CSV file. In this example, you'll create templates for both the **Pet** and **Account** entities.

1. On [powerapps.com](https://web.powerapps.com/), in the **Entities** list, select **Export data**.
1. Select the **Account** and **Pet** entities, and then select **Export data**.
1. After the export is finished, select **Download exported data**, and save the files.

## Copy data into your template
When you add data to a template file, you must make sure the data is unique. You can use either *primary keys* or *alternate keys*.

1. Open the CSV files that you created in the previous section.
1. Add at least one new row of data.
1. Save the file.

## Import the file
1. In the left navigation pane, expand **Data**, and then select **Entities**.
1. Select the **Pets** entity, select **Get Data**, and then select **Get data from Excel**.
1. Select the file that you created.
1. After the file is uploaded, and the **Mapping status** field indicates that mapping was successful, select **Import** in the upper-right corner.

    > [!div class="mx-imgBorder"]
    > ![Example of a Mapping status field and Import button for a successful upload](../media/success-map-imp.png)

1. After the import is successful, you'll see the total number of inserts and updates.
