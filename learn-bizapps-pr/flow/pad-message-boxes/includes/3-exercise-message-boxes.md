In attended automation, interaction between the user and workstation is necessary; message boxes provide a direct means for this communication to take place.

In this exercise, you will develop an attended flow, which receives real-time input from the user, and provides useful information as output while running.

1. Start by prompting the user to select an Excel file. Use a **Display Select File Dialog** action.
 
   ![display select file dialog properties exercise](..\media\display-select-file-dialog-properties-exercise.png)

1. To read all the data in the Excel file, first retrieve the range of the data within.
 
   ![exercise workspace](..\media\exercise-workspace.png)

1. Then, read the data in the designated range.
 
   ![read from excel worksheet properties exercise](..\media\read-from-excel-worksheet-properties-exercise.png)

1. Add a **For Each** action to iterate through the data.
 
   ![for each properties exercise](..\media\for-each-properties-exercise.png)

1. To check the contents of the **Gross Sales** column (column G), first convert them into a number, and add an **If** action to check whether it exceeds 100000.
 
   ![convert text to number properties exercise](..\media\convert-text-to-number-properties-exercise.png)

   ![exercise workspace continued](..\media\exercise-workspace-continued.png)

1. In case the value exceeds 100000, the user should decide whether to add a discount. Use the **Display Message** action to provide the necessary information to the user, and prompt them to choose using **Yes**/**No** buttons.
 
   ![display message properties exercise](..\media\display-message-properties-exercise.png)

1. Add another **If** action, to check which button was pressed.
 
   ![if properties exercise](..\media\if-properties-exercise.png)

1. If the user selects **Yes**, a window will prompt them to enter the discount amount; use the **Display Input Dialog** action to achieve this.
 
   ![display input dialog properties exercise](..\media\display-input-dialog-properties-exercise.png)

1. Finally, write the discount amount into Excel.
 
    ![write to excel worksheet properties exercise](..\media\write-to-excel-worksheet-properties-exercise.png)

1. Run the flow.
 
    ![final exercise workspace](..\media\final-exercise-workspace.png)

This way, the user interacts with the flow seamlessly throughout the entire task. 