This unit describes the advanced data types: lists, data tables, and JSON custom objects.

## Lists

Lists are collections of items. Depending on the types of the individual list items, there can be lists of text values, lists of numbers, lists of files, etc. The list data type is the equivalent of a single-dimension array in programming terms. 

![The Edit Variable window.](..\media\edit-variable-window-lists.png)

You can create a list through the **Create New List** action and add an item to that list through the **Add Item to List** action. 

![The Create New List action's properties dialog.](..\media\create-new-list-action-properties.png)

You can also create a list through actions that generate lists as output. For example, the **Read text from file** action will return a list if you select to store the file’s contents as a list and **Get Files in Folder** action will return a list of files.

To retrieve a specific item of a list, you will have to use the following notation: **%VariableName\[ItemNumber\]%**

In the example below, we rename the first folder of the previously displayed folder list. Keep in mind that the **ItemNumber** should be 0 for the first item of the list.

![The populated Folder to Rename field in the Rename Folder action's properties dialog.](..\media\rename-folder-action-properties.png)

A common practice is to use a **For Each** action to iterate through the items of a list.

## Data tables

A data table contains rows and columns, and each item stored in the data table can be retrieved through its unique row and column number. You can think of data tables as lists: each item of the list is also a list. It is the equivalent of a two-dimensional array in programming terms. 

![The Edit Variable window.](..\media\edit-variable-window-data-tables..png)

There is no direct way to create a data table, but two actions generate a data table as output: the **Read from Excel** action and the **Execute SQL Statement** action.

To retrieve a specific item of a data table, you will have to use the following notation: **%VariableName\[RowNumber\]\[ColumnNumber\]%**

For example, in the following action we save the price of the first product inside a new variable. Keep in mind that the **RowNumber** and the **ColumnNumber** should be 0 for the first item (row or column).

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-data-tables.png)

If you loop through a data table with a **For Each** action, the variable that will contain the current iteration’s data is considered to be a data row. 

## JSON format - Custom objects

Custom objects are a type of variable in WinAutomation that allows users to generate and translate data in JSON format.

JSON (JavaScript Object Notation) is based on a subset of the JavaScript programming language. The main benefits of JSON are:

- It is easy for humans to read and write
- It is easy for machines to parse and generate, and
- It is completely language independent but uses conventions that are familiar to programmers.

These properties make JSON an ideal data-interchange language that is popular among web developers.

JSON supports the following structures:

- An object which can be seen as an unordered set of name/value pairs, like **{ "firstName": "John", "lastName": "Michael" }** inside curly braces and separated by commas. All names must be text values, while values can be almost anything. A colon (**:**) is used to separate the name from its corresponding value.

- An array which is an ordered collection of values, like \[1,2,3,4\] inside brackets and separated by commas. 

The combination of these two structures allows the creation of ordered lists of name/value pairs. 

![The Edit Variable window.](..\media\edit-variable-window-json.png)

You can access individual object values by using either the dot (**.**) notation (**Object.PropertyName**) or the bracket (**[]**) notation (**Object\["PropertyName"\]**).

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-json.png)

Custom objects follow the same functionality, using pairs of properties and values.

You can convert variables between both types using the Convert Custom Object to Json action and the Convert Json to Custom Object action.
