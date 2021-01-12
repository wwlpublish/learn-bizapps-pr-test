Reading an Excel document retrieves the data from the document, allowing it to be processed and modified in flows.

Read and extract data from an Excel document with the **Read from Excel Worksheet** action. 

Select the excel instance and specify the range of data to read. Set the **Retrieve** option to **Single Cell’s Value** to retrieve the contents of a single cell, and then specify the **Cell Location** with the **Column** and **Row** properties.


![read from excel action properties](..\media\read-from-excel-action-properties.png)


To extract a table of data, set **Retrieve** to the **Values from a range of cells** option. Define the table by the coordinates in the **Start column/row** and **End column/row** properties. Specify the column by its letter or corresponding number. For example, you can enter **column E, row 8** or **column 5, row 8** for cell E8. This output will be of a **Datatable** type variable.
  

<!--![read from excel action properties continued](..\media\read-from-excel-action-properties-continued.png)
-->



Variables store cell contents based on their type. For example, a date is stored as a **Datetime** variable. To store all data as text, select the **Get cell contents as text** option. When selecting to read values from a range of cells, select **First line of range contains column names** to ignore the first row. To ignore the type of data in the cell and retrieve the contents as text, select **Get Cell Contents as Text**. Change these properties in the **Advanced** section.
  


![read from excel properties advanced section](..\media\read-from-excel-properties-advanced-tab.png)

Alternatively, select cells in the document to which the instance is assigned. The last option, **Values from Selection**, will retrieve the values of the currently selected cells.

Determine the size of the data in the Excel document with the **Get First Free Column/Row from Excel Worksheet** action. This action helps select the appropriate cells dynamically if the number of rows and columns is unknown.

The numbers of the first free row and column are stored as variables. For example, reference them when specifying the range of information that is to be extracted with the **Read from Excel worksheet** action.
  

![get first free row column excel action properties](..\media\get-first-free-row-column-excel-action-properties.png)


To select all data in an Excel worksheet, specify the range to start at column 1, row 1. Then specify **Column** as **%FirstFreeColumn-1%** and **Row** as **%FirstFreeRow-1%**.
  

![read from excel action properties example](..\media\read-from-excel-action-properties-example.png)
