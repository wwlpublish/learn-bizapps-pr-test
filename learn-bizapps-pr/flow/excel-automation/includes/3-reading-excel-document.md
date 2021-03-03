With the **Read from Excel Worksheet** action, you can read and extract data from an Excel document.

After specifying an instance of Excel, you can specify the range of data that you want to read. Set the **Retrieve** option to **Single Cell’s Value** to retrieve the contents of a single cell, and then specify the **Cell Location** with the **Column** and **Row** properties.

![Screenshot of Properties of 'Read from Excel Worksheet' action with Retrieve set to "Single Cell's Value," and with Column and Row highlighted.](..\media\read-from-excel-action-properties.png)

Alternatively, you can set the **Values from a Range of Cells** option to extract an entire table of data, which you can define by the coordinates in the **Range Starts At** and **Range Ends At** properties. This output will be of a **DataTable** type variable.

![Screenshot of the same dialog with Retrieve set to "Values from a Range of Cells," and with Range Start and End Columns and Rows highlighted.](..\media\read-from-excel-action-properties-continued.png)

The column can be specified by its letter or corresponding number, for example, you can enter **column E, row 8** or **column 5, row 8** for cell E8.
The last option, **Values from Selection**, will retrieve the values of the currently selected cells.

Cell contents are stored in variables based on their type. For example, a date will be stored as a **DateTime** variable. To store all data as text, select the **Get Cell Contents as Text** option in the **Advanced** tab.

![Screenshot of Properties of 'Read from Excel Worksheet' action Advanced tab with Get Cell Contents as Text highlighted.](..\media\read-from-excel-properties-advanced-tab.png)

The **Get First Free Column/Row from Excel Worksheet** action is useful in helping to determine the size of the data in the Excel document when you want to select rows and columns dynamically and the number of rows and columns is unknown.

The numbers of the first free row and column are stored as variables and you can reference them when specifying the range of information that is to be extracted with the **Read from Excel Worksheet** action.

![Screenshot of Properties of 'Get First Free Column/Row from Excel Worksheet' action with Store First Free Column and Row properties set.](..\media\get-first-free-row-column-excel-action-properties.png)

To select all data in an Excel worksheet, in the **Range Starts At** parameters, specify the range to start at column 1, row 1. Then, in the **Range Ends At** parameters, specify **Column** as **%FirstFreeColumn-1%** and **Row** as **%FirstFreeRow-1%**.

![Screenshot of Properties of 'Read from Excel Worksheet' action with Range Starts and Range Ends at properties set.](..\media\read-from-excel-action-properties-example.png)
