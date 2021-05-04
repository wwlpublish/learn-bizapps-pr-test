While triggers start a flow in Power Automate, actions are exactly what they sound like, the actions the flow will perform once triggered.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Dataverse actions.](../media/dataverse-actions.png)](../media/dataverse-actions.png#lightbox)

**Create a new record** - This action allows you to input a new row of data into a table. It is important to remember that you don't need to have a Dataverse trigger to use Dataverse actions, so you could create a record after other actions such as holding a log of information when specific emails are sent.

**Get record** - This action allows you to find a specific record. If you had a child item (such as lines in a purchase order), this would allow you to fetch the parent item (the main information in the purchase order).

**List records** - This action allows you to fetch multiple records such as all the child items associated with a parent item (such as line items associated with a purchase order). You can then perform further actions on those items.

**Update a record** - This action allows you to make changes to a specific record such as updating a status once an approval process has completed.

**Delete a record** - This action allows you to delete a row of information. In the example we used in the triggers, you could create a flow triggered by the deletion of the main purchase order information, use the action List records to find all the line items (or child items) associated with that purchase order and then use this action to delete those.

Dataverse actions in Power Automate allow you to create robust processes surrounding your data.
