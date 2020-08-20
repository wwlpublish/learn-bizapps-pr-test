By using properties, you can configure process-level (third level) error handling. This level is set individually for each process and overrides the global behavior defined in the **Options** tab. 

To override the global behavior for the selected process: 

1.	Navigate to the **Error Handling** tab inside the Process properties dialog.

    ![The Error Handling Tab in the process properties dialog.](..\media\error-handling-tab-process-properties.png)

1.	Select the **Override Default Options** radio button. 

    ![Radio buttons that enable or disable the default options overriding.](..\media\override-default-options-error-handling.png)

1.	Enable the actions  that you want to be run when an error occurs. WinAutomation provides five different options:

    1.	Send an email to one or multiple recipients. You can set the STMP server credentials in the Options tab, Email/SMTP. More information can be found on the [Email documentation page](https://docs.winautomation.com/en/email-smtp-tab.html).

        ![A checkbox that enables the Send Email feature, and the relevant fields.](..\media\send-email-error-handling.png)

    1.	Run another process. It is a common practice to develop secondary processes that handle possible exceptions of the primary process. 

         ![A checkbox that enables the Run Another process feature, and the relevant field.](..\media\run-another-process-error-handling.png)

    1.	Append text to a selected file.

        ![A checkbox that enables the Write Event to Text file feature, and the relevant field.](..\media\write-event-to-text-error-handling.png)

    1.	Record the exception in the Windows Application Event Log. 

         ![A checkbox that enables recording to the Windows Event Log.](..\media\windows-event-log-error-handling.png)

    1.	In the WinAutomation logs, add a screenshot of the monitors when an exception occurs.

        ![A checkbox that enables screenshots to the logs.](..\media\screenshots-error-handling.png)


