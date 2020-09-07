This Process will demonstrate some Actions used to organize and manage files and folders. Specifically, the process will:

* Get the location of the Desktop folder for the current user
* Retrieve the contents of a folder on the Desktop
* Create a new folder on the Desktop
* Copy the contents of the first folder to the new folder
* Write to a text file
* Rename the text file to contain the current date and time in its filename

First, create a folder on your **Desktop**, and call it **Important**.

Open the new folder, right-click in the folder, go to **New** and create a new **Text Document**. Repeat the previous step for other available document or file types. There is no restriction, but three files should be enough for the demonstration.

Create a new Process and add the **Get Special Folder** Action to the workspace. Set the Action to retrieve Special Folder Name: DesktopDirectory and store it in a Variable.

![Get Special Folder exercise](..\media\get-special-folder-exercise.png)

Using the **Get Files in Folder** Action, set Folder to **%SpecialFolder%\Important**. This will select the folder you created on the Desktop in the previous step.

![Get FIles in Folder exercise](..\media\get-files-in-folder-exercise.png)
 
Add the **Create Folder** Action to the Workspace. In **Create New Folder** into enter **%SpecialFolder%** and into **New Folder name** enter **Backup Files**.

![Create Folder exercise](..\media\create-folder-exercise.png)
 
Next, add the **Copy File(s)** Action. Set **File(s) to Copy** to **%Files%**, Destination Folder to **%New Folder%** and **If File(s) Exists** to **Overwrite**.

![Copy Files exercise](..\media\copy-files-exercise.png)
 
To create the log file, add the **Write Text to File** Action and set **File Path** to **%NewFolder%\Backup Log.txt**. In **Text to Write**, add a message that will show that the process has run successfully.

![Write Text to File Exercise](..\media\write-text-to-file-exercise.png)
 
Lastly, add the **Rename File(s)** Action. Set **File(s) to Rename** to **%NewFolder%\Backup Log.txt**. In the **Rename Scheme** choose **Add Date or Time**. Set **Separator** to **no separator** and **DateTime Format** to **dd.MM.yy_HH.mm**.

![Rename Files exercise](..\media\rename-files-exercise.png)
 
The completed Process should look like this:

![process finished exercise](..\media\completed-process-workspace-exercise.png)
 
Run the process. After execution is complete, you will have a new folder called Backup Files on your Desktop. The folder will contain all the contents of the folder named Important, and an additional text file called Backup Log with the last date and time the process has run appended to its filename.