When downloading or uploading files using the **Download File(s) from FTP** and **Upload File(s) to FTP** actions, you can specify the transfer type to be **ASCII**, **BINARY**, or **AUTO**. 

If you select **AUTO**, WinAutomation will use a defined list of file types to determine whether the file will be transferred in ASCII or binary mode.

![The Download File(s) from FTP action.](..\media\download-files-from-ftp-action-properties.png)

This list is also used by the **Download Folder(s) from FTP** and **Upload Folder(s) to FTP** actions to determine how to transfer the files contained into the folders.

To configure WinAutomation to treat a file type as ASCII: 

1.	Navigate to the **FTP** tab inside the **Settings** tab.

    ![The FTP tab.](..\media\ftp-tab-settings-options.png)

1.	Populate the respective field with the file type you want to treat as ASCII.

    ![A text-field to enter the file types to be treated as ASCII.](..\media\add-filtype-ftp-tab.png)

1.	Click on the **Add Filetype** button.

    ![A button to add file types in the ASCII list.](..\media\add-button-ftp-tab.png)

To remove a file type from the list, select it and click on the **Remove Selected** button. 

![A button to remove file types from the list.](..\media\remove-filtype-ftp-tab.png)

More information about FTP action can be found in the respective [WinAutomation documentation page](https://docs.winautomation.com/en/ftp.html). 