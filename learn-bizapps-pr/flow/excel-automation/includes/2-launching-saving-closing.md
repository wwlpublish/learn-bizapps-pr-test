## Opening an Excel File and Creating an Instance

The first thing that is required to Automate any Excel-related task is to create an Excel instance. 

An instance determines which session of an application WinAutomation interacts with. Instances can be created either by opening a locally stored or new Excel file, or attaching the Process to an already open file. These operations are achieved by the **Launch Excel** Action or **Attach to Running Excel** respectively.

Opening a new Excel file is done by the **Launch Excel** Action, by selecting to Launch Excel **with a blank document**.
 

![launch excel action properties](..\media\launch-excel-action-properties.png)
 

Alternatively, Launching Excel with an existing file is done by changing the **Launch Excel** setting to **open the following document** and entering a **Document Path**.


![launch excel action properties continued](..\media\launch-excel-action-properties-continued.png)


If **Make Instance Visible** is checked, the Excel window will be opened during process execution. If the instance isn’t visible, it runs in the background.
In the **Advanced** tab, there is an option to **Load Add-Ins and Macros**, as the Excel file is launched.
 

![launch excel properties advanced tab](..\media\launch-excel-properties-advanced-tab.png)


An already opened Excel file can be used as an instance with the **Attach to Running Excel** Action. The **Document Name** will have to be specified.
 

![attach to running excel action properties](..\media\attach-to-running-excel-action-properties.png)


## Saving and Closing

An Excel file can be saved and closed only if the instance has already been determined. To save an Excel file, the **Save Excel** Action can be used. 

Set Save Mode to **Save document** to save the document in its current path with its current filename, or to **Save document as** to save the document in a different path and/or under a different filename.
 

![save excel action properties](..\media\save-excel-action-properties.png)


When choosing **Save document as**, there will be additional options to change the Document Format, and provide the new **Document Path**.
  

![save excel action properties continued](..\media\save-excel-action-properties-continued.png)


The **Close Excel** Action is used to close a specific instance of Excel. Additional options are available in case the file must also be saved.

 If any option to save the document is chosen, the Action functions similarly to the Save Excel Action, in addition to closing the document.
  

![close excel action properties](..\media\close-excel-action-properties.png)