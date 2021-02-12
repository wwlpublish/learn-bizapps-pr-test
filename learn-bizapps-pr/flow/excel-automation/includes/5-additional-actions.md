You can use the **Get First Free Row on Column from Excel Worksheet** action when you want to write data to the first available cell in a given column.

![Screenshot of Properties of 'Get First Free Row On Column from Excel Worksheet' action dialog with output set.](..\media\get-first-free-row-on-column-excel-action-properties.png)

The **Read** and **Write** actions can use the currently selected cell as a point of reference. The **Get Selected Cell Range from Excel Worksheet** action is used for this purpose by providing the indexes of the first and last column and row of the selection.

![Screenshot of Properties of 'Get Select Cell Range from Excel Worksheet' action dialog with output properties set.](..\media\get-selected-cell-range-excel-action-properties.png)

To change the selected cells, use the **Select Cells in Excel Worksheet** action. Set the **Select** option to **Range of Cells** to select cells by specifying the upper-left and bottom-right corner cells.

![Screenshot of Properties of 'Select Cells in Excel Worksheet' action with Select set to Range of Cells, and with Range Starts and Ends highlighted.](..\media\select-cells-in-excel-action-properties.png)

Alternatively, you can set the **Select** option to **Range of Cells Relatively to Active Cell** to select a number of cells from the currently selected cell.

![The same dialog with Select set to "Range of Cells Relatively to Active Cell," and with range X Axis Direction and Number of Cells highlighted.](..\media\select-cells-in-excel-action-properties-continued.png)

To activate a particular cell, use the **Activate Cell in Excel Worksheet** action. In the **Activate** field, you can either choose to specify a cell by its coordinates (**Absolutely specified Cell**) or relative to the currently active cell (**Relatively specified Cell**).

![Screenshot of Properties of 'Activate Cell in Excel Worksheet' action dialog with Activate set to Absolutely specified Cell.](..\media\activate-cell-in-excel-action-properties.png)

It is also possible to insert and delete columns and rows by using the appropriate actions; however, you are required to specify a column or row index. In case of insertion, the row or column will be added before the one that is specified.

![Screenshot of Properties of 'Insert Row to Excel Worksheet' action dialog.](..\media\insert-row-to-excel-action-properties.png)
