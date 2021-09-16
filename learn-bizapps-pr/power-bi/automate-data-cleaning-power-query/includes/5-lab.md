Now is your opportunity to give Power Query a try with this guided, step-by-step use case. Use the provided example data source files to complete the exercises.

## Lab 01 - Analytics in Excel: Use Power Query in Excel

The estimated time to complete this lab is 30 minutes.

In this hands-on learning lab, you will complete the following tasks:

1. Use Power Query to connect to a .csv source data file - Customers

1. Use Power Query transformations to splice a column by delimiter - Customers

1. Use Power Query to connect to an Excel source data file - Quotes

1. Use Power Query transformations to unpivot - Quotes

1. Use Power Query transformations to clean - Quotes

## Lab prerequisites

The following prerequisites and setup must be in place for successful completion of the exercises:

- You must be connected to the internet.

- You must have Microsoft Office installed.

- Sign up for [Microsoft Power BI](https://aka.ms/pbimaiadtraining/?azure-portal=true).

- At a minimum, you should have a computer with two cores and 4 GB of RAM that is running one of the following versions of Windows: Windows 8 / Windows Server 2008 R2 or later.

- If you choose to use Internet Explorer, it will require version 10 or greater. You can also use Microsoft Edge or Google Chrome.

- Verify whether you have a 32-bit or 64-bit operating system to decide if you need to install the 32-bit or 64-bit applications.

  > [!NOTE]
  > 64-bit Excel and Power BI Desktop is best.

- Download the Attendee Content: Create a folder called MAIAD on the C: drive of your local machine. Copy all content from the folder called MAIADAttendee to the MAIAD folder that you created (C:\MAIAD).

- Download and install Power BI Desktop by using any one of the following options:

  - If you have Windows 10, use Microsoft App Store to download and install Power BI Desktop application.

  - Download and install [Microsoft Power BI Desktop](https://www.microsoft.com/download/details.aspx?id=45331&azure-portal=true).

- If you already have Power BI Desktop installed, ensure that you have the latest version of Power BI downloaded.

## Document structure

Source data or starting files for each lab are located within each lab folder.

- Lab 01 is completed by using Power Query in the Excel application.

- Lab 02A and Lab 02B are completed by using Power BI Desktop application.

- Lab 03A is completed by using Power BI Desktop, Power BI service, and Excel applications.

- Lab 03B is completed by using Excel and Power BI service applications.

Each lab comes with step-by-step instructions to follow and contains screen images throughout the instructions. The key actions for each step are identified by **bold** text. Pay attention to notes, tips, and other important information. Each lab contains a completed solution file that can be used as a reference.

## Overview

The estimated time to complete this lab is 30 minutes.

In this lab, you will complete the following tasks:

1. Use Power Query to connect to a CSV source data file - Customers

1. Use Power Query transformations to split column by delimiter - Customers

1. Use Power Query to connect to an XLSX source data file - Quotes

1. Use Power Query transformations to unpivot - Quotes

1. Use Power Query transformations to clean - Quotes

    > [!NOTE]
    > This lab has been created based on the sales activities of the *fictitious* wireless provider company called SureWi, which has been provided by [P3 Adaptive](https://p3adaptive.com/?azure-portal=true). The data is property of P3 Adaptive and has been shared with the purpose of demonstrating Excel and Power BI functionality with industry sample data. Any use of this data must include this attribution to P3 Adaptive.

## Exercise 1: Use Power Query to connect to CSV - Customers.csv

In this exercise, you will use Excel to connect to a CSV source data file.

### Task 1: Launch Excel

In this task, you will launch a new blank worksheet to get started.

1. Launch Excel.

1. Create a new blank workbook.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a new blank workbook in Excel.](../media/5-1-blank.png)](../media/5-1-blank.png#lightbox)

### Task 2: Use Power Query to connect to CSV

In this task, you will connect to the Customers CSV source data file.

1. Select the **Data** tab on the main Excel ribbon.

1. Select **Get Data > From File > FromText/CSV**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Data tab in Excel, showing Get Data > From File > From Text/CSV selected.](../media/5-2-from-text.png)](../media/5-2-from-text.png#lightbox)

1. Go to the **D:\data-cleaning\AttendeeLab MaterialsLab 01 MAIAD Lab 01 - Data Source - Customers.csv** file.

   The **Preview** area will display a sample of the customer's data, column names, and values.

    > [!NOTE]
    > This example is only a preview of the data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigator window showing preview data from MAIAD Lab 01 - Data Source - Customers.csv, with the Transform Data button highlighted.](../media/5-3-transform.png)](../media/5-3-transform.png#lightbox)

1. Select the **Transform Data** button, which will launch the Power Query Editor window.

    > [!NOTE]
    > When you are working in Power Query, it's best to maximize the Power Query Editor window so that you can fully view the Power Query window menus, panes, and options.

1. By default, the **Queries** pane on the left side of the Power Query Editor window will be collapsed. Select the arrow in the **Queries** pane to expand and open it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor window with the Queries pane collapsed and the arrow shown to expand the pane.](../media/5-4-expand-pane.png)](../media/5-4-expand-pane.png#lightbox)

1. In the **Queries** pane, right-click the default query name called **MAIAD Lab 01 - Data Source - Customers** and then **Rename** the query to **Customers**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queries pane open, showing the MAIAD Lab 01 - Data Source - Customers query and the Rename button highlighted.](../media/5-5-rename.png)](../media/5-5-rename.png#lightbox)

    > [!TIP]
    > Queries that will be loaded to use as part of a data model should be given a clear, descriptive, and user-friendly name that describes what the data represents, such as Customers, Quotes, Invoices, Products, or Geography.

## Exercise 2: Use Power Query transformations to split a column by delimiter - Customers

In this exercise, you will use Power Query to extract the first name from the Contact column.

### Task 1: Use the Column from Examples transformation

In this task, you will create a new column called **First Name** by using the **Add Column > Column from Examples** transformation to split the **Contact** by a delimiter.

1. From the **Preview** grid, select the **Contacts** column.

1. From the **Add Column** tab, select **Column from Examples > From Selection**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Power Query Editor window displaying the Add Column menu options.](../media/5-6-add-column.png)](../media/5-6-add-column.png#lightbox)

    > [!NOTE]
    > This action opens a new user interface window called **Add Column From Examples**. This window is similar to the **Preview** grid, but it's a separate window that allows you to enter the proposed value so that Power Query can identify the pattern and formula to apply, thus helping you achieve the end results.

1. In the **Add Column From Examples** window, in the **Column1** column, type the value **Hugo** and then press the **Enter** key.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Add Column From Examples window showing Hugo entered in Column1.](../media/5-7-add-from-examples.png)](../media/5-7-add-from-examples.png#lightbox)

    > [!NOTE]
    > After you have pressed the **Enter** key, Power Query will identify if a pattern exists in the data to populate the values for all rows.

1. Double-click the **Text Before Delimiter** default header and rename the new column to **First Name**. Select the **OK** button.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Column From Examples window showing the renaming of the default column name to First Name.](../media/5-8-rename.png)](../media/5-8-rename.png#lightbox)

    > [!NOTE]
    > The **Preview** grid in Power Query Editor will now show the new **First Name** column, which was created by parsing out the **First Name** from the **Contact** by using the **Column from Examples** transformation.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Preview grid in Power Query Editor showing the new First Name column.](../media/5-9-first-name.png)](../media/5-9-first-name.png#lightbox)

## Exercise 3: Use Power Query to connect to XLSX - Quotes.xlsx

In this exercise, you will use Excel to connect to an XLSX source data file.

### Task 1: Connect to XLSX source data from within the Power Query Editor window

In this task, you will start from within the **Power Query Editor** window.

1. From the **Home** menu, select **New Source > File > Excel**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power Query Editor window showing the Home tab options with the New Source > File > Excel option selected.](../media/5-10-new-source.png)](../media/5-10-new-source.png#lightbox)

1. Go to the **D:\data-cleaning\AttendeeLab MaterialsLab 01 MAIAD Lab 01 - Data Source - Quotes.xlsx** file.

1. In the **Navigator** window, select the **Lab 01 - Quotes** worksheet.

    > [!NOTE]
    > This example is only a preview of the data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Navigator window showing the Lab 01A - Quotes worksheet highlighted.](../media/5-11-navigator.png)](../media/5-11-navigator.png#lightbox)

1. Select the **OK** button to load as a second query in the **Power Query Editor** window.

1. In the **Queries** pane, right-click the default **Lab 01 - Quotes** query name and **Rename** it to **Quotes**.

    > [!div class="mx-imgBorder"]
    > [![Screesnshot of the Queries pane in the Power Query Editor window, with the Lab 01 - Quotes name selected for renaming.](../media/5-12-rename.png)](../media/5-12-rename.png#lightbox)

## Exercise 4: Use Power Query to unpivot - Quotes

In this exercise, you will use Power Query transformations to structure the quotes data for Power Pivot.

### Task 1: Use First Row as Headers transformation button

In this task, you will move the first row with the column header values to the table header.

On the **Home** menu, select the **Use First Row as Headers** button.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Home tab showing the Use First Row as Headers button selected.](../media/5-13-use-first-row.png)](../media/5-13-use-first-row.png#lightbox)

### Task 2: Use the Unpivot transformation menu option

In this task, you will unpivot the Quotes data.

1. In the **Preview** pane, right-click the **CustID** column to display the menu options.

1. Select the **Unpivot Other Columns** option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the CustID column and the Unpivot Other Columns option highlighted for selection.](../media/5-14-unpivot.png)](../media/5-14-unpivot.png#lightbox)

1. Double-click the **Attribute** column to rename it to **QuoteDate**.

1. Double-click the **Value** column to rename it to **QuoteAmt**.

    The following screenshot shows an example of how the column headers appear before they're renamed.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the CustID, Attribute, and Values column headers before they're renamed.](../media/5-15-before.png)](../media/5-15-before.png#lightbox)

    The following screenshot shows an example of how the column headers appear after you have renamed them.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Attribute and Value columns renamed to QuoteDate and QuoteAmt.](../media/5-16-after.png)](../media/5-16-after.png#lightbox)

## Exercise 5: Use Power Query to clean - quotes

In this exercise, you will use Power Query transformations to clean the quotes data.

### Task 1: Use the Replace transformation

In this task, you will use a replace technique to change the **QuoteDate** to a full date that can be converted to a **Date** data type.

1. In the **Preview** window, right-click the **QuoteDate** column to display menu options.

1. Select the **Replace Values** option.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the QuoteDate column highlighting the Replace Values menu option.](../media/5-17-replace.png)](../media/5-17-replace.png#lightbox)

1. In the **Replace Values** window, complete the following steps:

    1. Enter a dash (**-**) in the **Value To Find** text box.

    1. Enter **/1/** in the **Replace With** text box.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Replace Values window showing entries in the Value To Find and the Replace With text boxes.](../media/5-18-replace-values.png)](../media/5-18-replace-values.png#lightbox)

    1. Select the **OK** button.

### Task 2: Use the data type icon

In this task, you will use the data type icon to change the data type from **Text** to **Date**.

1. Select the **ABC** icon, which indicates that the column is a **Text** data type.

1. Select the **Date** data type option from the data type menu options.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the QuoteDate data format icon selected with the Date data type highlighted.](../media/5-19-data-type.png)](../media/5-19-data-type.png#lightbox)

### Task 3: Close and load to the data model

In this task, you will load the Customers and Quotes tables to the data model.

1. From the **Home** menu, select **Close & Load > Close & Load To**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Close & Load button selected and the Close & Load To option highlighted.](../media/5-20-close-load-to.png)](../media/5-20-close-load-to.png#lightbox)

1. On the **Import Data** window, select the **Only Create Connection** option and then select the **Add this data to the Data Model** checkbox.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Import Data window displaying the Only Create Connection button and the Add this data to the Data Model checkbox selected.](../media/5-21-only-connection.png)](../media/5-21-only-connection.png#lightbox)

1. Select the **OK** button.

    > [!NOTE]
    > The loaded tables will be displayed in the **Queries & Connections** pane with total number of rows loaded.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queries & Connections pane displaying the Customers query with 7,560 rows loaded and the Quotes query with 84,307 rows loaded.](../media/5-22-queries.png)](../media/5-22-queries.png#lightbox)

    > [!NOTE]
    > At the point, you have connected to the data sources by using Power Query and have selected the checkbox option to **Add this data to the Data Model**. However, you have not actually observed where this data has been loaded to. In Lab 02A, you will use Power BI Desktop to import the Power Query connections, Customer table, and Quote table to create the data model.

### Task 4: Save the file

In this task, you will save the Excel file with the **Customers** and **Quotes** query connections.

1. From the main Excel ribbon, select **File > Save**.

1. Go to the **D:\data-cleaning\AttendeeLab MaterialsLab 01** folder and then save the file as **MAIAD Lab 01 - My Solution.xlsx**.



In this lab, you used Power Query in Excel to connect to CSV and XLSX source data files, created a new column by using the **Column from Examples** transformation, unpivoted and applied transformations in Power Query, loaded source data to a data model, and then saved the Excel file with the data connections.

> [!div class="mx-imgBorder"]
> [![Screenshot of the final results in Excel showing the Customers and Quotes queries.](../media/5-23-final.png)](../media/5-23-final.png#lightbox)
