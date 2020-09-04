Using the **Read from Excel Worksheet** Action, we may read and extract data from an Excel Document. 

After specifying an instance of Excel, specify the range of data you would like to read. Set **Retrieve** to **Single Cell’s Value** to retrieve the contents of a single cell, specifying the location of the cell with the column and row.


![read from excel action properties](..\media\read-from-excel-action-properties.png)


Alternatively, set the option **Values from a Range of Cells** to extract an entire table of data, defined by the coordinates its first top left and bottom-right cells. The output of this will be a DataTable type variable.
  

![read from excel action properties continued](..\media\read-from-excel-action-properties-continued.png)


The Column can be specified either by its letter, or its corresponding number. For example, for cell E8 you can enter column E, row 8 or column 5, row 8.
The last option, **Values from selection**, retrieves the values of the currently selected cells.

Cell contents are stored in variables based on their type. For example, A date will be stored as a datetime variable. To store all data as text, set **Get Cell Contents as Text** in the **Advanced** tab.
  

![read from excel properties advanced tab](..\media\read-from-excel-properties-advanced-tab.png)
 

The **Get First Free Column/Row from Excel Worksheet** Action is useful to determine the size of the data in the Excel document when we want to select rows and columns dynamically, and the number of rows and columns is unknown.

The numbers of the first free row and column are stored as variables, and can be referenced when specifying the range of information that is to be extracted with the Read from Excel Worksheet Action.
  

![get first free row column excel action properties](..\media\get-first-free-row-column-excel-action-properties.png)


To select all the data in an Excel Worksheet, specify the range to start at column 1, row 1, and end at column **%FirstFreeColumn-1%** and row **%FirstFreeRow-1%**.
  

![read from excel action properties example](..\media\read-from-excel-action-properties-example.png)