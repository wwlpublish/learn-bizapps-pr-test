This exercise demonstrates some actions that are used to organize and manage files and folders.

In this exercise, you will:

- Get the location of the desktop folder for the current user.
- Retrieve the contents of a folder on the desktop.
- Create a new folder on the desktop.
- Copy the contents of the first folder to the new folder.
- Write to a text file.
- Rename the text file to contain the current date and time in its file name.

### Steps

Follow these steps to organize and manage files and folders:

1. Create a folder on your **Desktop** and name it **Important**.

2. Open the new folder, right-click in the folder, go to **New**, and then create a new **Text Document**.

3. Repeat the previous step for other available document or file types. Though no restrictions are placed on the amount, three files should be enough for this exercise.

4. Create a new process and add the **Get Special Folder** action to the workspace.

5. Set the **Special Folder Name:** field to **DesktopDirectory** and then store it in a variable.

   ![Screenshot of Properties of 'Get Special Folder' action dialog.](..\media\get-special-folder-exercise.png)

6. Using the **Get Files in Folder** action, set the **Folder** field to **%SpecialFolder%\Important**. This setting will select the folder that you previously created on the desktop.

   ![Screenshot of Properties of 'Get Files in Folder' action dialog.](..\media\get-files-in-folder-exercise.png)

7. Add the **Create Folder** action to the workspace.

8. In the **Create New Folder into** field, enter **%SpecialFolder%**.

9. In the **New Folder Name** field, enter **Backup Files**.

   ![Screenshot of Properties of 'Create Folder' action dialog.](..\media\create-folder-exercise.png)

10. Add the **Copy File(s)** action.

11. Set the **File(s) to Copy** field to **%Files%**, the **Destination Folder** field to **%New Folder%**, and the **If File(s) Exists** drop-down option to **Overwrite**.

    ![Screenshot of Properties of 'Copy Files' action dialog.](..\media\copy-files-exercise.png)

12. To create the log file, add the **Write Text to File** action and then set the **File Path** field to **%NewFolder%\Backup Log.txt**.

13. In the **Text to Write** field, add a message that will show that the process has run successfully.

    ![Screenshot of Properties of 'Write Text to File' action dialog.](..\media\write-text-to-file-exercise.png)

14. Add the **Rename File(s)** action and then set the **File(s) to Rename** field to **%NewFolder%\Backup Log.txt**.

15. In the **Rename Scheme** drop-down menu, select the **Add Date or Time** option.

16. Set the **Separator** drop-down option to **no separator** and the **DateTime Format** option to **dd.MM.yy_HH.mm**.

    ![Screenshot of Properties of 'Rename Files' action dialog.](..\media\rename-files-exercise.png)

    The completed process should resemble the following screenshot.

    ![Screenshot of the completed Main process.](..\media\completed-process-workspace-exercise.png)

17. Run the process.

After the run process has completed, you will have a new folder called **Backup Files** on your **Desktop**. The folder will contain all contents of the folder named **Important** and an additional text file called **Backup Log**, which will have the last date and time that the process has run appended to its file name.
