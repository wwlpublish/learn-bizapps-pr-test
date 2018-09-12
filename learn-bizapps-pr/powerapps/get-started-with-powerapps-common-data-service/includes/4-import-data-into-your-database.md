You can import data into your Common Data Service for Apps database in bulk from Microsoft Excel or CSV files. 

Every entity has required fields that must exist in your input file. We recommend that you create a template. First, export data from the entity. You will use the same file (modified with your data) to import data into the entity. Using a template saves time and effort. 

## Create a file template
You can do a one-time data export from a standard entity or custom entity, and you can export data from more than one entity at a time. If you export data from more than one entity, each entity is exported into its own Microsoft CSV file. In this example, you will create templates for both the **Pet** and **Account** entities.

1. On the [powerapps.com](https://web.powerapps.com/) Entities list, click **Export data**.  
1. Select the **Account** and **Pet** entities, and then click **Export data**.

1. After the export finishes, click **Download exported data**, and save the files.


## Copy data into your templates
When you add data to a template files, you'll need to make sure that the data is unique. You can use either **primary keys** or **Alternate Keys**.  
1. Open the CSV files that you created.
1. Add at least one new row of data. 
1. Save the file.

## Import the file
1. Expand the **Data** section of the left navigation pane, and then click **Entities**.  
1. Select the **Pets** entity, click **Get Data**, and then click **Get data from Excel**.  
1. Select the file that you created. After it has been uploaded and the **Mapping status** is green, in the top-right corner, click **Import**.
  > [!div class="mx-imgBorder"] 
  > ![Example of a successful **Mapping status** and **Import** button](../media/success-map-imp.png)

1. After the import finishes successfully, you'll see the total number of inserts and updates.  
