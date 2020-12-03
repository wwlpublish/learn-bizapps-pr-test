To connect to a database, use the **Open SQL Connection** action. This action only requires one input: the connection string. The **Connection String** field specifies all information that is necessary to connect to a database, such as the driver, the database, server names, and the username and password. 

Enter the string manually or as a variable. When the action connects to a database, it stores the connection into a SQL connection variable.

![open sql connection action properties](..\media\open-sql-connection-action-properties.png)

<!--
If the appropriate connection string is not known, select the ellipsis (**...**) button to open the **Data Link Properties** window. The data link tool helps the user compose the required connection string step by step. First, select the correct driver for the database under the **Provider** tab.

![data link properties](..\media\data-link-properties.png)


Next, under the **Connection** tab, enter the remaining details such as the server name, the username, password, and database name. Select the **Test Connection** button to test that the connection string will connect to a database successfully. Alternatively, you can copy a ready-made connection string. 

![data link properties connection tab](..\media\data-link-properties-connection-tab.png)

It is also possible to specify a connection timeout in the **Advanced** tab.

![data link properties advanced tab](..\media\data-link-properties-advanced-tab.png)
-->

Query the fatabase using the **Execute SQL Statement** action. Under **Get connection by** select ** Configure the action using the already established SQL connection and by setting the SQL connection variable that was created by the previous action. 

Alternatively, the action can connect to the database directly, with the method described in the **Open SQL Connection** action.

![execute sql statement action properties](..\media\execute-sql-statement-action-properties.png)

To terminate the connection to the database, use the **Close SQL Connection** action. The SQL connection variable is required. 

![close sql connection action properties](..\media\close-sql-connection-action-properties.png)
