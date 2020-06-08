## Overview

The estimated time to complete the lab is 45 minutes

In this lab, you commence the development of a Power BI Desktop solution
for the Adventure Works company. It involves connecting to source data,
previewing the data, and using data preview techniques to understand the
characteristics and quality of the source data.

In this lab, you learn how to:

  - Open Power BI Desktop
  - Set Power BI Desktop options
  - Connect to source data
  - Preview source data
  - Use data preview techniques to better understand the data

## Prepare Data

In this exercise, you will create eight Power BI Desktop queries. Six
queries will source data from SQL Server, and two from CSV files.

### Save the Power BI Desktop file

In this task, you will first save the Power BI Desktop file.

1.  Open Power BI Desktop. Click the **File** ribbon tab to open the backstage view.

2.  Select **Save**.

3.  In the **Save As** window, navigate to the **D:\\DA100\\MySolution**
    folder.

4.  In the **File Name** box, enter **Sales Analysis**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the file name box](../media/lab-002.png)](../media/2-file-types-c.png#lightbox)

5.  Click **Save**.

> [!TIP]
> You can also save the file by click the **Save** icon located at
the top-right.

### Set Power BI Desktop options

In this task, you will set Power BI Desktop options.

6.  In Power BI Desktop, click the **File** ribbon tab to open the
    backstage view.

7.  At the left, select **Options and Settings**, and then select
    **Options**.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of Options and Settings](../media/lab-005.png)](../media/2-file-types-c.png#lightbox)

8.  In the **Options** window, at the left, in the **Current File**
    group, select **Data Load**.

   The **Data Load** settings for the current file allow setting options that determine default behaviors when modeling.

9.  In the **Relationships** group, uncheck the two options that are checked.

   > [!div class="mx-imgBorder"]
   > [![Screenshot of the Relationships options](../media/lab-007.png)](../media/2-file-types-c.png#lightbox)

   While these two options can be helpful when developing a data model, they have been disabled to support the lab experience. When you create relationships in **Lab 03A**, you will learn why you are adding each one.

10. Click **OK**.

11. Save the Power BI Desktop file.

### Get data from SQL Server

In this task, you will create queries based on SQL Server tables.

12. On the **Home** ribbon tab, from inside the **Data** group, click
    **SQL Server**.

13. In the **SQL Server Database** window, in the **Server** box, enter
    **localhost**.

   In the labs, you will connect to the SQL Server database by using **localhost**. This isn’t a recommended practice, however, when creating your own solutions. It’s because gateway data sources cannot resolve **localhost**.

14. Click **OK**.

15. Notice that the default authentication is to
    **Use My Current Credentials**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the authentication window](../media/lab-012.png)](../media/2-file-types-c.png#lightbox)

16. Click **Connect**.

17. When prompted about encryption support, click **OK**.

18. In the **Navigator** window, at the left, expand the **AdventureWorksDW2020** database.

   The **AdventureWorksDW2020** database is based on the **AdventureWorksDW2017** sample database. It has been modified to support the learning objectives of the course labs.

19. Select but don’t check the **DimEmployee** table.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the DimEmployee option](../media/lab-016.png)](../media/2-file-types-c.png#lightbox)

20. In the right pane, notice a preview of the table.

   The preview allows you to determine the columns and a sample of rows.

21. To create queries, check the following six tables:

<!-- end list -->

  - DimEmployee
  - DimEmployeeSalesTerritory
  - DimProduct
  - DimReseller
  - DimSalesTerritory
  - FactResellerSales

<!-- end list -->

22. To apply transformations to the data of the selected tables, click
    **Transform Data**.

   You won’t be transforming the data in this lab. The objectives of this lab are to explore and profile the data in the **Power Query Editor** window.

### Preview SQL Server queries

In this task, you will preview the data of the SQL Server queries. First, you will learn relevant information about the data. You will also use column quality, column distribution, and column profile tools to understand the data, and assess data quality.

23. In the **Power Query Editor** window, at the left, notice the **Queries** pane.

   The **Queries** pane contains one query for each selected table.

24. Select the first query **DimEmployee**.

   The **DimEmployee** table stores one row for each employee. A subset of the rows represent the salespeople, which will be relevant to the model you’ll develop.

25. At the bottom left, in the status bar, notice the table statistics - the table has 33 columns, and 296 rows.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the status bar](../media/lab-020.png)](../media/2-file-types-c.png#lightbox)

26. In the data preview pane, scroll horizontally to review all columns.

27. Notice that the last five columns contain **Table** or **Value**
    links.

   These five columns represent relationships to other tables in the database. They can be used to join tables together. You will join tables in **Lab 03A**.

28. To assess column quality, on the **View** ribbon tab, from inside
    the **Data Preview** group, check **Column Quality**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the View ribbon tab](../media/lab-021.png)](../media/2-file-types-c.png#lightbox)

   Column quality allows you to easily determine the percentage of valid, error, or empty values.

29. For the **Position** column (sixth last column), notice that 94% of
    rows are empty (null).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the position column](../media/lab-022.png)](../media/2-file-types-c.png#lightbox)

30. To assess column distribution, on the **View** ribbon tab, from
    inside the **Data Preview** group, check **Column Distribution**.

31. Review the **Position** column again, and notice that there are four distinct values, and one unique value.

32. Review the column distribution for the **EmployeeKey** (first)
    column—there are 296 distinct values, and 296 unique values.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the column distribution](../media/lab-024.png)](../media/2-file-types-c.png#lightbox)

   When the distinct and unique counts are the same, it means the column contains unique values. When modeling, it’s important that some tables contain unique columns. They will be used to create one-to-many relationships.

33. In the **Queries** pane, select the **DimEmployeeSalesTerritory** query.

   The **DimEmployeeSalesTerritory** table stores one row for each employee and the sales territory regions they manage. The table supports relating many regions to a single employee. Some employees manage one, two, or possibly more regions. When you model this data, you will need to define a many-to-many relationship.

34. In the **Queries** pane, select the **DimProduct** query.

   The **DimProduct** table contains one row per product sold by the company.

35. Horizontally scroll to reveal the last columns.

36. Notice the **DimProductSubcategory** column.

   If you were to add transformations to this query, you would use the **DimProductSubcategory** column to join tables.

37. In the **Queries** pane, select the **DimReseller** query.

   The **DimReseller** table contains one row per reseller. Resellers sell, distribute, or value add Adventure Works’ products.

38. To view column values, on the **View** ribbon tab, from inside the **Data Preview** group, check **Column Profile**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of column values](../media/lab-028.png)](../media/2-file-types-c.png#lightbox)

39. Select the **BusinessType** column header.

40. Notice that a new pane opens beneath the data preview pane.

41. Review the column statistics and value distribution.

42. Notice the data quality issue: there are two labels for warehouse
    (**Warehouse**, and the misspelled **Ware House**).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of value distribution with two labels: Warehouse and Ware House](../media/lab-029.png)](../media/2-file-types-c.png#lightbox)

43. Hover the cursor over the **Ware House** bar, and notice that there are five rows with this value.

44. In the **Queries** pane, select the **DimSalesTerritory** query.

   The **DimSalesTerritory** table contains one row per sales region, including **Corporate HQ** (headquarters). Regions are assigned to a country, and countries are assigned to groups.

45. In the **Queries** pane, select the **FactResellerSales** query.

   The **FactResellerSales** table contains one row per sales order line - a sales order contains one or more line items.

46. Review the column quality for the **TotalProductCost** column, and
    notice that 8% of the rows are empty.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the column quality](../media/lab-032.png)](../media/2-file-types-c.png#lightbox)

   Missing **TotalProductCost** column values is a data quality issue. To address the issue, you would apply transformations to fill in missing values by using the product standard cost, which is stored in the **DimProduct** table.

### Get data from a CSV file

In this task, you will create a query based on a CSV file.

47. To add a new query, in the **Power Query Editor** window, on the
    **Home** ribbon tab, from inside the **New Query** group, click the
    **New Source** down-arrow, and then select **Text/CSV**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Source button on the Home ribbon](../media/lab-033.png)](../media/2-file-types-c.png#lightbox)

48. In the **Open** window, navigate to the **D:\\DA100\\Data** folder,
    and select the **ResellerSalesTargets.csv** file.

49. Click **Open**.

50. In the **ResellerSalesTargets.csv** window, notice the data preview.

51. Click **OK**.

52. In the **Queries** pane, notice the addition of the
    **ResellerSalesTargets** query.

   The **ResellerSalesTargets** CSV file contains one row per salesperson, per year. Each row records 12 monthly sales targets (expressed in thousands). The business year for the Adventure Works company commences on July 1.

53. Notice that no columns contain empty values.

   When there isn’t a monthly sales target, a hyphen character is stored instead.

54. Review the icons in each column header, to the left of the column
    name.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the icon in the column headers](../media/lab-036.png)](../media/2-file-types-c.png#lightbox)

   The icons represent the column data type. **123** is whole number, and **ABC** is text.


### Get additional data from a CSV file

In this task, you will create an additional query based on a different
CSV file.

55. Use the steps in the previous task to create a query based on the
    **D:\\DA100\\Data**\\**ColorFormats.csv** file.

   The **ColorFormats** CSV file contains one row per product color. Each row records the HEX codes to format background and font colors. 

### Finish up

In this task, you will complete the lab.

56. On the **View** ribbon tab, from inside the **Data Preview** group,
    uncheck the three data preview options:

<!-- end list -->

  - Column quality
  - Column distribution
  - Column profile

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the data preview options](../media/lab-038.png)](../media/2-file-types-c.png#lightbox)

57. To save the Power BI Desktop file, on the **File** backstage view, select **Save**.

58. When prompted to apply the queries, click **Apply Later**.

   Applying the queries will load their data to the data model. You’re not ready to do that, as there are many transformations that must be applied first.

59. Leave Power BI Desktop open.

