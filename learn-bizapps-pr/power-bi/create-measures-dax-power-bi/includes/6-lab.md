**The estimated time to complete the lab is 45 minutes**

In this lab you will create calculated tables, calculated columns, and simple measures using Data Analysis Expressions (DAX).

In this lab you learn how to:

- Create calculated tables

- Create calculated columns

- Create measures

### Lab story

This lab is one of many in a series of labs that was designed as a complete story from data preparation to publication as reports and dashboards. You can complete the labs in any order. However, if you intend to work through multiple labs, for the first 10 labs, we suggest you do them in the following order:

1. [Prepare data in Power BI Desktop](https://docs.microsoft.com/learn/modules/get-data/lab-prepare/?azure-portal=true)

1. [Load data in Power BI Desktop](https://docs.microsoft.com/learn/modules/clean-data-power-bi/8-lab/?azure-portal=true)

1. [Model data in Power BI Desktop, part 1](https://docs.microsoft.com/learn/modules/design-model-power-bi/8-lab/?azure-portal=true)

1. [Model data in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/design-model-power-bi/9-lab/?azure-portal=true)

1. **Create DAX calculations in Power BI Desktop, Part 1** << You are here. This is the lab for the current module.

1. [Create DAX calculations in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/create-measures-dax-power-bi/8-lab/?azure-portal=true)

1. [Design a report in Power BI Desktop, part 1](https://docs.microsoft.com/learn/modules/visuals-power-bi/8-lab/?azure-portal=true)

1. [Design a report in Power BI Desktop, part 2](https://docs.microsoft.com/learn/modules/data-driven-story-power-bi/13-lab/?azure-portal=true)

1. [Create a Power BI dashboard](https://docs.microsoft.com/learn/modules/create-dashboards-power-bi/9-lab/?azure-portal=true)

1. [Perform data analysis in Power BI Desktop](https://docs.microsoft.com/learn/modules/ai-visuals-power-bi/5-lab/?azure-portal=true)

1. [Create a Power BI paginated report](https://docs.microsoft.com/learn/modules/create-paginated-reports-power-bi/6-lab/?azure-portal=true)

> [!NOTE]
> Each lab starts with a PBIX file that has all of the previous lab work completed. If you should lose your work for any reason, you can open the PBIX file that includes the progress up to that point from the folder indicated at the beginning of the next lab.

## Exercise 1: Create Calculated Tables

In this exercise you will create two calculated tables. The first will be the **Salesperson** table, to allow a direct relationship between it and the **Sales** table. The second will be the **Date** table.

### Task 1: Get started

In this task you'll set up the environment for the lab.

> [!IMPORTANT]
> If you are continuing on from the previous lab (and you completed that lab successfully), do not complete this task. Instead, continue from the next task.

1. To open the Power BI Desktop, on the taskbar, select the Microsoft Power BI Desktop shortcut.

1. To close the getting started window, at the top-left of the window, select **X**.

1. To open the starter Power BI Desktop file, select the **File** ribbon tab to open the backstage view.

1. Select **Open Report**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the File menu expanded with the Open report option highlighted.](../media/lab-6-5-ssm.png)](../media/lab-6-5-ssm.png#lightbox)

1. Select **Browse Reports**.

1. In the **Open** window, navigate to the **D:\DA100\Labs\create-dax-calculations-in-power-bi-desktop\Starter** folder.

1. Select the **Sales Analysis** file.

1. Select **Open**.

1. Close any informational windows that may open.

1. To create a copy of the file, select the **File** ribbon tab to open the backstage view.

1. Select **Save As**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the File menu expanded with the Save as option highlighted.](../media/lab-6-5-a-ssm.png)](../media/lab-6-5-a-ssm.png#lightbox)

1. If prompted to apply changes, select **Apply**.

1. In the **Save As** window, navigate to the **D:\DA100\MySolution** folder.

1. Select **Save**.

### Task 2: Create the Salesperson table

In this task, you'll create the **Salesperson** table (direct relationship to **Sales**).

1. In Power BI Desktop, in Report view, on the **Modeling** ribbon, from inside the **Calculations** group, select **New Table**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Table feature in the Modeling ribbon.](../media/lab-6-1-ssm.png)](../media/lab-6-1-ssm.png#lightbox)

1. In the formula bar (which opens directly beneath the ribbon when creating or editing calculations), type **Salesperson =**, press **Shift+Enter**, type **'Salesperson (Performance)'**, and then press **Enter**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the formula entered in the formula bar.](../media/lab-6-2-ssm.png)](../media/lab-6-2-ssm.png#lightbox)

    For your convenience, all DAX definitions in this lab can be copied from the **D:\DA100\Labs\create-dax-calculations-in-power-bi-desktop\Assets\Snippets.txt** file.

    A calculated table is created by first entering the table name, followed by the equals symbol (=), followed by a DAX formula that returns a table. Note that the table name cannot already exist in the data model.

    The formula bar supports entering a valid DAX formula. It includes features like auto-complete, Intellisense and color-coding, enabling you to quickly and accurately enter the formula.

    This table definition creates a copy of the **Salesperson (Performance)** table. It copies the data only, however properties like visibility, formatting, etc. are not copied.

    > [!TIP]
    > You are encouraged to enter “white space” (such as carriage returns and tabs) to lay out formulas in an intuitive and easy-to-read format, especially when formulas are long and complex. To enter a carriage return, press **Shift+Enter**. White space is optional.

1. In the **Fields** pane, notice that the table icon is a shade of blue (denoting a calculated table).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the table icon shaded blue.](../media/lab-6-3-ssm.png)](../media/lab-6-3-ssm.png#lightbox)

    Calculated tables are defined by using a DAX formula which returns a table. It is important to understand that calculated tables increase the size of the data model because they materialize and store values. They're recomputed whenever formula dependencies are refreshed, as will be the case in this data model when new (future) date values are loaded into tables.

    Unlike Power Query-sourced tables, calculated tables cannot be used to load data from external data sources. They can only transform data based on what has already been loaded into the data model.

1. Switch to Model view.

1. Notice that the **Salesperson** table is available (take care, it might be hidden from view—scroll horizontally to locate it).

1. Create a relationship from the **Salesperson | EmployeeKey** column to the **Sales | EmployeeKey** column.

1. Right-click the inactive relationship between the **Salesperson (Performance)** and **Sales** tables, and then select **Delete**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the delete inactive relationship button.](../media/lab-6-4-ssm.png)](../media/lab-6-4-ssm.png#lightbox)

1. When prompted to confirm the deletion, select **Delete**.

1. In the Salesperson table, multi-select the following columns, and then hide them:

    - EmployeeID

    - EmployeeKey

    - UPN

1. In the diagram, select the **Salesperson** table.

1. In the **Properties** pane, in the **Description** box, enter: **Salesperson related to a sale**.

    Descriptions appear as tooltips in the **Fields** pane when the user hovers their cursor over a table or field.

1. For the **Salesperson (Performance)** table, set the description to: **Salesperson related to region(s)**.

    The data model now provides two alternatives when analyzing salespeople. The **Salesperson** table allows you to analyze sales made by a salesperson, while the **Salesperson (Performance)** table allows you to analyze sales made in the sales region(s) assigned to the salesperson.

### Task 2: Create the Date table

In this task, you will create the **Date** table.

1. Switch to Data view.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the switch to data view icon.](../media/lab-6-6-ssm.png)](../media/lab-6-6-ssm.png#lightbox)

1. On the **Home** ribbon tab, from inside the **Calculations** group, select **New Table**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New table feature on the Home ribbon.](../media/lab-6-7-ssm.png)](../media/lab-6-7-ssm.png#lightbox)

1. In the formula bar, enter the following, and then press Enter:

    ```DAX
    Date =  
    ‎CALENDARAUTO(6)
    ```

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the formula entered on the formula bar.](../media/lab-6-8-ss.png)](../media/lab-6-8-ss.png#lightbox)

    The CALENDARAUTO() function returns a single-column table consisting of date values. The “auto” behavior scans all data model date columns to determine the earliest and latest date values stored in the data model. It then creates one row for each date within this range, extending the range in either direction to ensure a full year of data is stored.

    This function can take a single optional argument which is the last month number of a year. When omitted, the value is 12, meaning that December is the last month of the year. In this case 6 is entered, meaning that June is the last month of the year.

1. Notice the column of date values.

    If the column does not appear, in the **Fields** pane, select a different table, and then select the **Date** table.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the date table in the Fields pane.](../media/lab-6-9-ss.png)](../media/lab-6-9-ss.png#lightbox)

    The dates shown are formatted using US regional settings (mm/dd/yyyy).

1. At the bottom-left corner, in the status bar, notice the table statistics, confirming that 1826 rows of data have been generated, which represents five full years’ data.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the 1826 rows of data generated message.](../media/lab-6-10-ss.png)](../media/lab-6-10-ss.png#lightbox)

### Task 4: Create calculated columns

In this task, you will add additional columns to enable filtering and grouping by different time periods. You will also create a calculated column to control the sort order of other columns.

1. On the **Table Tools** contextual ribbon, from inside the **Calculations** group, select **New Column**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New column feature on the Table tools ribbon.](../media/lab-6-11-ssm.png)](../media/lab-6-11-ssm.png#lightbox)

1. In the formula bar, type the following, and then press **Enter**.

    ```DAX
    Year =

    "FY" & YEAR('Date'[Date]) + IF(MONTH('Date'[Date]) > 6, 1)
    ```

    A calculated column is created by first entering the column name, followed by the equals symbol (=), followed by a DAX formula that returns a single-value result. The column name cannot already exist in the table.

    The formula uses the date’s year value but adds one to the year value when the month is after June. This is how fiscal years at Adventure Works are calculated.

1. Verify that the new column was added.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Year column added.](../media/lab-6-12-ssm.png)](../media/lab-6-12-ssm.png#lightbox)

1. Use the snippets file definitions to create the following two calculated columns for the **Date** table:

    - Quarter
    - Month

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the quarter and month columns.](../media/lab-6-13-ssm.png)](../media/lab-6-13-ssm.png#lightbox)

1. To validate the calculations, switch to Report view.

1. To create a new report page, at the bottom-left, select the plus icon.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the create new report page button.](../media/lab-6-14-ssm.png)](../media/lab-6-14-ssm.png#lightbox)

1. To add a matrix visual to the new report page, in the **Visualizations** pane, select the matrix visual type.

    > [!TIP]
    > You can hover the cursor over each icon to reveal a tooltip describing the visual type.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of an icon on the Visualizations tab.](../media/lab-6-15-ssm.png)](../media/lab-6-15-ssm.png#lightbox)

1. In the **Fields** pane, from inside the **Date** table, drag the **Year** field into the **Rows** well.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the year to rows drag action.](../media/lab-6-16-ssm.png)](../media/lab-6-16-ssm.png#lightbox)

1. Drag the **Month** field into the **Rows** well, directly beneath the **Year** field.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the month in rows directly below year.](../media/lab-6-17-ssm.png)](../media/lab-6-17-ssm.png#lightbox)

1. Next to the matrix visual, select the forked-double arrow icon (which will expand all years down one level).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the forked double arrow to expand all years down one level.](../media/lab-6-18-ssm.png)](../media/lab-6-18-ssm.png#lightbox)

1. Notice that the years expand to months, and that the months are sorted alphabetically rather than chronologically.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the months sorted alphabetically.](../media/lab-6-19-ss.png)](../media/lab-6-19-ss.png#lightbox)

    By default, text values sort alphabetically, numbers sort from smallest to largest, and dates sort from earliest to latest.

1. To customize the **Month** field sort order, switch to Data view.

1. Add the **MonthKey** column to the **Date** table.

    ```DAX
    MonthKey =

    (YEAR('Date'[Date]) * 100) + MONTH('Date'[Date])
    ```

    This formula computes a numeric value for each year and month combination.

1. In Data view, verify that the new column contains numeric values (e.g. 201707 for July 2017, etc.).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the MonthKey column containing numeric values.](../media/lab-6-20-ssm.png)](../media/lab-6-20-ssm.png#lightbox)

1. Switch back to Report view.

1. In the **Fields** pane, ensure that the **Month** field is selected (when selected, it will have a dark gray background).

1. On the **Column Tools** contextual ribbon, from inside the **Sort** group, select **Sort by Column**, and then select **MonthKey**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Sort by Column with MonthKey selected.](../media/lab-6-21-ssm.png)](../media/lab-6-21-ssm.png#lightbox)

1. In the matrix visual, notice that the months are now chronologically sorted.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the months chronologically sorted.](../media/lab-6-22-ss.png)](../media/lab-6-22-ss.png#lightbox)

### Task 5: Complete the Date table

In this task, you will complete the design of the **Date** table by hiding a column and creating a hierarchy. You will then create relationships to the **Sales** and **Targets** tables.

1. Switch to Model view.

1. In the **Date** table, hide the **MonthKey** column.

1. In the **Date** table, create a hierarchy named **Fiscal**, with the following three levels:

    - Year
    - Quarter
    - Month

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Date table with year, quarter, month levels.](../media/lab-6-23-ssm.png)](../media/lab-6-23-ssm.png#lightbox)

1. Create the follow two model relationships:

    - **Date | Date** to **Sales | OrderDate**
    - **Date | Date** to **Targets | TargetMonth**

1. Hide the following two columns:

    - Sales | OrderDate
    - Targets | TargetMonth

### Task 6: Mark the Date table

In this task, you will mark the **Date** table as a date table.

1. Switch to Report view.

1. In the **Fields** pane, select the **Date** table (not the **Date** field).

1. On the **Table Tools** contextual ribbon, from inside the **Calendars** group, select **Mark as Date Table**, and then select **Mark as Date Table**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Mark as Data Table option.](../media/lab-6-24-ssm.png)](../media/lab-6-24-ssm.png#lightbox)

1. In the **Mark as Date Table** window, in the **Date Column** dropdown list, select **Date**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Date column field.](../media/lab-6-25-ssm.png)](../media/lab-6-25-ssm.png#lightbox)

1. Select **OK**.

1. Save the Power BI Desktop file.

    Power BI Desktop now understands that this table defines dates (time). This is important when relying on time intelligence calculations. You’ll work with time intelligence calculations in the **Create DAX calculations in Power BI Desktop, Part 2** lab.

    > [!NOTE]
    > This design approach for a date table is suitable when you don’t have a date table in your data source. If you have access to a data warehouse, it would be appropriate to load date data from its date dimension table rather than “redefining” date logic in your data model.

## Exercise 2: Create Measures

In this exercise, you'll create and format several measures.

### Task 1: Create simple measures

In this task, you will create simple measures. Simple measures aggregate a single column or table.

1. In Report view, on **Page 2**, in the **Fields** pane, drag the **Sales | Unit Price** field into the **Values** section in matrix visual.

    The labs use a shorthand notation to reference a field. It will look like this: **Sales | Unit Price**. In this example, **Sales** is the table name and **Unit Price** is the field name.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Unit Price on the matrix visual.](../media/lab-6-27-ss.png)](../media/lab-6-27-ss.png#lightbox)

    In the **Model data in Power BI Desktop, Part 2** lab, you set the **Unit Price** column to summarize by **Average**. The result you see in the matrix visual is the monthly average unit price (sum of unit price values divided by the count of unit prices).

1. In the visual fields pane (located beneath the **Visualizations** pane), in the **Values** well, notice that **Unit Price** is listed.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Unit Price listed in the Values well.](../media/lab-6-28-ssm.png)](../media/lab-6-28-ssm.png#lightbox)

1. Select the down-arrow for **Unit Price**, and then notice the available menu options.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the available menu options for Unit price.](../media/lab-6-29-ssm.png)](../media/lab-6-29-ssm.png#lightbox)

    Visible numeric columns allow report authors to decide at report design time how a column will summarize (or not). This can result in inappropriate reporting. Some data modelers don't like leaving things to chance, however, and choose to hide these columns and instead expose aggregation logic defined by measures. This is the approach you will now take in this lab.

1. To create a measure, in the **Fields** pane, right-click the **Sales** table, and then select **New Measure**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Measure feature in the Sales table.](../media/lab-6-30-ssm.png)](../media/lab-6-30-ssm.png#lightbox)

1. In the formula bar, add the following measure definition:

    ```DAX
    Avg Price = AVERAGE(Sales[Unit Price])
    ```

1. Add the **Avg Price** measure to the **Values** section in the matrix visual.

1. Notice that it produces the same result as the **Unit Price** column (but with different formatting).

1. In the **Values** well, open the context menu for the **Avg Price** field, and notice that it is not possible to change the aggregation technique.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the context menu for the Average Price field.](../media/lab-6-31-ssm.png)](../media/lab-6-31-ssm.png#lightbox)

1. Use the snippets file definitions to create the following five measures for the **Sales** table:

    - Median Price
    - Min Price
    - Max Price
    - Orders
    - Order Lines

    The DISTINCTCOUNT() function used in the **Orders** measure will count orders only once (ignoring duplicates). The COUNTROWS() function used in the **Order Lines** measure operates over a table.

    In this case, the number of orders is calculated by counting the distinct **SalesOrderNumber** column values, while the number of order lines is the number of table rows (each row is a line of an order).

1. Switch to Model view, and then multi-select the four price measures: **Avg Price**, **Max Price**, **Median Price**, and **Min Price**.

1. For the multi-selection of measures, configure the following requirements:

    - Set the format to two decimal places
    - Assign to a display folder named **Pricing**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Pricing folder with Average Price, Maximum Price, Median Price, and Minimum Price.](../media/lab-6-32-ssm.png)](../media/lab-6-32-ssm.png#lightbox)

1. Hide the **Unit Price** column.

    The **Unit Price** column is now unavailable to report authors. They must use the measure you’ve added to the model. This design approach ensures that report authors won’t inappropriately aggregate prices, for example, by summing them.

1. Multi-select the **Orders** and **Order Lines** measures, and configure the following requirements:

    - Set the format use the thousands separator
    - Assign to a display folder named **Counts**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Counts folder with Order lines and Orders.](../media/lab-6-33-ssm.png)](../media/lab-6-33-ssm.png#lightbox)

1. In Report view, in the **Values** well of the matrix visual, for the **Unit Price** field, select **X** to remove it.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the X to remove the Unit Price field.](../media/lab-6-34-ssm.png)](../media/lab-6-34-ssm.png#lightbox)

1. Increase the size of the matrix visual to fill the page width and height.

1. Add the following five new measures to the matrix visual:

    - Median Price
    - Min Price
    - Max Price
    - Orders
    - Order Lines

1. Verify that the results looks sensible and are correctly formatted.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the results correctly formatted.](../media/lab-6-35-ss.png)](../media/lab-6-35-ss.png#lightbox)

### Task 2: Create additional measures

In this task, you will create additional measures that use more complex expressions.

1. In Report view, select **Page 1**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Page 1 report view.](../media/lab-6-36-ssm.png)](../media/lab-6-36-ssm.png#lightbox)

1. Review the table visual, noticing the total for the **Target** column.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Total Target column value.](../media/lab-6-37-ssm.png)](../media/lab-6-37-ssm.png#lightbox)

    In a previous lab we learned that there’s a many-to-many relationship between salespeople and regions. Summing the target values together doesn’t make sense because salespeople targets are set for each salesperson based on their sales region assignments. A target value should only be shown when a single salesperson is filtered. You will implement a measure now to do just that.

1. Select the table visual, and then in the **Visualizations** pane,  remove the **Target** field.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the X to remove the Target field.](../media/lab-6-38-ssm.png)](../media/lab-6-38-ssm.png#lightbox)

1. Rename the **Targets | Target** column as **Targets | TargetAmount**.

    > [!TIP]
    > There are several ways to rename the column in Report view:
    >
    > - In the **Fields** pane, you can right-click the column and then select **Rename**
    > - Double-click the column
    > - Select it and press **F2**

    You’re about to create a measure named **Target**. It’s not possible to have a column and measure in the same table, with the same name.

1. Create the following measure on the **Targets** table:

    ```DAX
    Target =

    IF(

    HASONEVALUE('Salesperson (Performance)'[Salesperson]),

    SUM(Targets[TargetAmount])
    
    )
    ```

    The HASONEVALUE() function tests whether a single value in the **Salesperson** column is filtered. When true, the expression returns the sum of target amounts (for just that salesperson). When false, BLANK is returned.

1. Format the **Target** measure for zero decimal places.

    > [!TIP]
    > You can use the **Measure Tools** contextual ribbon.

1. Hide the **TargetAmount** column.

   > [!TIP]
   > You can right-click the column in the **Fields** pane, and then select **Hide**.

1. Add the **Target** measure to the table visual.

1. Notice that the **Target** column total is now BLANK.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Target total with a blank value.](../media/lab-6-39-ssm.png)](../media/lab-6-39-ssm.png#lightbox)

1. Use the snippets file definitions to create the following two measures for the **Targets** table:

    - Variance
    - Variance Margin

1. Format the **Variance** measure for zero decimal places.

1. Format the **Variance Margin** measure as percentage with two decimal places.

1. Add the **Variance** and **Variance Margin** measures to the table visual.

1. Resize the table visual so you can see all columns and rows.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the widened table so all values are displayed.](../media/lab-6-40-ss.png)](../media/lab-6-40-ss.png#lightbox)

    While it appears that the salespeople are not meeting their targets, remember that the table visual isn’t yet filtered by a specific time period. You’ll produce sales performance reports that filter by a user-selected time period in the **Design a report in Power BI Desktop, Part 1** lab.

1. At the top-right corner of the **Fields** pane, collapse and then expand to open the pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the expand Fields pane icon.](../media/lab-6-41-ssm.png)](../media/lab-6-41-ssm.png#lightbox)

    Collapsing and re-opening the pane resets the content.

1. Notice that the **Targets** table now appears at the top of the list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Targets table at the top of the list.](../media/lab-6-42-ssm.png)](../media/lab-6-42-ssm.png#lightbox)

    Tables that comprise only visible measures are automatically listed at the top of the list.

### Finish up

In this task, you will complete the lab.

1. Save the Power BI Desktop file.

1. If you intend to start the next lab, you can opt to leave Power BI Desktop open.

    > [!WARNING]
    > If you leave the lab open, it will time out after one to four hours. Your work in the *current* module's lab will be lost, but each lab after the first one includes a PBIX file with the work from all previous labs completed so that you don't need to start over.

You’ll enhance the data model with more advanced calculations using DAX in the **Create DAX calculations in Power BI Desktop, Part 2** lab.

[!INCLUDE [](../../../includes/power-bi-lab-end.md)]
