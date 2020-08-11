A run policy defines the behavior of the WinAutomation platform when it tries to run a process, while at least one of the following conditions is true:

- You are logged in and your workstation is locked.
- You are not logged in.
- A physical screen is not available.

To set the desired behavior for these cases:

1.	Navigate to the **Run Policy** tab inside the **Process Properties** dialog.

    ![The Run Policy tab in the Process Properties dialog.](..\media\run-policy-tab-process-properties.png)

1.	Select the desired action to be performed when the process is triggered, while you are logged in and your workstation is locked. You can choose to unlock the workstation using the password specified in the **Authentication** tab of WinAutomation **Options**.

    In case the selected process is not interactive, you can choose to run the process without unlocking the workstation. Lastly, you can choose to cancel the process. 

    ![Radio buttons to select what action will be performed when you are logged in and your workstation is locked.](..\media\loggedin-workstation-locked-run-policy.png)

    [!NOTE]
    A process is called interactive when it performs input or output operations, such as keystrokes, mouse movements, and messages.

1.	Select the desired action to be performed when the process is triggered, while you are not logged in. You can choose between the same options as in the previous step. 

    ![Radio buttons to select what action will be performed when you are not logged in.](..\media\loggedin-run-policy.png)

1.	Select the desired action to be performed when the process is triggered and there is no available screen. You can choose between starting the process in non-interactive mode or canceling the process. 

    ![Radio buttons to select what action will be performed when there is no available screen.](..\media\no-screen-available-run-policy.png)

1.	Lastly, if you want to restore the workstation to the logged out/locked state it was initially, enable the respective option. 

    ![A checkbox that enables the restoring to the Logged out/Locked state in which the workstation was initially.](..\media\restore-workstation-state-run-policy.png)