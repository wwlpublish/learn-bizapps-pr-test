In attended automation, interaction between the user and workstation is necessary; message boxes provide a direct means for this communication to take place.

In this exercise, you will develop an attended Process, which receives real-time input from the user, and provides useful information as output during its execution.
## Step 1
Use a **Display Select File Dialog** Action to prompt the user to select an Excel file:
 
![display select file dialog properties exercise](..\media\display-select-file-dialog-properties-exercise.png)

## Step 2
Open the selected file in Excel, and retrieve the range of the data within:
 
![exercise workspace](..\media\exercise-workspace.png)

## Step 3
Read the data in the Excel file:
 
![read from excel worksheet properties exercise](..\media\read-from-excel-worksheet-properties-exercise.png)

## Step 4
Add a **For Each** Action to iterate through the data:
 
![for each properties exercise](..\media\for-each-properties-exercise.png)

## Step 5
Within the loop, use a **Display Notification** Action to display the ID number of each row; this is located in the first column of the file:
 
![display notification properties exercise](..\media\display-notification-properties-exercise.png)

## Step 6
Convert the contents of the **Gross Sales** column (column G) into a number, and add an **If** Action to check whether it exceeds 100000:
 
![convert text to number properties exercise](..\media\convert-text-to-number-properties-exercise.png)

 
![exercise workspace continued](..\media\exercise-workspace-continued.png)

## Step 7
In case the value exceeds 100000, the user should decide whether to add a discount. Use the **Display Message** Action to provide the necessary information to the user, and prompt them to choose using **Yes**/**No** buttons:
 
![display message properties exercise](..\media\display-message-properties-exercise.png)

## Step 8
Add another **If** Action, to check which button was pressed:
 
![if properties exercise](..\media\if-properties-exercise.png)

## Step 9
If the user selects **Yes**, a window will prompt them to enter the discount amount; use the **Display Input Dialog** Action to achieve this:
 
![display input dialog properties exercise](..\media\display-input-dialog-properties-exercise.png)

## Step 10
Finally, write the discount amount into Excel:
 
![write to excel worksheet properties exercise](..\media\write-to-excel-worksheet-properties-exercise.png)

## Step 11
Run the Process:
 
![final exercise workspace](..\media\final-exercise-workspace.png)

The Notification Window provides information on the current row being processed while the loop is being executed, and the user interacts with the Process seamlessly throughout the entire task. 
