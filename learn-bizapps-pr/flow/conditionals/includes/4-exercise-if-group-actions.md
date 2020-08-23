In this exercise, you will apply some of the If actions available, in order to identify the capabilities they offer.

1. Use a **Get Special Folder** action to retrieve the path to the desktop.

2. Check whether a folder named **Records** exists in the desktop. To do this, use the **If Folder Exists** action, and configure its input as follows:

    ![If records folder exists](..\media\if-records-folder-exists.png)

3. Inside the **If** block, add an **If File Exists** action to check if the **Expenses** Excel file exists inside the **Records** folder. Configure it as follows:

    ![If expenses file exists](..\media\if-expenses-file-exists.png)

4. This, of course, will only run if the Folder exists. By this stage, your process should look like this:

    ![Initial process structure](..\media\initial-process-structure.png)

5. If the file exists, move it to the desktop folder using the **Move Files** action. Otherwise, the user should be notified; add an **Else** action inside the second if block, and a **Display Message** action to inform the user that the file has already been moved:

    ![Initial process structure](..\media\initial-process-structure.png)

6. Finally, in case the folder itself does not exist, add an **Else** action inside the first **If** block, and a second **Display Message** action to inform the user that the **Records** folder does not exist:

    ![Outside else display message](..\media\outside-else-display-message.png)
    
7. We suggest that you run the process, trying different scenarios. 
