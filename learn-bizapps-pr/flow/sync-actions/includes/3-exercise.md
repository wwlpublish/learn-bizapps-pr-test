In this exercise, you will develop a process that registers new customers in a Microsoft Excel file. You will use synchronization actions to ensure that multiple instances of the process can't modify the file simultaneously.

1. Launch WinAutomation and create a new process named **Register new customer**.

    ![Screenshot of the create new process dialog box.](..\media\register-new-customer.png)

1. Create an Excel file named **Customers.xlsx** and deploy a **Launch Excel** action to open it.

    ![Screenshot of the Launch Excel action with populated fields.](..\media\launch-excel.png)

1. Add three **Display Input Dialog** actions to the workspace. Configure them to prompt users to enter the customer's **name**, **last name**, and **ID number**.

    ![Screenshot of the three Display Input Dialog actions in the workspace.](..\media\display-input-dialog.png)

1. Use a **Get First Free Column/Row from Excel Worksheet** action to find the Excel file's first free row.

    ![Screenshot of the Get First Free Column and Row from Excel Worksheet in the workspace.](..\media\get-first-free-row.png)

1. Deploy a **Write to Excel Worksheet** action to write the customer's name in the first column of the first free row.

    ![Screenshot of the Write to Excel Worksheet action with populated fields.](..\media\write-name-excel.png)

1. Repeat the previous step to write the customer's last name and the ID number in the second and third columns, respectively.

    ![Screenshot of the two Excel Worksheet actions in the workspace.](..\media\write-lastname-id-excel.png)

1. Use a **Close Excel** action to save and close the Excel file.

    ![Screenshot of the Close Excel actions with populated fields.](..\media\close-excel.png)

1. Deploy a **Lock Handle** action and set it as the first action in the process. Open its properties and enter a name for the handle, such as **Excel Handle**.

    ![Screenshot of the Lock Handle action with populated fields.](..\media\lock-handle.png)

1. Add a **Release Handle** at the end of the process to indicate the locked region's end. In the action's properties, enter the same name for the handle as before.

    ![Screenshot of the Release Handle action with populated fields.](..\media\release-handle.png)

1. Save the process and run it twice simultaneously. If the locked region is configured correctly, the second instance will wait for the first one to be completed.

    ![Screenshot of the notification when one instance of the process is waiting for the other one.](..\media\notification.png)
