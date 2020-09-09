The **Open SQL Connection** Action only requires one input, the **Connection String**. The connection string specifies all the information necessary to connect to a database, such as the driver used, the database, and server names as well as the username and password. 

The string can be entered manually or as a variable. When the Action connects to a database, it stores the connection into a SQL connection variable.

![open sql connection action properties](..\media\open-sql-connection-action-properties.png)

If the appropriate connection string is not known press the **ellipses** button to open the data link properties window. This tool helps the user compose the required connections string step by step. First, select the correct driver for the database under the **Provider** tab.

![data link properties](..\media\data-link-properties.png)

Next, under the **Connection** tab, enter the remaining details like the server name, the username, password, and database name. Press the test connection button to test that this connection string connects to a database successfully. Alternatively, the user can copy a ready-made connection string. 

![data link properties connection tab](..\media\data-link-properties-connection-tab.png)

It is also possible to specify a connection timeout in the **Advanced** tab.

![data link properties advanced tab](..\media\data-link-properties-advanced-tab.png)

Use the **Execute SQL Statement** Action to query the database. The Action can be configured by using the already established SQL connection and setting the SQL connection variable created by the previous action. 

Alternatively, it can connect to the database directly, using the same method described in the previous Action.

![execute sql statement action properties](..\media\execute-sql-statement-action-properties.png)

The **Close SQL Connection** Action requires the SQL connection variable and terminates the connection to the database. 

![close sql connection action properties](..\media\close-sql-connection-action-properties.png)
