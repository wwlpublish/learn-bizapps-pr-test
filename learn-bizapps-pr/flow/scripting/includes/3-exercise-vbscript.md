In this exercise, you'll create a process that calculates how many hours employees have worked overtime. Consider that a typical working day is 8 hours. 

1. Launch WinAutomation and create a new process called **Overtime calculator**.

    ![The New Porcess dialog.](..\media\new-process-overtime-calculator.png)

1. Add a **Launch Excel** action to the workspace and configure it to launch an Excel file named **Employees.xlsx**.

    ![The Launch Excel action with populated field.](..\media\launch-excel.png)

1. Use the **Get First Free Column/Row from Excel Worksheet** action to find the first free row in the file.

    ![The Get First Free Column/Row from Excel Worksheet action with populated field.](..\media\get-free-row-excel.png)

1. Deploy a **Loop** and set it to iterate from the second row to the last populated row of the file. The first row contains the titles, so it isn't needed in this process.

    ![The Loop action with populated field.](..\media\loop.png)

1. Inside the loop, use a **Read from Excel Worksheet** action to read the cell containing the current employee's total working hours. 

    ![The Read from Excel Worksheet action with populated field.](..\media\read-excel.png)

1. Now, deploy a **Run VBScript** action. In the **VBScript to run** field, populate the code of the image below. This code uses the modulo operator to calculate the rest of the operation **total working hours / 8**. 

    ![The Run VBScript action with populated field.](..\media\run-vbscript-exercise.png)

1. Keep in mind that the return value of the **Run VBScript** action is a text. Use a **Convert Text to Number** action to convert it to a number. 

    ![The Convert Text to Number action with populated field.](..\media\convert-text-to-number-vbscript.png)

1. Use a **Write to Excel Worksheet** action to write the numerical value in the current row's third cell.

    ![TheWrite to Excel Worksheet action with populated field.](..\media\write-excel.png)

1. Outside the loop, add a **Close Excel** action to save and close the file.

    ![The Close Excel action with populated field.](..\media\close-excel.png)

1. Lastly, save the process and execute it to test that every action works as expected. 

    ![The final process.](..\media\final-process-vbscript.png)