Contents {#contents .TOCHeading}
========

[Introducing WinAutomation Options 2](#introducing-winautomation-options)

[Learning Objectives 2](#learning-objectives)

[Prerequisites 2](#prerequisites)

[Configure Notification Settings 3](#configure-notification-settings)

[Backup and Restore the Database File 6](#backup-and-restore-the-database-file)

[Create a Global Concurrency Policy 10](#create-a-global-concurrency-policy)

[Treat files as ASCII in FTP Actions. 14](#treat-files-as-ascii-in-ftp-actions)

[Configure Level 4 Error Handling 17](#configure-level-4-error-handling)

[SMTP Server Configuration 20](#smtp-server-configuration)

[Sign in with a new Power Automate Account 22](#sign-in-with-a-new-power-automate-account)

[Check your knowledge 25](#check-your-knowledge)

[Summary 25](#summary)

Introducing WinAutomation Options
=================================

WinAutomation provides an extensive selection of options that enables you to configure the way the platform operates. All the platform\'s essential settings are located in the Options Tab, the last Tab of the Console menu.

The Options Tab consists of 3 sub-Tabs:

1.  Settings

2.  Error Handling

3.  Account

Each Tab configures different features of the platform, such as Concurrency policy, Database operations, Error Handling and Account management.

![](media/image1.png){width="6.5in" height="3.686111111111111in"}

By the end of this module, you will be able to understand and execute some of the most important operations that WinAutomation Options provide.  

Learning Objectives
-------------------

In this module, you will:

-   Understand the various configurations and options of WinAutomation.

-   Configure notification settings

-   Take backup of the database file and restore it.

-   Create a Concurrency Policy.

-   Become familiar with Level 4 Exception Handling.

-   Sign out and connect with a new Microsoft Power Automate account.

Prerequisites
-------------

-   Basic familiarity with the WinAutomation Console.

-   Basic familiarity with WinAutomation architecture.

-   Basic familiarity with Exception Handling functionality.

Configure Notification Settings
===============================

To enhance user experience, WinAutomation displays a notification every time a Process is executed. 

This notification pane is called **Notification Popup Window**, and it is be displayed exclusively when a Process is fired from the WinAutomation Console, a Schedule, or a Trigger. 

![](media/image2.png){width="4.6670713035870515in" height="1.1334317585301836in"}

Note

A notification is not displayed when a Process is executed from within the Process Designer.

The **Notification Popup Window **is enabled by default, but you can disable it by performing the following steps:

1.  Navigate to the **General **Tab inside the **Settings **Tab.

> ![](media/image3.png){width="6.5in" height="4.282777777777778in"}

2.  Uncheck the **Display Notification Popup Window** option in the **Notifications** section.

![](media/image4.png){width="6.5in" height="4.282777777777778in"}

After the deactivation, you can run a Process to confirm that no notification is displayed. 

Besides the **Notification Popup Window**, notification settings allow you to enable or disable the WinAutomation icon in the Windows system tray.

To disable WinAutomation icon in the system tray:

1.  Navigate to the **General **Tab inside the **Settings **Tab.

> ![](media/image3.png){width="6.5in" height="4.282777777777778in"}

2.  Uncheck the **Display Icon in System Tray** in the **Notifications** section. 

> ![](media/image5.png){width="6.5in" height="4.282777777777778in"}

Backup and Restore the Database File
====================================

All WinAutomation Processes are stored collectively in one database file named Processes.dat. The platform uses this file to save new Processes or restore existing ones. 

To create a backup file of this database:

1.  Navigate to the **Processes File **Tab inside the **Settings **Tab.

    ![](media/image6.png){width="6.5in" height="4.282638888888889in"}

2.  Click on the **Backup Database** button.

    ![](media/image7.png){width="6.5in" height="4.282638888888889in"}

3.  In the pop-up window, select a destination folder for the file. 

    ![](media/image8.png){width="6.5in" height="4.604166666666667in"}

Alternatively, you can create a backup of the database by manually copying the file from the defined location.

![](media/image9.png){width="6.5in" height="3.4256944444444444in"}

The first field of the **Processes File** Tab determines the location of the database file. The default location is: **C:\\Users\\\...username\...\\Documents\\WinAutomation\\Processes.dat**

![](media/image10.png){width="6.5in" height="4.282638888888889in"}

To restore a database file:

1.  Navigate to the **Processes File **Tab inside the **Settings **Tab.

    ![](media/image11.png){width="6.500694444444444in" height="4.280555555555556in"}

2.  Click on the **Restore Database** button.

    ![](media/image12.png){width="6.5in" height="4.282638888888889in"}

3.  In the pop-up window, select the file to be restored.

    ![](media/image13.png){width="6.5in" height="4.604166666666667in"}

Besides the **Restore Database** option, you can restore a database by replacing the current file in the respective folder.

Note

Please keep in mind that restoring a database file will delete all the Processes in your current database and replace them with the ones from the backup copy. 

Create a Global Concurrency Policy
==================================

WinAutomation supports parallel execution of numerous Processes or even parallel execution of many instances of the same Process. Concurrency Policies allow you to restrict the number of Processes that can be executed simultaneously.

By implementing a Concurrency Policy, you can ensure that low-performance machines will not execute a high number of Processes at the same time and you may prevent crashes.

To create a Global Concurrency Policy:

1.  Navigate to the **Concurrency Policy** Tab inside the **Settings **Tab.

    ![](media/image14.png){width="6.5in" height="4.282638888888889in"}

2.  Enable the **Limit the number of Processes that can run concurrently** option.

    ![](media/image15.png){width="6.5in" height="4.282638888888889in"}

3.  Set the max number of simultaneously executed Processes in the **Max processes limit** field.

    ![](media/image16.png){width="6.5in" height="4.282638888888889in"}

4.  In the **If this limit is reached** dropdown menu, select the desired action to be performed when the limit is reached. You can choose between adding Processes in a waiting queue or cancel the execution of them.

    ![](media/image17.png){width="6.5in" height="4.282638888888889in"}

5.  Optional: If you select **Queue Process** in the previous step, you can enable the **Set Timeout** checkbox to set a period after which the Process will be rejected.

    ![](media/image18.png){width="6.5in" height="4.282638888888889in"}

6.  Populate **the Wait for max \_ minutes before being rejected** field with the desired value.

    ![](media/image19.png){width="6.5in" height="4.282638888888889in"}

Treat files as ASCII in FTP Actions 
====================================

When downloading or uploading files using the **Download File(s) from FTP** and **Upload File(s) to FTP** Actions, you can specify the transfer type to be ASCII, BINARY or AUTO. 

If you select AUTO, WinAutomation will use a defined list of file types to determine whether the file will be transferred in ASCII or binary mode.

![](media/image20.png){width="4.173519247594051in" height="3.5in"}

This list is also used by the **Download Folder(s) from FTP** and **Upload Folder(s) to FTP** Actions to determine how to transfer the files contained into the folders.

To configure WinAutomation to treat a file type as ASCII:

1.  Navigate to the **FTP** Tab inside the **Settings **Tab.

    ![](media/image21.png){width="6.5in" height="4.282638888888889in"}

2.  Populate the respective field with the file type you want to treat as ASCII.

    ![](media/image22.png){width="6.5in" height="4.282638888888889in"}

3.  Click on the **Add Filetype** button.

    ![](media/image23.png){width="6.5in" height="4.282638888888889in"}

To remove a file type from the list, select it and click on the **Remove Selected** button.

![](media/image24.png){width="6.5in" height="4.282638888888889in"}

More information about FTP Action can be found on the respective [WinAutomation documentation page](https://docs.winautomation.com/en/ftp.html). 

Configure Level 4 Error Handling 
=================================

Through the Options Tab, you can configure the Level 4 of the WinAuotmation Error Handling functionality. This level is global across Processes, and the defined behaviour will be executed If you have not overridden the behaviour of a Process at a lower level.

To determine which actions will be performed if a Process fails to execute successfully:

1.  Navigate to the **Behaviour** Tab inside the **Error Handling **Tab.

    ![](media/image25.png){width="6.5in" height="4.282638888888889in"}

2.  Enable the respective action(s) you want to be executed when an error occurs. WinAutomation provides five different options:

    a.  Send an Email to one or multiple recipients. You can set the details about the SMTP server in the **Email/SMTP** Tab.

![](media/image26.png){width="6.5in" height="4.282638888888889in"}

b.  Run another Process. It is a common practice to develop secondary Processes that handle possible Exceptions of the primary Process.

![](media/image27.png){width="6.5in" height="4.288194444444445in"}

c.  Append text to a selected file.

![](media/image28.png){width="6.5in" height="4.288194444444445in"}

d.  Record the Exception to the Windows Applications Event Log.

![](media/image29.png){width="6.5in" height="4.288194444444445in"}

e.  Add a Screenshot of the monitor(s) when an Exception occurs in the WinAutomation Logs. More information about the Logging in WinAutomation can be found on the [respective documentation page](https://docs.winautomation.com/en/logs.html).

![](media/image30.png){width="6.5in" height="4.288194444444445in"}

SMTP Server Configuration
-------------------------

If you enable the **Send Email option** in the **Behaviour** Tab, you have to configure the SMTP server information. To do that:

1.  Navigate to the **Email/SMTP** Tab inside the **Error Handling **Tab.

    ![](media/image31.png){width="6.5in" height="4.288194444444445in"}

2.  Populate the **Address** and the **Port** of the SMTP server. If the server uses SSL, enable the respective option.

![](media/image32.png){width="6.5in" height="4.288194444444445in"}

3.  In case the server needs authentication, enable the **SMTP Server needs Authentication** checkbox**,** and populate the **Username** and **Password** fields.

![](media/image33.png){width="6.5in" height="4.288194444444445in"}

4.  Lastly, select if you want WinAutomation to accept untrusted certificates.

Note

In case you have enabled 2FA (Two-Factor Authentication) in your email account, you have to populate the **Password** field with an App Password. More information can be found on the respective [WinAutomation documentation page](https://docs.winautomation.com/en/email-interaction-with-two-step-verification.html#email-interaction-with-two-step-verification).

Sign in with a new Power Automate Account
=========================================

In case you want to sign out from your current Microsoft Power Automate Account and connect with a new one, you can do it through the **Account** Tab

1.  Navigate to the **Account** Tab.

    ![](media/image34.png){width="6.5in" height="4.288194444444445in"}

2.  Click on the **Sing out** button.

![](media/image35.png){width="6.5in" height="4.288194444444445in"}

3.  Select the **Use another account** option in the popup window.

    ![](media/image36.png){width="3.989093394575678in" height="3.941666666666667in"}

4.  Populate your credentials.

    ![](media/image37.png){width="3.99in" height="3.942562335958005in"}

Note

If you sign out without connecting to a new account, WinAutomation functionality will be disabled.

Check your knowledge
====================

Answer the following questions to see what you have learned.

1.  Which of the following Tabs does NOT exist in the Options Tab?

    a.  Logs \[Well done! Logs Tab is located in the Console main window and not in the Option Tab.\]

    b.  Error Handling \[Your answer is incorrect. The Error Handling Tab is the second option inside the Options Tab.\]

    c.  Account \[Your answer is incorrect. The Account Tab is the third option inside the Options Tab.\]

2.  The Handling Tab in Options Tab is the only Error Handling Level in WinAutomation.

    d.  True \[Your answer is incorrect. WinAutomation provides four Error Handling Levels.\]

    e.  False \[Well done! WinAutomation provides four Error Handling Levels.\]

3.  Through the Error Handling Tab, you can:

    f.  Add a screenshot to Logs \[Well done! The Add screenshot option is located in the Error Handling Tab.\]

    g.  Add a video to Logs \[Your answer is incorrect. There is no option to Record video when an error occurs in WinAutomation.\]

    h.  Both \[Your answer is incorrect. WinAutomation provides only the option to take a screenshot when an error occurs.\]

4.  In order to change the connected Microsoft Power Automate account, you have to reinstall WinAutomation.

    i.  True \[Your answer is incorrect. You can sign out of your current account and sign in a new one through the Account sub-Tab.\]

    j.  False \[Well done! You can sign out of your current account and sign in a new one through the Account sub-Tab.\]

Answers:

-   a

-   b

-   a

-   b

Summary
=======

WinAutomation Options Tab provides a wide variety of configurations and enables you to adjust the platform to your needs. By applying a custom Error Handling behavior and creating a Concurrency Policy, you can make Process execution more productive and robust to errors.
