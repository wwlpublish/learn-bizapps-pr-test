In attended automation, interaction between the user and workstation is necessary; message boxes provide a direct means for this communication to take place.

In this exercise, you will develop an attended flow, which receives real-time input from the user, and provides useful information as output while running.

To begin, download [**Orders.zip**](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/blob/master/power-automate-desktop/Orders.zip). Select **Download** on the right. Extract the Excel file to your local computer.

1. Start by prompting the user to select an Excel file. Use a **Display Select File Dialog** action.

   ![Screenshot of the display select file dialog properties dialog.](..\media\display-select-file-dialog-properties-exercise.png)

1. To read all the data in the Excel file, first retrieve the range of the data within.

   ![Screenshot of the exercise workspace with Get first free column and row.](..\media\exercise-workspace.png)

1. Then, read the data in the designated range.

   ![Screenshot of the Read from Excel worksheet properties dialog.](..\media\read-from-excel-worksheet-properties-exercise.png)

1. Add a **For Each** action to iterate through the data.

   ![Screenshot of the For each properties dialog.](..\media\for-each-properties-exercise.png)

1. To check the contents of the **Gross Sales** column (column G), first convert them into a number, and add an **If** action to check whether it exceeds 100000.

   ![Screenshot of the Convert text to number properties dialog.](..\media\convert-text-to-number-properties-exercise.png)

   ![Screenshot of the exercise workspace with For each added.](..\media\exercise-workspace-continued.png)

1. In case the value exceeds 100000, the user should decide whether to add a discount. Use the **Display Message** action to provide the necessary information to the user, and prompt them to choose using **Yes**/**No** buttons.

   ![Screenshot of the Display message properties dialog.](..\media\display-message-properties-exercise.png)

1. Add another **If** action, to check which button was pressed.

   ![Screenshot of the If properties dialog.](..\media\if-properties-exercise.png)

1. If the user selects **Yes**, a window will prompt them to enter the discount amount; use the **Display Input Dialog** action to achieve this.

   ![Screenshot of the Display input dialog properties dialog.](..\media\display-input-dialog-properties-exercise.png)

1. Finally, write the discount amount into Excel.

    ![Screenshot of the Write to Excel worksheet properties dialog.](..\media\write-to-excel-worksheet-properties-exercise.png)

1. Run the flow. When prompted, select the **Orders.xlsx** file.

    ![Screenshot of the completed exercise workspace.](..\media\final-exercise-workspace.png)

This way, the user interacts with the flow seamlessly throughout the entire task.
