Use the **Get Text Length** Action to determine the length of a text value or a list of text values. The action measures the number of characters in the text value.
 

![get text length action properties](..\media\get-text-length-action-properties.png)

> [!NOTE]
> An alternative way to retrieve the length of a text variable, is to use the syntax:

%Text%.length

With the **Append Line to Text** Action add a line of text to a single text value or list of text values. The result is stored in a new text variable
 
![append line to text action properties](..\media\append-line-to-text-action-properties.png)

Use the **Get Subtext** Action to retrieve a specific portion of a text or list of text values. Set Start Index to retrieve text starting at a character position or the start of the text and Length to end at another position or at the end of the text. The Action stores its output in a text variable.
 

![get subtext action properties](..\media\get-subtext-action-properties.png)

The **Pad Text** Action can add a whitespace, a word, or a phrase before or after a text or a list, so that the resulting text reaches a specified length. Both the text to pad or the text used to pad the text can be typed in or entered as variables. The padded text is stored in a text variable.
 
![pad text action properties](..\media\pad-text-action-properties.png)


Use the **Trim Text** Action to remove whitespace from the beginning, end of a text string or both.
 
![trim text action properties](..\media\trim-text-action-properties.png)

With the **Change Text Case** Action change the text case found in a single text value or list of text values. The new text will be stored in a separate text variable.
 
![change text case action properties](..\media\change-text-case-action-properties.png)

# Text, Dates, and Numbers

There are four text actions dedicated to converting text values to and from the number and date time datatypes. There are cases where data that includes numbers has been extracted from a source such as a spreadsheet or webpage and has been stored as a datatable, datarow, or even a text value, but must be entered as a numerical value elsewhere. For example data is extracted from multiple columns of an Excel sheet into a Datatable type variable. some of the columns contain text values while others contain numbers. the numbers must be entered into multiple dropdown fields in a desktop application. if the numbers must be stored as numerical values, otherwise the data will not be processed correctly and cannot be entered.

To ensure that numbers are stored as numerical values use the **Convert Text to Number** Action. The Action requires as input single text items, text list items, datarow, or datatable items. In the case of list, datarow, or datatable items, the item’s index must be specified.
 
![convert text to number action properties](..\media\convert-text-to-number-action-properties.png)

Use the **Convert Number to Text** Action to achieve the reverse conversion. Type in a number or enter a numeric variable to convert to a Text Variable. Set the number of decimal places to include, and configure the digit grouping options.
 
Use the **Convert DateTime to Text** Action to convert a datetime value to text. The Action properties contain several options regarding the format of the datetime input. The most straightforward way to use the Action is to enter a datetime variable created through the platform created with the get current date and time action. By doing this, the datetime value is guaranteed to be in a recognizable format. Alternatively, a custom value can be used s input. In this case, the user must ensure that it is entered in a compatible datetime format. The Action can be configured to save datetime as text using one of the available formats, or a custom format.
 
![convert datetime to text action properties](..\media\convert-datetime-to-text-action-properties.png)

Use the **Convert Text to DateTime** Action to achieve the reverse conversion. Type in a text value or enter a variable that uses a compatible DateTime format. If the value entered uses a custom format, check the box in the properties and define the custom format in the field that appears underneath. 
 
![convert text to datetime action properties](..\media\convert-text-to-datetime-action-properties.png)

### Date Formatting
When displayed on their own these characters produce the following formats:
* d: The Short Date (04/02/2010) 
* D: The Long Date (Friday, April 02, 2010) 
* f: The Full Date Time - short Time (Friday, April 02, 2010 10:00 AM)  
* F: The Full Date Time (Friday, April 02, 2010 10:00:46 AM)  
* g: General Date Time - short Time (04/02/2010 10:00 AM) 
* G: The General Date Time - long Time: (04/02/2010 10:00:46 AM) 
* M: The Month and day of the month: ( April 02) 
* m: The Month and day of the month: ( April 02) 
* r: A Shorter Full date (Fri, 02 Apr 2010 10:00:46 GMT) 
* R: A Shorter Full date (Fri, 02 Apr 2010 10:00:46 GMT) 
* s: The Sortable Date Time (2010-04-02T10:00:46) 
* t: The short time (10:00 AM) 
* T: The Long Time (10:00:46 AM) 
* y: The Month and Year: (April, 2010) 
 
 
When used as a combination the characters have the following representation:
* d: The day of the month as a number from 1 to 31 (2) 
* dd: The day of the month as a number from 01 to 31 (02) 
* ddd: The abbreviated day of the week (Fri) 
* dddd: The full day of the week (Friday) 
* gg: The period era (A.D.) 
* h: The hour as a number from 1 to 12 (10) 
* hh: The hour as a number from 01 to 12 (10) 
* HH: The hour as a number from 00 to 23 (10) 
* m: The minutes as a number from 0 to 59 (0) 
* mm: The minutes as a number from 00 to 59 (00) 
* M: The month as a number from 1 to 12: (4) 
* MM: The month as a number from 01 to 12 (04) 
* MMM: The abbreviated month (Apr) 
* MMMM: The month (April) 
* s: The seconds as a number from 0 to 59 (46) 
* ss: The seconds as a number from 00 to 59 (46) 
* tt: The AM/PM designator (AM) 
* y: The last digit of the year (0) 
* yy: The last two digits of the year (10) 
* yyyy: The year (2010) 
* zz: The time zone (+02) 
* zzz: The time zone in full format (+02:00) 

## Additional Text Actions
The **Create Random Text** Action is ideal for generating passwords as it can be configured to generate text of a certain length and include upper-case and lower-case letters, digits, and symbols.
 
![create random text action properties](..\media\create-random-text-action-properties.png)

To combine a list of text values into a single text value, use the **Join Text** Action and enter a list variable as its input. Determine if the list items should be separated using a delimiter, like a space. If the list items will be separated, choose from one of the standard delimiters, or specify a custom delimiter.
 
![join text action properties](..\media\join-text-action-properties.png)

To separate a single text value into a list of items use the **Split Text** Action. Enter a value or a text variable as the input. Ideally, the text should include recognizable delimiters separating the items. Select one of the standard delimiters or enter a custom delimiter.

With the **Parse Text** Action, you can search a text value for a specific string of text. Set the Action to search for either the first, or all occurrences of the text string. Optionally, set the Action to **Ignore Case** (thus making the search case-insensitive). The output of the Action stores the position or list of positions as a numerical value (or list of numerical values) indicating the position(s) where the search string was found in the text.
 
![parse text action properties](..\media\parse-text-action-properties.png)

If the search string is not known beforehand, a regular expression can be searched for. Check Is Regular Expression to store the matched string of a Regular Expression in a new variable.
 
![parse text properties regex](..\media\parse-text-properties-regex.png)


The **Replace Text** Action can find a string in a text and replace it with another string or character. The Text to Parse and Text to Find are required inputs, as well as the Replacement Text. As with the Parse Text Action, the search can be configured to be case-insensitive, and regular expressions can be used for the search. Escape sequences enable the user to add characters such as a tab, or a new line into the replacement text.
 
![replace text action properties](..\media\replace-text-action-properties.png)

The **Escape Text for Regular Expression** Action can modify a regular expression so the characters that are used in regular expressions are escaped and are treated as literal characters in the string. This Action can be useful if a regular expression contains a variable with a text value. It can be used to escape the value in the variable, ensuring that the regular expression handles all the characters in the text.
 
![escape text for regular expression action properties](..\media\escape-text-for-regular-expression-action-properties.png)