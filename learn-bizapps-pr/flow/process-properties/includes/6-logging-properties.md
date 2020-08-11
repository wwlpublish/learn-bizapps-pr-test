When you run processes through the **Console** or because to a **Trigger** or **Schedule**, the related events are logged into a central log file. 

> [!NOTE]
> Keep in mind that when a process is run through the **Process Designer**, the event is not recorded into the log database.

Process properties allow you to define what information will be logged and enable you to create more informative logs. 

The first logging feature in WinAutomation that will present is called **Automatic Logging** and defines if the logs will contain information for every single action run in the process.

This option can be valuable when running complicated processes where a single log message may not be sufficient. 

To enable the respective feature:

1.	Navigate to the **General** tab inside the **Process Properties** dialog.

    ![The General tab in the Process Properties dialog.](..\media\general-tab-process-properties.png)

1.	Enable the **Automatic Logging** checkbox.

    ![A checkbox that enables the Automatic Logging feature.](..\media\automatic-logging-process-properties.png)

The second logging feature that process properties provide is called **Add a Screenshot to Logs**. By enabling this feature, a screenshot of the current monitor state will be added into the logs when an error occurred.

To enable this feature:

1.	Navigate to the **Error Handling** tab inside the **Process Properties** dialog.

    ![The Error Handling tab in the Process Properties dialog.](..\media\error-handing-tab-process-properties.png)

1.	Select the **Override Default Options** radio button to override the global error handling behavior. 

    ![Radion buttons that enable or disable the default options overriding.](..\media\override-default-options-error-handling-tab.png)

1.	Enable the **Add a Screenshot to Logs** checkbox.

    ![A checkbox that adds screenshots to the logs.](..\media\screenshots-logs-error-handling.png)

