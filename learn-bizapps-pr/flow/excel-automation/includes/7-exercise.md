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

1. Specify the name of the file in the **Action** properties (**Customers.xlsx**).

   ![Screenshot of Properties of 'Attach To Running Excel' action dialog with Document Name set to Customers dot X L S X.](..\media\attach-to-running-excel-exercise.png)

The Excel document contains a list of customers. Each customer has a first name, a last name, an address, a state, and a city.

1. Insert a row with headers by using the **Insert Row to Excel Worksheet** action, specifying the **Row Index**. To add a row at the top of the worksheet, set the **Row Index** property to **1**.
  
   ![Screenshot of Properties of 'Insert Row To Excel Worksheet' action dialog with Row Index set to 1 and highlighted.](..\media\insert-row-to-excel-exercise.png)

1. Add five **Write to Excel Worksheet** actions, one for each column (or header). In the properties of the first of these actions, set **Value to Write** to **First Name**, and then set the **Column** property to **A**.

![Properties of 'Write To Excel Worksheet' action with "Value to Write" set to First Name an "Write Value Into Cell At" set to Column A and Row 1.](..\media\write-to-excel-exercise.png)

The rest of the **Write to Excel Worksheet** actions should be configured as follows:

- **Last Name** — Column B
- **Address** — Column C
- **State** — Column D
- **City** — Column E

### Switch positions of two columns

Next, to switch the positions of the last two columns so that **State** appears after **City**, follow these steps:

1. Select the **Get First Free Row on Column from Excel Worksheet** action, which will retrieve the index of the first available row in the column of your choice.

1. Because you will be moving the **State** column, select column **D**.
  
    ![Screenshot of Properties of 'Get First Free Row On Column from Excel Worksheet' action dialog with Column set to D and highlighted.](..\media\get-first-free-row-on-column-excel-exercise.png)

### Copy and paste cells

To copy the cells, follow these steps:

1. Select the **Copy Cells From Excel Worksheet** action.

1. In the **Copy Mode** options, select **Values from a Range of Cells**.

1. In the **Range Starts At** property, set **Column** to **D** and then set **Row** to **1**.

1. In the **Range Starts At** property, set **Column** to **D** and then set **Row** to **%FirstFreeRowOnColumn-1%** so that the entire column is dynamically selected without you having to calculate its length.

    ![Screenshot of Properties of 'Copy Cells from Excel Worksheet' action dialog with Copy Mode set to Values from a Range of Cells and highlighted.](..\media\copy-cells-from-excel-exercise.png)

To paste cells, follow these steps:

1. Select the **Paste Cells to Excel Worksheet** action.

1. Set the **Column** property to **F** and the **Row** property to **1**. This setting will paste the cells in the clipboard into the specified cell.

    ![Screenshot of Properties of 'Paste Cells To Excel Worksheet' action with Cell Location set to Column F and Row 1 and highlighted.](..\media\paste-cells-to-excel-exercise.png)

### Delete a blank column

To delete the blank column, select the **Delete Column from Excel Worksheet** action and then set the **Column** property to **D**.
  
![Screenshot of Properties of 'Delete Column from Excel Worksheet' action dialog with Delete Column set to D and highlighted.](..\media\delete-column-from-excel-exercise.png)

Save and quit the file by adding the **Close Excel** action and then selecting to save the document before closing.
  
![Screenshot of Properties of 'Close Excel' action dialog with Before Closing Excel set to Save document and highlighted.](..\media\close-excel-exercise.png)

The completed process should look like the following screenshot.

![The completed process on the Main tab as described below.](..\media\excel-exercise-workspace.png)

```c
Attach To Running Excel
Attach to Excel Document with Name Customers.xlsx

Insert Row to Excel Worksheet
Insert a row above row No: 1 of the Excel document whose Instance is stored into %ExcelInstance%

Write to Excel Worksheet
Write the value First Name into cell in column A and row 1 of the Excel Instance stored into %ExcelInstance%

Write to Excel Worksheet
Write the value Last Name into cell in column B and row 1 of the Excel Instance stored into %ExcelInstance%

Write to Excel Worksheet
Write the value Address into cell in column C and row 1 of the Excel Instance stored into %ExcelInstance%

Write to Excel Worksheet
Write the value State into cell in column D and row 1 of the Excel Instance stored into %ExcelInstance%

Write to Excel Worksheet
Write the value City into cell in column E and row 1 of the Excel Instance stored into %ExcelInstance%

Get First Free Row On Column from Excel Worksheet
Get the first free row, given the column in the active worksheet of the Excel document whose Instance is stored into %ExcelInstance%

Copy Cells from Excel Worksheet
Copy the cells within a range from column D row 1 to column D row %FirstFreeRowOnColumn-1%

Paste Cells to Excel Worksheet
Paste copied cells on cell in column F and row 1

Delete Column from Excel Worksheet
Delete column D from the Excel document whose Instance is stored into %ExcelInstance%

Close Excel
Close the Excel document and close the Excel Instance stored into %ExcelInstance%
```

## Run the process

Run the process to see that a new row has been inserted, the headers have been written, and the last two columns have switched positions. When you are satisfied with the results, save and close the file.
