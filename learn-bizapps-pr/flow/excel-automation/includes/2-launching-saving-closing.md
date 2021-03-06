## Open an Excel file and create an instance

The first task in automating any Excel-related task is to create an Excel instance.

An instance determines which application session that WinAutomation will interact with. Instances can be created by opening a locally stored or new Excel file or by attaching the process to an already opened file. These operations are achieved by the **Launch Excel** action or the **Attach To Running Excel** action.

To open a new Excel file, go to the **Launch Excel > General** tab, and under the **Action Input** section, in the **Launch Excel** drop-down menu, select to open **with a blank document**.

![Screenshot of Properties of 'Launch Excel' action with Launch Excel set to "with a blank document" and highlighted.](..\media\launch-excel-action-properties.png)

Alternatively, you can launch Excel with an existing file by changing the **Launch Excel** setting to **and open the following document** and then entering a **Document Path**.

![Screenshot of Properties of 'Launch Excel' action on the Advanced tab with Launch Excel set to "and open the following document" and Document Path highlighted.](..\media\launch-excel-action-properties-continued.png)

If the **Make Instance Visible** check box is selected, then the Excel window will be opened during process implementation. If the instance isn’t visible, it will run in the background. The **Advanced** tab includes an option to **Load Add-Ins and Macros** as the Excel file launches.

![Screenshot of Properties of 'Launch Excel' action with Load Add-Ins and Macros highlighted.](..\media\launch-excel-properties-advanced-tab.png)

An already opened Excel file can be used as an instance with the **Attach To Running Excel** action. With this action, you will need to specify the **Document Name**.

![Screenshot of Properties of 'Attach To Running Excel' action with Document Name highlighted.](..\media\attach-to-running-excel-action-properties.png)

## Save and close an Excel file

You can save and close an Excel file only if the instance has already been determined. To save an Excel file, you can use the **Save Excel** action.

Set the **Save Mode** option to **Save document** to save the document in its current path with its current filename, or set the option to **Save document as** to save the document in a different path and/or under a different file name.

![Screenshot of Properties of 'Save Excel' action with Save Mode settings "Save document" and "Save document as" highlighted.](..\media\save-excel-action-properties.png)

When you select **Save document as**, additional options will be available for you to change the **Document Format** and to provide the new **Document Path**.

![Screenshot of Properties of 'Save Excel' action with Document Format and Document Path settings highlighted.](..\media\save-excel-action-properties-continued.png)

You can use the **Close Excel** action to close a specific instance of Excel. Additional options are available if the file must also be saved.

If you select any of the options to save the document, the action will function similarly to the **Save Excel** action, in addition to closing the document.

![Screenshot of Properties of 'Close Excel' action with Before Closing Excel settings "Do not save document," "Save document," and "Save document as" highlighted.](..\media\close-excel-action-properties.png)
