In this exercise, you will create a process that prompts users to enter basic information of new clients and then register them into an Excel file.

1. Launch WinAutomation and create a new process named **User Registration**.

    ![Screenshot of the Create New Process button and window.](..\media\create-new-process-button-and-window-exercise.png)

1. Deploy a **Display Input Dialog** action and populate the **Input Dialog Message** field with a message asking for the user's name.

    ![Screenshot of the populated input fields in the Display Input Dialog action's properties dialog.](..\media\display-input-dialog-action-properties-input-exercise.png)

1. Rename the **Store Users Input into** output variable to a more descriptive name, such as **NameInput**.

    ![Screenshot of the populated output field in the Display Input Dialog action's properties dialog.](..\media\display-input-dialog-action-properties-output-exercise.png)

1. Repeat the last two steps 3 more times for the last name, the phone number and the country code, respectively.

    ![All the deployed actions in the workspace.](..\media\workspace-exercise.png)

1. Add a **Set Variable** action to join the name and the last name into a new variable called **FullName**.

    ![Screenshot of the NameInput and LastNameInput fields in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-full-name-exercise.png)

1. Repeat step 5, to join the country code and the phone number into a variable called **FullPhoneNumber**.

    ![Screenshot of the CountryCodeInput and PhoneNumber fields in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-full-phone-number-exercise.png)

    Because both variables have been created through a **Display Input Dialog** action, they are texts and not numbers. If the variables were numbers, the action above would have performed addition and not string concatenation.

    ![Screenshot of the created variables in the Variables Pane.](..\media\variables-pane-exercise.png)

1. Add a **Launch Excel** action to open the Excel file containing the clients' information.

    ![Screenshot of the populated fields in the Launch Excel action's properties dialog.](..\media\launch-excel-action-properties-exercise.png)

    The file must contain two columns, one for the users' full name and one for the phone number.

    ![Screenshot of the Excel file with two columns.](..\media\excel-columns-exercise.png)

1. Use the created instance as an input for a **Get First Free Column/Row from Excel Worksheet** action.

    ![Screenshot of the populated fields in the Get First Free Column/Row from Excel Worksheet action's properties dialog.](..\media\get-first-free-column-row-from-excel-worksheet-action-properties.png)

1. Deploy a **Write to Excel Worksheet** action and populate the fields with the following values:

    - The **Excel Instance** field with the respective Excel instance variable.
    - The **Value to Write** field with the **FullName** variable
    - The **Column** field with the value 1.
    - The **Row** field with the **FirstFreeRow** variable.

    ![Screenshot of the FullName field in the Write to Excel Worksheet action's properties dialog.](..\media\write-to-excel-worksheet-action-properties-full-name-exercise.png)

1. Repeat step 9, populating the **Value to Write** field with the **FullPhoneNumber** variable and the **Column** field with the Value two.

    ![Screenshot of the FullPhoneNumber field in the Write to Excel Worksheet action's properties dialog.](..\media\write-to-excel-worksheet-action-properties-full-phone-exercise.png)

1. Lastly, add a **Close Excel** action to save and close the launched Excel worksheet.

    ![Screenshot of the populated fields in the Close Excel action's properties dialog.](..\media\close-excel-action-properties.png)

1. Now, the process must be the same as the image below. Click on the **Run** button to test it.

    ![Screenshot of the Run button in the Process Designer.](..\media\process-designer-run-button-exercise.png)
