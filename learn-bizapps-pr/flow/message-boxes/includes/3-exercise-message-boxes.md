In attended automation, interaction between the user and workstation is necessary; message boxes provide a direct means for this communication to take place.

In this exercise, you will develop an attended process, which receives real-time input from the user, and provides useful information as output while running.

1. Use a **Display Select File Dialog** action to prompt the user to select an Excel file.

   ![Screenshot of Properties of 'Display Select File Dialog' action dialog.](..\media\display-select-file-dialog-properties-exercise.png)

2. Open the selected file in Excel, and retrieve the range of the data within.

   ![Screenshot of exercise workspace for opening Excel and getting first free column and row.](..\media\exercise-workspace.png)

3. Read the data in the Excel file.

   ![Screenshot of Properties of 'Read from Excel Worksheet' action dialog.](..\media\read-from-excel-worksheet-properties-exercise.png)

4. Add a **For Each** action to iterate through the data.

   ![Screenshot of Properties of 'For Each' action dialog.](..\media\for-each-properties-exercise.png)

5. Within the loop, use a **Display Notification** action to display the ID number of each row; this is located in the first column of the file.

   ![Screenshot of Properties of 'Display Notification' action dialog.](..\media\display-notification-properties-exercise.png)

6. Convert the contents of the **Gross Sales** column (column G) into a number, and add an **If** action to check whether it exceeds 100000.

   ![Screenshot of Properties of 'Convert Text to Number' action dialog.](..\media\convert-text-to-number-properties-exercise.png)

   ![Screenshot of exercise workspace with the For Each loop added.](..\media\exercise-workspace-continued.png)

7. In case the value exceeds 100000, the user should decide whether to add a discount. Use the **Display Message** action to provide the necessary information to the user, and prompt them to choose using **Yes**/**No** buttons.

   ![Screenshot of Properties of 'Display Message' action dialog.](..\media\display-message-properties-exercise.png)

8. Add another **If** action, to check which button was pressed.

   ![Screenshot of Properties of 'If' action dialog.](..\media\if-properties-exercise.png)

9. If the user selects **Yes**, a window will prompt them to enter the discount amount; use the **Display Input Dialog** action to achieve this.

   ![Screenshot of Properties of 'Display Input Dialog' action dialog.](..\media\display-input-dialog-properties-exercise.png)

10. Finally, write the discount amount into Excel.

    ![Screenshot of Properties of 'Write to Excel Worksheet' action dialog.](..\media\write-to-excel-worksheet-properties-exercise.png)

11. Run the process.

    ![Screenshot of the completed exercise workspace.](..\media\final-exercise-workspace.png)

The Notification Window provides information on the current row being processed while the loop is running, and the user interacts with the process seamlessly throughout the entire task.
