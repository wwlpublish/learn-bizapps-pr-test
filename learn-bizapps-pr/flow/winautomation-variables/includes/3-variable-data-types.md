Every variable belongs to a specific type, according to its content. WinAutomation recognizes 17 distinct data types. 

Some of them can be used only with explicit actions or group of actions (for example, FTP connection), while others are widely used throughout the application (e.g., numbers). 

In the following list, there is a brief description of each data type. You can find more information about data types in the [WinAutomation documentation](https://docs.winautomation.com/data-types.html). 

**Simple data types**

- **Text** - Any kind of text, from email addresses to the text contents of a .txt file. 
- **Number** - Numerical values. Only this data type can be used in mathematical operations.
- **Boolean** - The value can be either **True** or **False**.

**Advanced data types**

- **List** - Collection of other items. It is the equivalent of a single-dimension array in programming terms. 
- **Data row** - A DataRow contains multiple values in a single, iterable row.
- **Data table** - Contains data in a tabular form. It is the equivalent of a two-dimensional array in programming terms. 
- **Custom object** – Contains pairs of properties and values, and can be easily translated into JSON format. 

**Instances**

- **Custom dialog instance** – Stores the instance of a custom dialog created through the **Display Custom Dialog** action. 
- **Browser instance** – Contains a browser instance created through the **Launch New Internet Explorer** or other browser launching actions.
- **Window instance** – Contains a window instance created through the **Get Window** action.
- **Excel instance** – Contains an Excel instance created through the **Launch Excel** action.

**Others**

- **Date time** - Contains date and time information.
- **FTP connection** - Contains an FTP connection created through the **Open FTP Connection** and **Open Secure FTP Connection** actions.
- **File** - Represents a file.
- **Folder** - Represents a folder.
- **Mail message** - Represents an email message. The **Retrieve Emails** action populates these variables.
- **OCR engine** – Contains an OCR engine created through the **Create OCR Engine** action.

## Data type properties

Some of the built-in WinAutomation data types have properties that are associated with the value stored in the variable. 

A property may contain a part of the information stored in the variable (for example, the day of a date) or an extra attribute describing the variable (for example, the size of a list).

The value of these properties can be accessed directly through the following notation: **%VariableName.PropertyName%**.

For example, if you have a list of files called **Files**, you can get the number of the stored files using the expression: **%Files.Count%**

![The Count variable property selected in the Display Message action's properties dialog.](..\media\display-message-action-properties-variable-property.png)

The data types that have properties are displayed in the following list. Extensive information about all the available properties can be found in the [WinAutomation documentation](https://docs.winautomation.com/en/data-type-properties.html).

- Texts
- Dates
- Lists
- Files
- Folders
- Mail messages
- FTP files
- FTP folders
- Data tables
- Data rows
- Custom dialog instances