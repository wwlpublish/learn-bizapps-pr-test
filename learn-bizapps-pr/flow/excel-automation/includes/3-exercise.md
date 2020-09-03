This Process will demonstrate some Actions used to organize data in a spreadsheet. We will create a process, which will:
* Attach to an open excel file
* Switch the positions of two columns
* Add a header to each column

## Attach to Running Excel
To begin, download and open the Customers.xlsx file. Create a new Process, and add the Action **Attach to Running Excel**. Specify the name of the file in the Action properties (**Customers.xlsx**).
  
![attach to running excel exercise](..\media\attach-to-running-excel-exercise.png)


The Excel document contains a list of customers. Each customer has a first name, a last name, an address, a state, and a city. 
 
## Insert Header Row
First, to insert a row with headers, use the **Insert Row to Excel Worksheet** Action, specifying the Row Index. To add a row at the top, set **Row Index** to **1**. 
  
![insert row to excel exercise](..\media\insert-row-to-excel-exercise.png)

 
## Write Headers to First Row
Then, add five **Write to Excel Worksheet** Actions, one for each column (or header). In the properties of the first of these Actions, set **Value to Write** to **First Name**, and set the column to A. 
  
![write to excel exercise](..\media\write-to-excel-exercise.png)


The rest of the Write to Excel Actions should be configured as follows:
* Last Name—column B
* Address—column C
* State—column D
* City—column E

 
## Get First Free Row on State Column
Next, to switch the positions of the last two columns, so that **State** appears after **City**, use the **Get First Free Row on Column from Excel Worksheet** Action. This will retrieve the index of the first available row in the column of your choice. Since you will be moving the **State** column, select column **D**.
  
  
![get first free row on column excel exercise](..\media\get-first-free-row-on-column-excel-exercise.png)


## Copy Cells
To copy the cells, use the **Copy Cells From Excel Worksheet** Action. In the **Copy Mode** options, select **Values from a Range of Cells**, starting the range at column **D**, row **1**, and ending the range at column **D**, row **%FirstFreeRowOnColumn-1%**. This way, the entire column is dynamically selected without having to calculate its length.
  

![copy cells from excel exercise](..\media\copy-cells-from-excel-exercise.png)


## Paste Cells
Paste the cells using **Paste Cells to Excel Worksheet** and select column **F**, row **1**. This will paste the cells in the clipboard into the specified cell.
  

![paste cells to excel exercise](..\media\paste-cells-to-excel-exercise.png)


## Delete Blank Column
To delete the blank column, we use **Delete Column from Excel Worksheet** and select column **D**.
  

![delete column from excel exercise](..\media\delete-column-from-excel-exercise.png)

 
Save and Quit
To save and quit, add the **Close Excel** Action, and choose to save the document before closing.
  
![close excel exercise](..\media\close-excel-exercise.png)


The completed process should look like this:
  

![excel exercise workspace](..\media\excel-exercise-workspace.png)


## Running the Process
Execute the process, to see that a new row is inserted, to which the headers are written, and the last two columns switch positions. The file is then saved and closed.