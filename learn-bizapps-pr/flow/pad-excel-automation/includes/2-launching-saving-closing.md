## Open an Excel file and create an instance

The first task in automating any Excel-related task is to create an Excel instance. 

An instance determines which application session Power Automate Desktop will interact with. Create instances by opening a locally stored or new Excel file or by attaching the process to an already opened file. These operations are achieved by the **Launch Excel** action or the **Attach to running Excel** action.

To open a new Excel file, under **Launch Excel**, select **with a blank document**.
 

![launch excel action properties](..\media\launch-excel-action-properties.png)
 

Alternatively, launch Excel with an existing file by changing the **Launch Excel** setting to **and open the following document**. Enter a **Document path**, or browse for and select a file.

<!--
![launch excel action properties continued](..\media\launch-excel-action-properties-continued.png)
-->

To view the Excel actions when the flow runs in real time, check the **Make instance visible** check box. The Excel window opens when the flow runs. If the checkbox isn't checked, Excel runs in the background. Expand the **Advanced** section, which includes an option to **Load add-Ins and macros** as the Excel file launches.
 

<!--
![launch excel properties advanced section](..\media\launch-excel-properties-advanced-section.png)
-->

Use an already opened Excel file as an instance with the **Attach to running Excel** action. With this action, specify the **Document name**.
 

![attach to running excel action properties](..\media\attach-to-running-excel-action-properties.png)


## Save and close an Excel file

You can save and close an Excel file only if the instance has already been determined. To save an Excel file,  use the **Save Excel** action. 

To save the document in its current path with its current filename, set the **Save mode** option to **Save document**. To save the document in a different path and/or under a different file name set the option to **Save document as**.
 

![save excel action properties](..\media\save-excel-action-properties.png)


Select **Save document as**, to show additional options to change the **Document Format** and to provide the new **Document path**.
  

![save excel action properties continued](..\media\save-excel-action-properties-continued.png)


Close a specific instance of Excel with the **Close Excel** action. Optionally, save the file with any of the **before closing Excel** options.

Use any of the options to save the document, and the action will function similarly to the **Save Excel** action, in addition to closing the document.
  

![close excel action properties](..\media\close-excel-action-properties.png)
