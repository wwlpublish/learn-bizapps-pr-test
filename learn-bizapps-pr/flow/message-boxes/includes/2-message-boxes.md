Message boxes enable real-time interaction between users and processes. **message boxes** actions can be used both to provide input to processes, as well as provide output to the users.

We will examine both cases in the following paragraphs.

## Output actions

To demonstrate actions that provide output to the user, we'll examine a process that extracts data from an excel file and enters it into a web platform:
 
![output function workspace](..\media\output-function-workspace.png)

Based on the data size and the time it takes to process each entry, this process may take a lot of time to complete - therefore, the user might prefer a high-level overview of how far the process has progressed, for example, which claim it's currently working on. This can be done by using the **Display Notification** action, which displays a message on the notification window while running:
 
![display notification action properties](..\media\display-notification-action-properties.png)

 
![output function workspace continued](..\media\output-function-workspace-continued.png)

Also, when the process is finished, we could add a message informing the user that the process has run, and mention the number of claims processed:
 
![display message action properties](..\media\display-message-action-properties.png)

 
![display message action in workspace](..\media\display-message-action-in-workspace.png)

Let’s examine how these actions will affect what the user sees. Every time a new entry is being processed, the message on the Notification Window will change accordingly:
 
![winautomation notification](..\media\winautomation-notification.png)

When the process is complete, the user is notified:
 
![message box](..\media\message-box.png)

## Input actions

Another important function of **message boxes** actions is allowing users to provide input to the process.

User input may come in many forms – text, date and time, files and folders, forms, etc. Each of these input types corresponds to a different message box action in WinAutomation.

As an example, consider the following process, which receives a file path and a multi-line text as input from the user, and appends the text input to the file:
 
![input function workspace](..\media\input-function-workspace.png)

The **Display Select File Dialog** action will produce a dialog window for the user to select a file; in this example, it is configured to filter for .txt files only:
 
![display select file dialog action properties](..\media\display-select-file-dialog-action-properties.png)

The **Display Input Dialog** action is configured to receive multi-line text as input:
 
![display input dialog action properties](..\media\display-input-dialog-action-properties.png)

Running this process will prompt the user to select a text file; they will then be prompted to enter the input; and finally, the input will be appended to the selected file.
 