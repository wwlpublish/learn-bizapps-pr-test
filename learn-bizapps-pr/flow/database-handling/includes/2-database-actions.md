The **Open SQL Connection** action only requires one input: the connection string. The **Connection String** field specifies all information that is necessary to connect to a database, such as the driver that is used, the database, server names, and the username and password.

The string can be entered manually or as a variable. When the action connects to a database, it stores the connection into a SQL connection variable.

![Screenshot of Properties of 'Open S Q L Connection' action with the Connection String property highlighted.](..\media\open-sql-connection-action-properties.png)

If the appropriate connection string is not known, select the ellipsis (**...**) button to open the **Data Link Properties** window. The data link tool helps the user compose the required connection string step by step. First, select the correct driver for the database under the **Provider** tab.

![Screenshot of the Process Designer with the ellipsis button next to Connection String highlighted and the Data Link Properties dialog highlighted.](..\media\data-link-properties.png)

Next, under the **Connection** tab, enter the remaining details such as the server name, the username, password, and database name. Select the **Test Connection** button to test that the connection string will connect to a database successfully. Alternatively, you can copy a ready-made connection string.

![Screenshot of the Data Link Properties Connection tab with the Test Connection button highlighted.](..\media\data-link-properties-connection-tab.png)

It is also possible to specify a connection timeout in the **Advanced** tab.

![Screenshot of the Data Link Properties Advanced tab with the Connection timeout property highlighted.](..\media\data-link-properties-advanced-tab.png)

Use the **Execute SQL Statement** action to query the database. The action can be configured by using the already established SQL connection and by setting the SQL connection variable that was created by the previous action.

Alternatively, the action can connect to the database directly, by using the same method that was described in the **Open SQL Connection** action.

![Screenshot of Properties of 'Execute S Q L Statement' action with the Connection Variable property set to %SQLConnection%.](..\media\execute-sql-statement-action-properties.png)

The **Close SQL Connection** action requires the SQL connection variable and will terminate the connection to the database.

![Screenshot of Properties of 'Close S Q L Connection' action with the S Q L Connection to close property set to %SQLConnection%.](..\media\close-sql-connection-action-properties.png)
