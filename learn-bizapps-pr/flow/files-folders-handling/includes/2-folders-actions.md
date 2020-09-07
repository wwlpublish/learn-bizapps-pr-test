The **Get Special Folder** Action is used to dynamically retrieve the path for directories whose paths are inconsistent among different workstations. Select the special folder whose path you would like to retrieve. The path will be displayed below, for reference. The Action outputs a variable, where the selected path is stored.

![Get Special Folder action properties](..\media\get-special-folder-action-properties.png)
 
There are numerous examples of special folders whose paths can be retrieved:

![Get Special Folder input drop down](..\media\get-special-folder-action-properties-continued.png)
 
The output of the Get Special Folder Action can then be referenced in the **Create Folder** Action, for instance. The input for this Action is the directory where the folder is going to be created, and the name of the new folder. 

In the screenshot below, the previously retrieved special folder is used as the directory for the new folder, which is going to be named Files.

![Create Folder action properties](..\media\create-folder-action-properties.png)
 
The output of this Action is of type Folder, and contains the following attributes:

![Folder Type Variable Properties](..\media\folder-type-variable-properties.png)
 
The **Copy Folder** Action requires the Folder to Copy and Destination Folder inputs. These can be provided as paths **(1)**, or as folder-type variables **(2)**. 

The **If Folder Exists** setting is the action to be taken if there is already a folder with the same name as the one you want to copy in the destination folder. Setting this to **Overwrite**, will overwrite the folder in the destination, or **Do not Copy** to take no action.

![Copy Folder action properties](..\media\copy-folder-action-properties.png)
 
Similarly, the **Move Folder** Action copies the folder to a new location. When moving a folder, however, it is deleted from its original location. The folder you wish to move, along with the destination folder are required inputs.

![Move Folder action properties](..\media\move-folder-action-properties.png)
 
 
The **Rename Folder** Action requires that you specify a folder and a new name.

![Rename Folder action properties](..\media\rename-folder-action-properties.png)
 
The **Delete Folder** and **Empty Folder** Actions only require one input; to specify the folder. When deleting a folder, it is deleted along with all of its contents, and when emptying a folder, only its contents are deleted.

The **Get Subfolders in Folder** Action retrieves a list of folders inside the specified folder. Required inputs are the parent folder. A **Folder Filter** can also be configured, to filter the output list by folder name. Include Subfolders can be checked to include additional layers of subfolders. The output is a list of folders.

![Get Subfolders in Folder action properties](..\media\get-subfolders-in-folder-action-properties.png)
 
In the **Advanced** tab, the Action can be set to fail if any subfolder is denied access to. The output can also be sorted sequentially by three fields. Checking the Descending box sorts the output by the selected field in descending order, as opposed to ascending if left unchecked.

![Get Subfolders in Folder properties Advanced tab](..\media\get-subfolders-in-folder-properties-advanced-tab.png)
 