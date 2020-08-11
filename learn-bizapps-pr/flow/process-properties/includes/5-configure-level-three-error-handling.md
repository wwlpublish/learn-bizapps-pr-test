Through the process properties, you can configure the third level of the WinAutomation error handling functionality. This level is set individually for each process and overrides the global behavior defined in the **Options** tab. 

To override the global behavior for the selected process: 

1.	Navigate to the **Error Handling** tab inside the **Process Properties** dialog.

    ![The Error Handling Tab in the Process Properties Dialog.](..\media\error-handling-tab-process-properties.png)

1.	Select the **Override Default Options** radio button. 

    ![Radio buttons that enable or disable the default options overriding.](..\media\override-default-options-error-handling.png)

1.	Enable the respective action(s) you want to be run when an error occurs. WinAutomation provides five different options:

    1.	Send an Email to one or multiple recipients. You can set the STMP server credentials in the **Email/SMTP** tab of the WinAutomation **Options**. More information can be found on the [respective documentation page](https://docs.winautomation.com/en/email-smtp-tab.html).

        ![A checkbox that enables the Send Email feature, and the relevant fields.](..\media\send-email-error-handling.png)

    1.	Run another process. It is a common practice to develop secondary processes that handle possible exceptions of the primary process. 

         ![A checkbox that enables the Run Another Process feature, and the relevant field.](..\media\run-another-process-error-handling.png)

    1.	Append text to a selected file.

        ![A checkbox that enables the Write Event to Text file feature, and the relevant field.](..\media\write-event-to-text-error-handling.png)

    1.	Record the exception to the Windows Application Event Log. 

         ![A checkbox that enables recording to the Windows Event Log.](..\media\windows-event-log-error-handling.png)

    1.	Add a screenshot of the monitor(s) when an exception occurs in the WinAutomation logs.

        ![A checkbox that enables screenshots to the logs.](..\media\screenshots-error-handling.png)


