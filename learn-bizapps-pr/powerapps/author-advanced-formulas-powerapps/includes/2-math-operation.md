When working with data in Power Apps, there are many reasons to perform
math operations across your data. This math can be counting functions or
aggregate functions. Both support tables of data. Not covered in this
module are additional math functions and operators for non-table data.
For a complete list of all functions, see [Formula reference for
Power Apps](https://docs.microsoft.com/powerapps/maker/canvas-apps/formula-reference).

Counting functions
------------------

Counting functions are used to compute the number of records in a table
of data based on criteria. They are often used to provide visual
indicators back to the user.

For example, you could use CountIf(TasksTable, Complete = "No") to count
the number of records in the TasksTable where the column Complete equals
No. Then based on the total, you could conditionally format the Color
property of a label or change the Visible property of an icon. These
types of visual indicators improve the user experience.

Power Apps includes the following counting functions:

-   **Count** counts the number of records that contain a
    number in a single-column table.

-   **CountA** counts the number of records that aren't
    blank in a single-column table. This function includes empty text
    ("") in the count.

-   **CountIf** counts the number of records in a table
    that are true for a logical formula. The formula can reference
    columns of the table.

-   **CountRows** counts the number records in a table.

**Count** and **CountA** only support single-column tables, and that is
the only argument they accept.

**CountIf** accepts a table and then the logical formula to process. It
then returns a count of all of the records that match the logical
formula.

**CountRows** accepts only a table as an argument and then returns a
count of the number of rows in that table. 
