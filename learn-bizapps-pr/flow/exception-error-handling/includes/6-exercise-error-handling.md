Set up error handling to configure the platform’s response to a process that has failed.

In this exercise, you will apply error handling rules to all processes through the **Console Settings**, and then configure a different set of rules for a specific process, whose errors should be handled in a different way.

## Set up global error handling for all processes

1. Open the **WinAutomation Console**, navigate to **Options**, and click on the **Error Handling** subtab:

    ![The Behaviour tab in the WinAutomation Options.](..\media\behaviour-error-handling-options-b.png)

1. Choose the **Write Event to Text File** option, assigning a .txt file in your documents folder, and **Add Screenshot to Logs**:

    ![The Write Event to Text File option in the behaviour tab.](..\media\write-event-to-text-file-error-handling.png)

    With this configuration in place, these operations will be performed whenever any process fails.

## Set up individual error handling

Let’s assume that a process has been rolled out by IT, and the error handling requirements in this case are different.

1. Locate the process in the console's Processes tab, select it, and press Properties.

    > [!NOTE]
    > For the purposes of this exercise, any example process will do.

    ![The Properties button in the Processes tab.](..\media\process-properties-button-console.png)

1. In the **Process Properties** window, navigate to **Error Handling**, and select **Override Default Options**:

    ![The Process Properties window.](..\media\override-default-options-error-handling-b.png)

1. Select **Record event to Windows Event Log**.

    ![The Process Properties window with the Overide Default Options radiobutton enabled.](..\media\windows-event-log-error-handling.png)

    Because the default options have been overridden, any errors produced by this process will not be written to the previously created text file, nor will they produce a screenshot to the logs; only the custom error handling options will be applied.


