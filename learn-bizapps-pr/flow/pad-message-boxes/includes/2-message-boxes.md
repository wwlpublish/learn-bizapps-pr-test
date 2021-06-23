Message boxes enable real-time interaction between users and flows. **Message boxes** actions can be used both to provide input to flows, as well as provide output to the users.

We will examine both cases in the following paragraphs.

## Output actions

To demonstrate actions that provide output to the user, we'll examine a flow that extracts data from an excel file and enters it into a web platform:

![Screenshot of the output function workspace.](..\media\output-function-workspace.png)

Based on the data size and the time it takes to process each entry, this flow may take a lot of time to complete. When the flow is finished, we could add a message informing the user that the flow has run, and mention the number of claims processed:

![Screenshot of the Display message action properties dialog.](..\media\display-message-action-properties.png)

![Screenshot of the display message action in workspace.](..\media\display-message-action-in-workspace.png)

Let’s examine how this action will affect what the user sees. When the flow is complete, the user is notified:

![Screenshot of the message box showing the number of claims processed as 4765.](..\media\message-box.png)

## Input actions

Another important function of message boxes actions is allowing users to provide input to the flow.

User input may come in many forms – text, date and time, files and folders, etc. Each of these input types corresponds to a different message box action.

As an example, consider the following flow, which receives a file path and a multi-line text as input from the user, and appends the text input to the file:

![Screenshot of the input function workspace.](..\media\input-function-workspace.png)

The **Display Select File Dialog** action will produce a dialog window for the user to select a file; in this example, it is configured to filter for .txt files only:

![Screenshot of the Display select file dialog action properties.](..\media\display-select-file-dialog-action-properties.png)

The **Display Input Dialog** action is configured to receive multi-line text as input:

![Screenshot of the Display select file dialog input action properties.](..\media\display-input-dialog-action-properties.png)

Running this flow will prompt the user to select a text file; they will then be prompted to enter the input; and finally, the input will be appended to the selected file.
