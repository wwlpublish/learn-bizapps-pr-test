When you run processes through the console, a trigger, or schedule, the related events are logged into a central log file. 

> [!NOTE]
> When a process is run through the Process designer, the event is not recorded in the log database.

Properties allow you to define what information will be logged and enable you to create more informative logs. 

## Automatic logging 

Automatic logging determines whether the logs will contain information for every single action run of the process.

This option can be valuable when running complicated processes where a single log message may not be sufficient. 

To enable automatic logging:

1.	Open the Process properties dialog box, and select the General tab.

    ![The General tab in the process properties dialog.](..\media\general-tab-process-properties.png)

1.	Enable the **Automatic logging** checkbox.

    ![A checkbox that enables the Automatic Logging feature.](..\media\automatic-logging-process-properties.png)

## Add a screenshot to logs

Properties also enable you to add a screenshot to your logs. By enabling this feature, a screenshot of the current monitor state will be added into the logs when errors occur.

To enable this feature:

1.	Open the Process properties dialog box, and select the Error Handling tab.

    ![The Error Handling tab in the process properties dialog.](..\media\error-handing-tab-process-properties.png)

1.	Select the **Override Default Options** radio button to override the global error handling behavior. 

    ![Radion buttons that enable or disable the default options overriding.](..\media\override-default-options-error-handling-tab.png)

1.	Enable the **Add a Screenshot to Logs** checkbox.

    ![A checkbox that adds screenshots to the logs.](..\media\screenshots-logs-error-handling.png)

