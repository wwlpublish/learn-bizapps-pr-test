There are three techniques to add columns to a model table. You can:

-   Add columns to a view or table (as a persisted column), and then source them in Power Query. Of course, this option only makes sense when your data source is a relational database and, you have the skills and permissions to do so. Still, it's a good option because it supports ease of maintenance and allows reuse of the column logic in other models or reports.

-   Add computed columns (using M) to Power Query queries.

-   Add calculated columns (using DAX) to model tables.

Regardless of which technique you use, it results in the same outcome. Interestingly, report users can't determine the origin of a column. Typically, they're not interested in how the column was created, though they're concerned that it delivers the right data.

When there are multiple ways to add a column, you can consider using the approach that best fits your skills and that's supported by the language (M or DAX). Bear in mind, there's a preference to add computed columns in Power Query, whenever possible. It's because they load to the model in a more compact and optimal way.

When you need to add a column to a calculated table, you must create a calculated column there's no other way. Otherwise, we recommend you only use a calculated column when the calculated column formula:

-   Depends on summarized model data.

-   Needs to use specialized modeling functions that are only available in DAX like the RELATED or RELATEDTABLE functions. Specialized functions can also include the [DAX parent and child functions](https://docs.microsoft.com/dax/understanding-functions-for-parent-child-hierarchies-in-dax/?azure-portal=true), which are design to naturalize a recursive relationship into columns. For example, in an employee table, when each row stores a reference to the row of the manager (who is also an employee).