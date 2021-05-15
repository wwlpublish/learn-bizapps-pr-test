Power Automate allows you to build automated workflows through a series of triggers and actions. Triggers act as a catalyst to begin a series of actions; they *trigger* your flow to begin. Dataverse acts as a scalable database but also offers rich metadata and built-in logic processes. Nevertheless, the triggers in Power Automate are built on the data that is stored inside Dataverse.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Dataverse triggers.](../media/dataverse-triggers.png)](../media/dataverse-triggers.png#lightbox)

The triggers in Dataverse are:

- **When a record is created** - Begins a flow when a record is created in a specified table in Dataverse. You can set additional logic to determine whether the actions are performed after grabbing the fields from the newly created row. This trigger could begin an approval process when a user creates a new purchase order or vacation request.

- **When a record is deleted** - Begins a flow when a record is deleted in a specified table. You could use this trigger to delete associated items in the same table or another one. For example, if a record was the main information in a purchase order and another table held the line items, you can delete the line items. Alternatively, you could store the deleted information in a secondary table for archival or until a manager approves deletion.

- **When a record is updated** - Begins a flow when a record is updated in a specified table. You could use this trigger to continue in a multilevel approval process or to update various users, such as the creator of the item, that changes have been made.

- **When a row is selected** - Adds a button to a specified table in Dataverse and allows you to begin a flow for a specific record. This trigger could be used as an archival flow or to perform actions on specific records.

Now that you have learned about the various triggers that are offered inside of Power Automate for Dataverse, you can learn how to use those triggers.
