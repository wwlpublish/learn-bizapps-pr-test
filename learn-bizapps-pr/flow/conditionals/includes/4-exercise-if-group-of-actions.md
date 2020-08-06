As stated above, the **If** group of Actions contains multiple Actions, which enable the user to set a variety of initial conditions, such as checking the existence of files and folders, text on the screen, running Windows processes and services, and so on.

In this exercise, you will apply some of the **If** Actions available, in order to identify the capabilities they offer.

## Step 1
Use a **Get Special Folder** Action to retrieve the path to the Desktop.

## Step 2
Check whether a folder named **Records** exists in the Desktop. To do this, use the **If Folder Exists** Action, and configure its input as follows:

![If records folder exists](..\media\if-records-folder-exists.png)

## Step 3
Inside the **If** block, add an **If File Exists** Action to check if the **Expenses** Excel file exists inside the **Records** folder. Configure it as follows:

![If expenses file exists](..\media\if-expenses-file-exists.png)

This, of course, will only be executed if the Folder exists.

By this stage, your Process should look like this:

![Initial process structure](..\media\initial-process-structure.png)

## Step 4
If the file exists, move it to the Desktop folder using the **Move File(s)** Action. Otherwise, the user should be notified; add an **Else** action inside the second if block, and a **Display Message** action to inform the user that the file has already been moved:

![Initial process structure](..\media\initial-process-structure.png)

## Step 5
Finally, in case the folder itself does not exist, add an **Else** Action inside the first **If** block, and a second **Display Message** Action to inform the user that the **Records** folder does not exist:

![Outside else display message](..\media\outside-else-display-message.png)
    
Execute the Process, trying different scenarios, to examine the Process’ behavior each time. 
