The **Get Files in Folder** Action works in a similar way to Get Subfolders in Folder. The path of the folder is a required input and can be specified as a variable. 

The **File Filter** is optional. You can add keywords, along with the asterisk (*) wildcard, and separate multiple terms with a semicolon (;). It is also possible to look in subfolders by checking the Include Subfolders box.

![Get Files in Folder action properties](..\media\get-files-in-folder-action-properties.png)
 
In the **Advanced** tab, similarly to Get Subfolders in Folder, the output can be sorted, and the Action can be set to Fail upon denial of access to any subfolder.

![Get FIles in Folder properties Advanced tab](..\media\get-files-in-folder-properties-advanced-tab.png)
 
>[!TIP]
>For example, if the file filter is set to
>*backup*; *.txt*
>Only text files (with the extension .txt) whose filenames contain the string backup will be stored in the list of files.

The **Copy File(s)** and **Move File(s)** Actions take as input a file, or a list of files, and a destination folder. The If File(s) Exists setting can be set to either overwrite or do not copy existing files of the same name.

![Copy Files action properties](..\media\copy-files-action-properties.png)
 
Similarly, the **Delete File(s)** Action only requires the file, or list of files as input.

The **Rename File(s)** Action contains many operations that can be performed on a filename. As with the previous actions, the required input is a file or list of files. Any additional requirements depend on the selected Renaming Scheme. 

For example, **Set New Name** will require a new name, with the option to remove the extension. Replace Text will require the text you would like to replace, as well as the text to replace it with. 

Changing the extension will require the new extension to be specified. If a file with the new name you have specified exists, you can choose to overwrite it, or perform no action.

![Rename Files action properties](..\media\rename-files-action-properties.png)
 
The **Read Text from File** Action stores text from a .txt file in a variable. The required input is a .txt file, and the file content can be stored as a single text value, or a list. In case a list is selected, each line of text in the file will be an item in the list. The encoding of the input file can also be selected from a list of options.

![Read Text from File action properties](..\media\read-text-from-file-action-properties.png)
 
A text file can also be written to with the **Write Text to File** Action. This action requires the path for the text file, and the text to append. You can also select to append a new line at the end of the written text. If the file exists, you can select to either overwrite the existing content, or append it to the file. 

![Write Text to File action properties](..\media\write-text-to-file-action-properties.png)
 
>[!NOTE]
>If you provide a path to a non-existent file under File Path, a file will be created with the contents specified in Text to Write.

The **Read from CSV File** Action is used to read data from a Comma-Separated Value (.csv) spreadsheet file. It requires the path to the .csv file, as well as the encoding of the file. The output is a DataTable type variable with the contents of the .csv file. 

In the **Advanced** tab, there are multiple options for handling the data in the .csv file. It is possible to trim (remove whitespaces from the beginning and end) of the value in each cell. If the first line is set to contain column names, it will not be stored in the output variable. Additionally, you change the columns separator in case a different symbol is used in the file. 

![Read from CSV File action properties](..\media\read-from-csv-file-action-properties.png)
 
With the **Write to CSV File** Action, you can write any DataRow or DataTable type variable to a .csv file. Specifying the path of the file, and the variable to write are required. 

In the **Advanced** tab, specify whether the first row of data includes column names (and should thus not be written to the file). If a file with the same name exists, the data can either be overwritten or appended. The columns separator can also be set.

![Write to CSV File action properties](..\media\write-to-csv-file-action-properties.png)
 
The **Get FilePath Part** Action requires a filepath as input and essentially breaks it down into multiple components, which are all stored as variables.

![Get Filepath Part action properties](..\media\get-filepath-part-action-properties.png)