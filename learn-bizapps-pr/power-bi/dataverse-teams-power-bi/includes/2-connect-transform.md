To connect to Dataverse for Teams data, install the Power BI Desktop, then get the environment URL.

## Install the Power BI Desktop

The Power BI Desktop is a free application that allows you to connect, transform, and visualize your data. It can connect to many data sources including SQL, Excel, SharePoint Lists, and Dataverse for Teams tables. Power BI Desktop then transforms and cleans the data to create interactive reports.

There are two ways to install the Power BI Desktop:

- **Windows 10** - Use the [Microsoft Store](https://www.microsoft.com/store/productId/9NTXR16HNW1T/?azure-portal=true). Updates to the software automatically install each month.

- **Windows 8 & 10** - Download the installer from [https://powerbi.microsoft.com/desktop](https://powerbi.microsoft.com/desktop/?azure-portal=true). Each month you're prompted to install the latest updates to the application.

## Get the environment URL for the Dataverse for Teams table

The environment URL for the Dataverse for Teams table is required when connecting with Power BI Desktop. To find the environment URL:

1. Launch Teams or use your browser to open [https://teams.microsoft.com](https://teams.microsoft.com/?azure-portal=true).

1. Select the **Power Apps** app.

1. Select the **Build** tab.

1. Select the team that contains the Dataverse for Teams table.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps Build tab with the Contoso team highlighted.](../media/image-2.png)](../media/image-2.png#lightbox)

1. Select the **About** tab then **Session details**. Copy the **Instance url** into notepad for reference later. The **Instance url** is the environment URL to connect Power BI Desktop to the Dataverse for Teams table.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Apps About tab with Session details selected and Instance U R L highlighted.](../media/image-3.png)](../media/image-3.png#lightbox)

## Connect to Dataverse for Teams table data

1. Launch Power BI Desktop.

1. From the **Home** ribbon, select **Get data**.

1. Select **Power Platform** then **Dataverse**. Select **Connect** to continue.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Get Data page with Power Platform selected and Dataverse highlighted.](../media/image-4.png)](../media/image-4.png#lightbox)

1. Enter in the environment URL for the Dataverse for Teams table that you copied earlier. Remove the **HTTPS://** and the trailing **/** from the URL. Set **Data Connectivity mode** to **Import,** then select **OK**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Dataverse dialog with Environment domain set to org0e211cd1.crm.dynamics.com and Data Connectivity mode set to Import.](../media/image-5.png)](../media/image-5.png#lightbox)

1. Select **Sign in,** then use your credentials when prompted. Once successfully signed in, press **Connect.**

1. In the **Navigator** screen, start typing in the name of the table to locate it. Select the table by selecting the check box next to the name. For our example, select the Cost Trends table we created earlier.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigator screen with search results for "cost." The cost trends table is selected and the Transform Data button is highlighted.](../media/image-6.png)](../media/image-6.png#lightbox)

1. Select **Transform Data** to open the table in Power Query Editor.

    Power Query Editor allows us to clean the data and makes it easier to create charts, graphs, and other visualizations. In the following steps, we use Power Query Editor to transform the data.

## Transform the data

Transforming data is the process of changing data to make it easier to work with. For example, you may want to remove unnecessary columns, change data types, or filter the data before creating Power BI reports. Dataverse for Teams tables have system columns used by Dataverse for Teams. These system columns aren't necessarily needed when creating Power BI visualizations.

For the Cost Trends table data, we need to remove unnecessary columns, rename columns, and verify that the correct data types are used.

1. To reduce the number of columns in the Power Query Editor **Home** ribbon, select **Choose Columns**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor Home ribbon with Choose Columns selected.](../media/image-7.png)](../media/image-7.png#lightbox)

1. Select only the following columns. The prefix is different in your environment.

    - cr71f_date
    - cr71f_materials
    - cr71f_printing
    - cr71f_assembly
    - cr71f_productiontotal
    - cr71f_shipping
    - cr71f_packagetotal

    Select **OK** to continue.

1. Rename columns by right-clicking the column name and selecting **Rename**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor with the first column name right-clicked and the Rename option selected.](../media/image-8.png)](../media/image-8.png#lightbox)

    Rename the columns to the following:

    - Date
    - Materials
    - Printing
    - Assembly
    - Total Production Cost
    - Shipping
    - Total Cost

1. Verify that the data type is correct for each column by looking at the icon next to the column names. For example, the Date column uses **Date/Time** data type, so 12:00:00 AM is added to each entry. Right-click the column name and select **Change Type-> Date** so that only the date appears.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor with the Date column right-clicked and Change Type selected and Date highlighted.](../media/image-9.png)](../media/image-9.png#lightbox)

    Some common data types and their icons:

    | Icon | Data type |
    |------|-----------|
    | ![Screenshot of the date and time icon.](../media/image-10.png) | Date/Time |
    | ![Screenshot of the date icon.](../media/image-11.png) | Date |
    | ![Screenshot of the whole number icon.](../media/image-12.png) | Whole Number |
    | ![Screenshot of the percentage icon.](../media/image-13.png) | Percentage |
    | ![Screenshot of the string icon.](../media/image-14.png) | String |

1. In the **Query Settings** tab, rename the table by selecting the **Name** and typing in **Cost Trends**. All of the transformation actions are listed under **Applied Steps**. You can undo a step by deleting it from the list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the query settings tab with the name set to Cost Trends.](../media/image-15.png)](../media/image-15.png#lightbox)

1. Select **Close & Apply** from the **Home** ribbon to load the data with the transformations into Power BI Desktop.

For more information about the Power Query Editor, see the Summary section at the end of the module.
