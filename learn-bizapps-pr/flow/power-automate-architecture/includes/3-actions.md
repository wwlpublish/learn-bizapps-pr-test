The actions used in Power Automate are defined by connectors. Each connector has its own set of actions. We will look at common actions with Power Automate and Dataverse.

The Common Data Service connector has the following actions:

- Create a new record
- Get record
- List records
- Update a record
- Delete a record

The Common Data Service (current environment) connector has the same actions but also many more:
- Create a new row
- Get a row by ID
- List rows
- Update a row
- Delete a row
- Relate rows
- Unrelate rows
- Perform a changeset request
- Download a file or an image
- Upload a file or an image
- Perform a bound action
- Perform an unbound action
- Predict using AI Builder models

The Common Data Service (current environment) connector can also allows the creation and use of child flows.

> [!NOTE]
> Common Data Service (current environment) has many advantages over the other connectors and should be your first choice with Power Automate.

## Retrieving data

When using "Get a row by ID" or "List rows" actions to retrieve data, specify only the column fields that are required for the flow.

With most Dataverse triggers, they provide all the fields and you don’t need to explicitly retrieve the record right after the trigger runs. However:

- The "When a record is selected" trigger doesn’t include N:1 lookup fields and a Get a row by ID action will be required.
- Delete only includes the ID of the row no other columns.

> [!NOTE]
> When referencing data previously retrieved earlier in a flow, the data is not updated automatically after the original step executes.

## Getting lists of data

The List rows actions can filter data using an OData query or a Fetch XML query to retrieve data.

![Screenshot showing the List rows action.](../media/3-list-rows-action.png)

When using the "List rows" action:

- Always filter the data on the List rows action not in a later step with Data Operation actions.
- FetchXML query filters can do more advanced criteria including related entities.
- Use Expand Query to include related rows in the result.
- Use the FetchXMl Builder tool in XrmToolBox to create your OData and Fetch XML queries.
- Enable pagination if you want more than one page of data. The page size is determined by the connector, , Dataverse is 1024. Pagination is enabled via the action settings. The limit is 100,000 rows.

> [!NOTE]
> Expand Query can help reduce the complexity of your flows, reduce the number of API calls made, and speed up your flows.

## Updating data

When using the "Update a row" action:

- Only include the columns that have changed. This avoids triggering other automation and audit logging.
- Use the null expression to clear values.
- If you are using an Alternate key, providing a GUID for the primary ID will perform an Upsert operation using the other data columns you supply.

## Calling custom actions

Microsoft uses the term action for several different things in processes; for a type of process and for steps within processes and flows. Custom actions are processes similar to classic workflows in their capabilities in terms of what can be performed with steps; in other words, action processes can use conditions, and can create and update rows.

Custom actions are reusable processes that can be initiated from code and Power Automate. Microsoft also includes several built-in actions such as:

- Set Word Template: Creates a Word document from a Word template.
- Add To Queue: Adds a record to a queue.

Power Automate cloud flows can call custom actions using the Common Data Service (current environment) connector. You should use "Perform a bound action" for action processes associated with a table, and use "Perform an unbound action" for action processes set as Global.
