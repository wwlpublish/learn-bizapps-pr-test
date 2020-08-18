In the Options tab, you can configure global WinAuotmation error handling settings. Global error handling works for any process that you have not defined error handling for at a lower level. 

To determine which actions will be performed if a process fails to run successfully:

1.	Navigate to the **Error Handling** tab, and then **Behavior**.

    ![The Behaviour tab.](..\media\behaviour-tab-error-handling-options.png)

1.	Enable the respective actions you want to be run when an error occurs in any process that fails. WinAutomation provides five different options:
    
    1.  Send an email to one or multiple recipients. You can set the details about the SMTP server in the **Email/SMTP** tab.

        ![A checkbox to enable the Send Email option and the relevant fields.](..\media\send-email-error-handling.png)

    1.  Run another process. It is a common practice to develop secondary processes that handle possible exceptions of the primary process. 

        ![A checkbox to enable the Run Another Process option and the relevant field.](..\media\run-another-process-error-handling.png)

    1.  Append text to a selected file.

        ![A checkbox to enable the Write Event to Text File option and the relevant field.](..\media\write-event-to-text-file-error-handling.png)

    1.  Record the exception to the **Windows Application Event Log**. 

        ![A checkbox to enable recording to the Windows Event Log.](..\media\windows-event-log-error-handling.png)

    1.  Add a screenshot of the monitors when an exception occurs in the WinAutomation logs. More information about logging in WinAutomation can be found in the [WinAutomation log documentation](https://docs.winautomation.com/logs.html). 

        ![A checkbox to enable screenshots in the WinAutomation logs.](..\media\screenshots-error-handling.png)

## SMTP server configuration

If you enable the Send Email option, you must configure the SMTP server.

1.	Navigate to the **Error Handling** tab, and then **Email/SMTP**.

    ![The Email/SMTP tab.](..\media\email-smtp-tab-error-handling-options.png)

1.	Populate the **Address** and the **Port** of the SMTP server. If the server uses SSL, enable the that option.

    ![Two fields to populate the Address and Port of the server.](..\media\address-port-email-smtp-tab.png)

1.	IF the server requires authentication, enable the **SMTP Server needs Authentication** checkbox, and populate the **Username** and **Password** fields. 

    ![A chechbox that specified if The SMTP server needs authentication, and the Username and Passwords fields.](..\media\authentication-email-smtp-tab.png)

1.	Lastly, select whether you want WinAutomation to accept untrusted certificates.

> [!ΝΟΤΕ]
> In case you have enabled multifactor authentication in your email account, you must populate the Password field with an application password. More information can be found in the  [WinAutomation multifactor authentication documentation](https://docs.winautomation.com/email-interaction-with-two-step-verification.html#email-interaction-with-two-step-verification). 