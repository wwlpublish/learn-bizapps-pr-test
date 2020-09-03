## Opening an Excel File and Creating an Instance

The first thing that is required to Automate any Excel related task is to create an Excel instance. 

An instance determines which session of an application WinAutomation interacts with. Instances can be created either by opening a locally stored or new Excel file, or attaching the Process to an already open file. These operations are achieved by the **Launch Excel** Action or **Attach to Running Excel** respectively.

Opening a new Excel file is done by the **Launch Excel** Action, by selecting to Launch Excel **with a blank document**.
 

![launch excel action properties](..\media\launch-excel-action-properties.png)
 

Alternatively, Launching Excel with an existing file is done by changing the **Launch Excel** setting to **open the following document** and entering a **Document Path**.


![launch excel action properties continued](..\media\launch-excel-action-properties-continued.png)


If **Make Instance Visible** is checked, the Excel window will be opened during process execution. If the instance isn’t visible, it runs in the background.
In the **Advanced** tab, there is an option to **Load Add-Ins and Macros**, as the Excel file is launched.
 

![launch excel properties advanced tab](..\media\launch-excel-properties-advanced-tab.png)


An already opened Excel file can be used as an instance with the **Attach to Running Excel** Action. The **Document Name** will have to be specified.
 

![attach to running excel action properties](..\media\attach-to-running-excel-action-properties.png)


## Saving and Closing

An Excel file can be saved and closed only if the instance has already been determined. To save an Excel file, the **Save Excel** Action can be used. 

Set Save Mode to **Save document** to save the document in its current path with its current filename, or to **Save document as** to save the document in a different path and/or under a different filename.
 

![save excel action properties](..\media\save-excel-action-properties.png)


When choosing **Save document as**, there will be additional options to change the Document Format, and provide the new **Document Path**.
  

![save excel action properties continued](..\media\save-excel-action-properties-continued.png)


The **Close Excel** Action is used to close a specific instance of Excel. Additional options are available in case the file must also be saved.

 If any option to save the document is chosen, the Action functions similarly to the Save Excel Action, in addition to closing the document.
  

![close excel action properties](..\media\close-excel-action-properties.png)


## Reading from an Excel Document

Using the **Read from Excel Worksheet** Action, we may read and extract data from an Excel Document. 

After specifying an instance of Excel, specify the range of data you would like to read. Set **Retrieve** to **Single Cell’s Value** to retrieve the contents of a single cell, specifying the location of the cell with the column and row.


![read from excel action properties](..\media\read-from-excel-action-properties.png)


Alternatively, set the option **Values from a Range of Cells** to extract an entire table of data, defined by the coordinates its first top left and bottom right cells. The output of this will be a DataTable type variable.
  

![read from excel action properties continued](..\media\read-from-excel-action-properties-continued.png)


Please note that the Column can be specified either by its letter, or its corresponding number. e.g. for cell E8 you can enter column E, row 8 or column 5, row 8.
The last option, **Values from selection**, retrieves the values of the currently selected cells.

Cell contents are stored in variables based on their type. e.g., A date will be stored as a datetime variable. To store all data as text, set **Get Cell Contents as Text** in the **Advanced** tab.
  

![read from excel properties advanced tab](..\media\read-from-excel-properties-advanced-tab.png)
 

The **Get First Free Column/Row from Excel Worksheet** Action is useful to determine the size of the data in the Excel document when we want to select rows and columns dynamically, and the number of rows and columns is unknown.

The numbers of the first free row and column are stored as variables, and can be referenced when specifying the range of information that is to be extracted with the Read from Excel Worksheet Action.
  

![get first free row column excel action properties](..\media\get-first-free-row-column-excel-action-properties.png)


To select all the data in an Excel Worksheet, specify the range to start at column 1, row 1, and end at column **%FirstFreeColumn-1%** and row **%FirstFreeRow-1%**.
  

![read from excel action properties example](..\media\read-from-excel-action-properties-example.png)


## Writing to an Excel Worksheet

The Write to Excel Worksheet Action can write any static data or variable to a specified cell in an Excel document. 

If a datatable is to be set to be written, the specified cell in the Action will be the first (top left) cell of the table, and the remaining cells corresponding cells will be overwritten. Write Mode can also be set to **On Currently Active Cell**, as well.
  

![write to excel action properties](..\media\write-to-excel-action-properties.png)


## Additional Actions and Features

We can use the **Get First Free Row on Column** Action, when we want to write data to the first available cell in a given column.
  

![get first free row on column excel action properties](..\media\get-first-free-row-on-column-excel-action-properties.png)


The Read and Write Actions can use the currently selected cell as a point of reference. The **Get Selected Cell Range from Excel Worksheet** Action is used for this purpose. It provides the indexes of the first and last column and row of the selection.
  

![get selected cell range excel action properties](..\media\get-selected-cell-range-excel-action-properties.png)


To change the selected cells, use the **Select Cells in Excel Worksheet** Action. Set **Select** to **Range of Cells** to select cells by specifying the top left and bottom right corner cells of the selection.


![select cells in excel action properties](..\media\select-cells-in-excel-action-properties.png)


Alternatively, set **Select** to **Range of Cells Relatively to Active Cell** to select a number of cells from the currently selected cell.
  

![select cells in excel action properties continued](..\media\select-cells-in-excel-action-properties-continued.png)


To activate a particular cell, use the **Activate Cell in Excel Worksheet** Action. In the **Activate** field, you can either choose to specify a cell by its coordinates (**Absolutely specified Cell**) or relative to the currently Active cell (**Relatively specified Cell**).
  

![activate cell in excel action properties](..\media\activate-cell-in-excel-action-properties.png)


It is also possible to insert and delete columns and rows, by using the appropriate Actions. Specifying a column or row index will be required. In case of insertion, the row or column will be added before the one which is specified.
  

![insert row to excel action properties](..\media\insert-row-to-excel-action-properties.png)


## Managing Worksheets

If the Excel document has multiple worksheets, we may need to use the **Set Active Excel Worksheet** Action, if the Worksheet opened by default is not the one we require. The Worksheet can be specified either by name or index.
  

![set active excel worksheet action properties](..\media\set-active-excel-worksheet-action-properties.png)


To get the names of all the Worksheets in a document, use the **Get Excel Worksheets** Action. The output will be a list with all the worksheets in the Excel document.
  

![get all excel worksheets action properties](..\media\get-all-excel-worksheets-action-properties.png)


The **Get Active Excel Worksheet** Action retrieves both the name and index of the currently active worksheet.
  

![get active excel worksheet action properties](..\media\get-active-excel-worksheet-action-properties.png)


Worksheets can also be added, renamed and deleted, using the appropriate Actions. You will need to provide the name of the Worksheet, and the Excel instance.