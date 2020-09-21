This exercise shows how you can use certain actions to organize data in an Excel spreadsheet. 

## Tasks

In this exercise, you will:

- Attach to an open Excel file and add a header to each column.
- Switch the positions of two columns.
- Copy and paste cells.
- Delete a blank column.
- Run the process to verify successful completion.


### Attach to an Excel file and add headers

To begin, download and open the **Customers.xlsx** file. Then, follow these steps to attach to this running Excel file: 

1. Create a new process and then add the **Attach to Running Excel** action. 

2. Specify the name of the file in the **Action** properties (**Customers.xlsx**).


![attach to running excel exercise](..\media\attach-to-running-excel-exercise.png)


The Excel document contains a list of customers. Each customer has a first name, a last name, an address, a state, and a city. 

3. Insert a row with headers by using the **Insert Row to Excel Worksheet** action, specifying the **Row Index**. To add a row at the top of the worksheet, set the **Row Index** property to **1**. 

  
![insert row to excel exercise](..\media\insert-row-to-excel-exercise.png)

 
5. Add five **Write to Excel Worksheet** actions, one for each column (or header). In the properties of the first of these actions, set **Value to Write** to **First Name**, and then set the **Column** property to **A**. 
  
![write to excel exercise](..\media\write-to-excel-exercise.png)


The rest of the **Write to Excel Worksheet** actions should be configured as follows:

- **Last Name** — Column B
- **Address** — Column C
- **State** — Column D
- **City** — Column E

 
### Switch positions of two columns

Next, to switch the positions of the last two columns so that **State** appears after **City**, follow these steps:

1. Select the **Get First Free Row on Column from Excel Worksheet** action, which will retrieve the index of the first available row in the column of your choice. 

2. Because you will be moving the **State** column, select column **D**.
  
  
![get first free row on column excel exercise](..\media\get-first-free-row-on-column-excel-exercise.png)


### Copy and paste cells

To copy the cells, follow these steps:

1. Select the **Copy Cells From Excel Worksheet** action. 

2. In the **Copy Mode** options, select **Values from a Range of Cells**. 

3. In the **Range Starts At** property, set **Column** to **D** and then set **Row** to **1**. 

4. In the **Range Starts At** property, set **Column** to **D** and then set **Row** to **%FirstFreeRowOnColumn-1%** so that the entire column is dynamically selected without you having to calculate its length.
  

![copy cells from excel exercise](..\media\copy-cells-from-excel-exercise.png)


To paste cells, follow these steps:

1. Select the **Paste Cells to Excel Worksheet** action. 

2. Set the **Column** property to **F** and the **Row** property to **1**. This setting will paste the cells in the clipboard into the specified cell.
  

![paste cells to excel exercise](..\media\paste-cells-to-excel-exercise.png)


### Delete a blank column
To delete the blank column, select the **Delete Column from Excel Worksheet** action and then set the **Column** property to **D**.
  

![delete column from excel exercise](..\media\delete-column-from-excel-exercise.png)

 
Save and quit the file by adding the **Close Excel** action and then selecting to save the document before closing.
  
![close excel exercise](..\media\close-excel-exercise.png)


The completed process should look like the following screenshot.
  

![excel exercise workspace](..\media\excel-exercise-workspace.png)


## Run the process
Run the process to see that a new row has been inserted, the headers have been written, and the last two columns have switched positions. When you are satisfied with the results, save and close the file.
