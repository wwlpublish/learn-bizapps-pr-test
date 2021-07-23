Reading an Excel document retrieves the data from the document, allowing it to be processed and modified in flows.

Read and extract data from an Excel document with the **Read from Excel Worksheet** action.

Select the Excel instance and specify the range of data to read. Set the **Retrieve** option to **The value of a single cell** to retrieve the contents of a single cell, and then specify the cell location with the **Column** and **Row** properties.

![Screenshot of Read from Excel worksheet action properties dialog.](..\media\read-from-excel-action-properties.png)

To extract a table of data, set **Retrieve** to the **Values from a range of cells** option. Define the table by the coordinates in the **Start column/row** and **End column/row** properties. Specify the column by its letter or corresponding number. For example, you can enter **column E, row 8** or **column 5, row 8** for cell E8. This output will be of a **datatable** type variable.

Variables store cell contents based on their type. For example, a date is stored as a **datetime** variable. To store all data as text, select the **Get cell contents as text** option. When selecting to read values from a range of cells, select **First line of range contains column names** to ignore the first row. To ignore the type of data in the cell and retrieve the contents as text, select **Get cell contents as text**. Change these properties in the **Advanced** section.

![Screenshot of Read from Excel worksheet properties advanced section.](..\media\read-from-excel-properties-advanced-tab.png)

Alternatively, select cells in the document to which the instance is assigned. The last option, **Values from selection**, will retrieve the values of the currently selected cells.

Determine the size of the data in the Excel document with the **Get first free column/row from Excel worksheet** action. This action helps select the appropriate cells dynamically if the number of rows and columns is unknown.

The numbers of the first free row and column are stored as variables. For example, reference them when specifying the range of information that is to be extracted with the **Read from Excel worksheet** action.

![Screenshot of Get first free column and row from Excel worksheet action properties dialog.](..\media\get-first-free-row-column-excel-action-properties.png)

To select all data in an Excel worksheet, specify the range to start at column 1, row 1. Then specify **End column** as **%FirstFreeColumn-1%** and **End row** as **%FirstFreeRow-1%**.

![Screenshot of Read from Excel worksheet action properties dialog completed.](..\media\read-from-excel-action-properties-example.png)
