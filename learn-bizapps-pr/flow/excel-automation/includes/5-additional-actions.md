You can use the **Get First Free Row on Column from Excel Worksheet** action when you want to write data to the first available cell in a given column.
  

![get first free row on column excel action properties](..\media\get-first-free-row-on-column-excel-action-properties.png)


The **Read** and **Write** actions can use the currently selected cell as a point of reference. The **Get Selected Cell Range from Excel Worksheet** action is used for this purpose by providing the indexes of the first and last column and row of the selection.
  

![get selected cell range excel action properties](..\media\get-selected-cell-range-excel-action-properties.png)


To change the selected cells, use the **Select Cells in Excel Worksheet** action. Set the **Select** option to **Range of Cells** to select cells by specifying the upper-left and bottom-right corner cells.


![select cells in excel action properties](..\media\select-cells-in-excel-action-properties.png)


Alternatively, you can set the **Select** option to **Range of Cells Relatively to Active Cell** to select a number of cells from the currently selected cell.
  

![select cells in excel action properties continued](..\media\select-cells-in-excel-action-properties-continued.png)


To activate a particular cell, use the **Activate Cell in Excel Worksheet** action. In the **Activate** field, you can either choose to specify a cell by its coordinates (**Absolutely specified Cell**) or relative to the currently active cell (**Relatively specified Cell**).
  

![activate cell in excel action properties](..\media\activate-cell-in-excel-action-properties.png)


It is also possible to insert and delete columns and rows by using the appropriate actions; however, you are required to specify a column or row index. In case of insertion, the row or column will be added before the one that is specified.
  

![insert row to excel action properties](..\media\insert-row-to-excel-action-properties.png)
