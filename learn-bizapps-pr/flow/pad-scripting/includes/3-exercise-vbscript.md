In this exercise, you'll create a flow that calculates how many overtime hours employees have worked. Consider that a typical working day is eight hours.

> [!NOTE]
> Before creating the flow, download the [**Employees.xlsx**](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/raw/master/power-automate-desktop/Employees.zip) file that is required for this exercise. Select **Download** on the right side of the page and extract the downloaded file to your local computer.

1. Launch Power Automate Desktop console and create a new flow named **Overtime calculator**.

    ![Screenshot of the Power Automate Build a flow dialog.](..\media\first-exercise-new-flow.png)

1. Add a **Launch Excel** action to the workspace and configure it to launch the **Employees.xlsx** file.

    ![Screenshot of the Power Automate Launch Excel action.](..\media\first-exercise-launch-excel-action.png)

1. Use the **Get first free column/row from Excel worksheet** action to find the first free row in the file.

    ![Screenshot of the Power Automate Get first free column/row from Excel worksheet action.](..\media\first-exercise-get-first-free-column-row-from-excel-worksheet-action.png)

1. Deploy a **Loop** and set it to iterate from the second row to the last populated row of the file. The first row contains the titles, so it isn't needed in this process.

    ![Screenshot of the Power Automate Loop action.](..\media\first-exercise-loop-action.png)

1. Inside the loop, use a **Read from Excel worksheet** action to read the cell that contains the current employee's total working hours.

    ![Screenshot of the Power Automate Read from Excel worksheet action.](..\media\first-exercise-read-from-excel-worksheet-action.png)

1. Deploy a **Run VBScript** action. In the **VBScript to run** field, populate the code shown in the following image. This code uses the modulo operator to calculate the rest of the operation as **total working hours / 8**.

    ![Screenshot of the Power Automate Run VBScript action.](..\media\first-exercise-run-vbscript-action.png)

1. The return value of the **Run VBScript** action is a text value. Use a **Convert text to number** action to convert it to a number.

    ![Screenshot of the Power Automate Convert text to number action.](..\media\first-exercise-convert-text-to-number-action.png)

1. Use a **Write to Excel worksheet** action to write the numerical value in the current row's third cell.

    ![Screenshot of the Power Automate Write to Excel worksheet action.](..\media\first-exercise-write-to-excel-worksheet-action.png)

1. Outside the loop, add a **Close Excel** action to save and close the file.

    ![Screenshot of the Power Automate Close Excel action.](..\media\first-exercise-close-excel-action.png)

1. Save the flow and then run it to test that every action works as expected.

    ![Screenshot of the Power Automate final flow and the save and run button.](..\media\first-exercise-final-flow.png)
