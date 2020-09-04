If the Excel document has multiple worksheets, we may need to use the **Set Active Excel Worksheet** Action, if the Worksheet opened by default is not the one we require. The Worksheet can be specified either by name or index.
  

![set active excel worksheet action properties](..\media\set-active-excel-worksheet-action-properties.png)


To get the names of all the Worksheets in a document, use the **Get Excel Worksheets** Action. The output will be a list with all the worksheets in the Excel document.
  

![get all excel worksheets action properties](..\media\get-all-excel-worksheets-action-properties.png)


The **Get Active Excel Worksheet** Action retrieves both the name and index of the currently active worksheet.
  

![get active excel worksheet action properties](..\media\get-active-excel-worksheet-action-properties.png)


Worksheets can also be added, renamed, and deleted, using the appropriate Actions. You will need to provide the name of the Worksheet, and the Excel instance.