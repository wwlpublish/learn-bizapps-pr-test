Error handling is configured as the platform’s response to a process that has failed.

In this exercise, you will apply error handling rules to all processes through the **Console Settings**, and then configure a different set of rules for a specific process, whose errors should be handled in a different way.

## Set up global error handling for all processes

### Step 1

Open the **WinAutomation Console**, navigate to **Options**, and click on the **Error Handling** subtab:

![The Behaviour tab in the WinAutomation Options.](..\media\behaviour-error-handling-options-b.png)

### Step 2

Choose the **Write Event to Text File** option, assigning a .txt file in your Documents folder, and **Add Screenshot to Logs**:

![The Write Event to Text File option in the behaviour tab.](..\media\write-event-to-text-file-error-handling..png)

With this configuration in place, these operations will be performed whenever any process fails.

Let’s assume that a process has been rolled out by IT, and the error handling requirements in this case are different.

### Step 3

Locate the process in the **Processes** tab of the **Console**, select it, and press the **Properties** button:

> [!NOTE]
> For the purposes of this exercise, any example process will do.

![The Properties button in the Processes tab.](..\media\process-properties-button-console.png)

### Step 4

In the **Process Properties** window, navigate to **Error Handling**, and select **Override Default Options**:

![The Process Properties window.](..\media\override-default-options-error-handling-b.png)

### Step 5

Proceed to check the **Record event to Windows Event Log** option:

![The Process Properties window with the Overide Default Options radiobutton enabled.](..\media\windows-event-log-error-handling.png)

Since the default options have been overridden, any errors produced by this process will not be written to the previously created text file, nor will they produce a screenshot to the logs; only the custom error handling options will be applied.


