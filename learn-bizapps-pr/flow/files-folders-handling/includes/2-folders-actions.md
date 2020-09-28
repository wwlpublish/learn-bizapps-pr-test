The **Get Special Folder** action is used to dynamically retrieve the path for directories whose paths are inconsistent among different workstations. On this page, you can select the special folder whose path you want to retrieve. The following screenshot displays the path for reference. The **Get Special Folder** action displays a variable where the selected path is stored.

![Get Special Folder action properties](..\media\get-special-folder-action-properties.png)
 
The following screenshot shows the numerous examples of special folders whose paths can be retrieved.

![Get Special Folder input drop down](..\media\get-special-folder-action-properties-continued.png)
 
The output of the **Get Special Folder** action can then be referenced in the **Create Folder** action, for instance. The input for this action is the directory, where the folder will be created, and the name of the new folder. 

The following screenshot shows that the previously retrieved special folder is used as the directory for the new folder, which will be named **Files**.

![Create Folder action properties](..\media\create-folder-action-properties.png)
 
The output of this action is of type Folder and contains the attributes that are shown in the following image.

![Folder Type Variable Properties](..\media\folder-type-variable-properties.png)
 
The **Copy Folder** action requires you to fill in the **Folder to Copy** and **Destination Folder** fields. As shown in the following screenshot, information in these fields can be provided as paths (**1**) or as folder-type variables (**2**). 

Use the **If Folder Exists** drop-down menu if a folder already exists with the same name as the one that you want to copy into the **Destination Folder** field. Setting this option to **Overwrite** will overwrite the folder in the destination, or you can set it to **Do not Copy** to take no action.

![Copy Folder action properties](..\media\copy-folder-action-properties.png)
 
Similarly, the **Move Folder** action will copy the folder to a new location. However, when you move a folder, it will be deleted from its original location. The folder that you want to move and the destination folder are required inputs.

![Move Folder action properties](..\media\move-folder-action-properties.png)
 
 
The **Rename Folder** action requires that you specify a folder and a new name.

![Rename Folder action properties](..\media\rename-folder-action-properties.png)
 
The **Delete Folder** and **Empty Folder** actions only require one input: to specify the folder. When you delete a folder, it will be deleted along with all of its contents, and when you empty a folder, only its contents will be deleted.

The **Get Subfolders in Folder** action will retrieve a list of folders inside the specified folder. Required input is the parent folder. A **Folder Filter** can also be configured to filter the output list by folder name. You can select the **Include Subfolders** check box to include additional layers of subfolders. The output is a list of folders.

![Get Subfolders in Folder action properties](..\media\get-subfolders-in-folder-action-properties.png)
 
In the **Advanced** tab, the **Get Subfolders in Folder** action can be set to fail if any subfolder has denied access. The output can also be sorted sequentially by three fields. Selecting the **Descending** check box will sort the output by the selected field in descending order, as opposed to ascending order if the check box is cleared.

![Get Subfolders in Folder properties Advanced tab](..\media\get-subfolders-in-folder-properties-advanced-tab.png)
 
