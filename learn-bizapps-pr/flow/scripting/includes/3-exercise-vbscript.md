In this exercise, you'll create a process that calculates how many hours of overtime employees have worked. Consider that a typical working day is eight hours.

1. Launch WinAutomation and create a new process called **Overtime calculator**.

    ![Screenshot of the New Process dialog box.](..\media\new-process-overtime-calculator.png)

1. Add a **Launch Excel** action to the workspace and configure it to launch an Excel file named **Employees.xlsx**.

    ![Screenshot of the Launch Excel action with populated field.](..\media\launch-excel.png)

1. Use the **Get First Free Column/Row from Excel Worksheet** action to find the first free row in the file.

    ![Screenshot of the Get First Free Column/Row from Excel Worksheet action with populated field.](..\media\get-free-row-excel.png)

1. Deploy a **Loop** and set it to iterate from the second row to the last populated row of the file. The first row contains the titles, so it isn't needed in this process.

    ![Screenshot of the Loop action with populated field.](..\media\loop.png)

1. Inside the loop, use a **Read from Excel Worksheet** action to read the cell that contains the current employee's total working hours.

    ![Screenshot of the Read from Excel Worksheet action with populated field.](..\media\read-excel.png)

1. Deploy a **Run VBScript** action. In the **VBScript to run** field, populate the code that's shown in the following image. This code uses the modulo operator to calculate the rest of the operation as **total working hours / 8**.

    ![Screenshot of the Run VBScript action with populated field.](..\media\run-vbscript-exercise.png)

1. The return value of the **Run VBScript** action is a text value. Use a **Convert Text to Number** action to convert it to a number.

    ![Screenshot of the Convert Text to Number action with populated field.](..\media\convert-text-to-number-vbscript.png)

1. Use a **Write to Excel Worksheet** action to write the numerical value in the current row's third cell.

    ![Screenshot of the Write to Excel Worksheet action with populated field.](..\media\write-excel.png)

1. Outside the loop, add a **Close Excel** action to save and close the file.

    ![Screenshot of the Close Excel action with populated field.](..\media\close-excel.png)

1. Save the process and then run it to test that every action works as expected.

    ![Screenshot of the completed process with the run button highlighted.](..\media\final-process-vbscript.png)
