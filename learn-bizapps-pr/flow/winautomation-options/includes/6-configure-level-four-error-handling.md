Through the **Options** tab, you can configure the fourth level of the WinAuotmation error handling functionality. This level is global across processes, and the defined behavior will be executed if you have not overridden the behavior of a process at a lower level.

To determine which actions will be performed if a process fails to execute successfully:

1.	Navigate to the **Behavior** tab inside the **Error Handling** tab.

    ![The Behaviour tab.](..\media\behaviour-tab-error-handling-options.png)

1.	Enable the respective action(s) you want to be executed when an error occurs. WinAutomation provides five different options:
    
    1.  Send an email to one or multiple recipients. You can set the details about the SMTP server in the **Email/SMTP** tab.

        ![A checkbox to enable the Send Email option and the relevant fields.](..\media\send-email-error-handling.png)

    1.  Run another process. It is a common practice to develop secondary processes that handle possible exceptions of the primary process. 

        ![A checkbox to enable the Run Another Process option and the relevant field.](..\media\run-another-process-error-handling.png)

    1.  Append text to a selected file.

        ![A checkbox to enable the Write Event to Text File option and the relevant field.](..\media\write-event-to-text-file-error-handling.png)

    1.  Record the exception to the **Windows Application Event Log**. 

        ![A checkbox to enable recording to the Windows Event Log.](..\media\windows-event-log-error-handling.png)

    1.  Add a screenshot of the monitor(s) when an exception occurs in the WinAutomation logs. More information about logging in WinAutomation can be found in the respective [documentation page](https://docs.winautomation.com/en/logs.html). 

        ![A checkbox to enable screenshots in the WinAutomation logs.](..\media\screenshots-error-handling.png)

## SMTP server configuration

If you enable the **Send Email** option in the **Behavior** tab, you have to configure the SMTP server information. To do that:

1.	Navigate to the **Email/SMTP** tab inside the **Error Handling** tab.

    ![The Email/SMTP tab.](..\media\email-smtp-tab-error-handling-options.png)

1.	Populate the **Address** and the **Port** of the SMTP server. If the server uses SSL, enable the respective option.

    ![Two fields to populate the Address and Port of the server.](..\media\address-port-email-smtp-tab.png)

1.	In case the server needs authentication, enable the **SMTP Server needs Authentication** checkbox, and populate the **Username** and **Password** fields. 

    ![A chechbox that specified if The SMTP server needs authentication, and the Username and Passwords fields.](..\media\authentication-email-smtp-tab.png)

1.	Lastly, select if you want WinAutomation to accept untrusted certificates.

[!ΝΟΤΕ]
In case you have enabled 2FA (Two-Factor Authentication) in your email account, you have to populate the **Password** field with an application password. More information can be found in the respective [WinAutomation documentation page](https://docs.winautomation.com/en/email-interaction-with-two-step-verification.html#email-interaction-with-two-step-verification). 