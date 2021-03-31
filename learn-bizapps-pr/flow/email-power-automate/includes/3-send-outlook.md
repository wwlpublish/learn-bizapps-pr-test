Microsoft 365 Outlook (previously known as Office 365 Outlook) has a standard connector that allows you to show, send, delete, and reply to email messages, in addition to other tasks.

## Basic concept of Microsoft 365 Outlook connector

Microsoft 365 Outlook can be used as both actions and triggers in a Power Automate flow. Here's the list and their descriptions:

### Actions and triggers

| **Action** | **Trigger** |
|------------|-------------|
| Create contact (V2) | When a new email arrives (V3) |
| Create event (V4) | When an email is flagged (V3) |
| Send an email (V2) | When a new email arrives in a shared mailbox (V2) |
| Delete contact (V2) | When a new email mentioning me arrives (V3) |
| Delete email (V2) | When a new event is created (V3) |
| Delete event (V2) | When an event is added, updated, or deleted (V3) |
| Export email (V2) | When an event is modified (V3) |
| Find meeting times (V2) | When an upcoming event is starting soon (V3) |
| Flag email (V2) |  |
| Forward an email (V2) |  |
| Get attachment (V2) |  |
| Get calendar view of events (V2) |  |
| Get calendars (V2) |  |
| Get contacts folders (V2) |  |
| Get contacts (V2) |  |
| Get email (V2) |  |
| Get emails (V3) |  |
| Get event (V3) |  |
| Get events (V4) |  |
| Get mail tips from a mailbox (V2) |  |
| Get room lists (V2) |  |
| Get rooms (V2) |  |
| Get rooms in room list (V2) |  |
| Mark as read or unread (V3) |  |
| Move email (V2) |  |
| Reply to email (V3) |  |
| Respond to an event invite (V2) |  |
| Send an email from a shared mailbox (V2) |  |
| Send email with options |  |
| Set up automatic replies (V2) |  |
| Update contact (V2) |  |
| Update event (V4) |  |
| Update my contact's photo |  |

For full descriptions of actions and triggers, see the link in the Summary unit at the end of this module.

## Send an email action with dynamic content from SharePoint

The SharePoint connector has a trigger for new items in Power Automate flows. In this example, we're going to start a workflow process when a new item for a travel reimbursement request has been submitted. Email notifications are sent using Microsoft Outlook.

Here's a screenshot of the SharePoint list with the column types for Travel Reimbursement. SharePoint adds the **Created**, **Created By**, **Modified** and **Modified By** columns automatically.

> [!div class="mx-imgBorder"]
> [![Screenshot of the SharePoint list showing column types.](../media/3-1-columns.png)](../media/3-1-columns.png#lightbox)

Here's a screenshot of the choice column.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Settings > Edit Column dialog with column type set to Choice (menu to choose from).](../media/3-2-edit-column.png)](../media/3-2-edit-column.png#lightbox)

Go back to the Travel Reimbursement list and from the ribbon, select **Automate** then **Power Automate** and select **Create a flow**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Travel Reimbursement list with Create a flow selected.](../media/3-3-create-flow.png)](../media/3-3-create-flow.png#lightbox)

On the right, in Create a flow, select Start approval when a new item is added.

> [!div class="mx-imgBorder"]
> [![Screenshot of Create a flow with Start approval when a new item is added highlighted.](../media/3-4-start-approval.png)](../media/3-4-start-approval.png#lightbox)

Confirm the connection and select **continue.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Start approval when a new item is added dialog with the Continue button highlighted.](../media/3-5-continue.png)](../media/3-5-continue.png#lightbox)

Change the flow title to **Travel Reimbursement** and the list name.

> [!div class="mx-imgBorder"]
> [![Screenshot of the When a new item is created dialog.](../media/3-6-travel-reimbursement.png)](../media/3-6-travel-reimbursement.png#lightbox)

We need to modify this template to get the manager information. For that, drag the **Get my profile (V2)** action and drop it below the trigger.

Before:

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow with an arrow from Get my profile to the spot to drop it.](../media/3-7-before.png)](../media/3-7-before.png#lightbox)

After:

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow with Get my profile in its new location.](../media/3-8-after.png)](../media/3-8-after.png#lightbox)

Select **+** and select **Add an action.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Get my profile action with Add an action highlighted.](../media/3-9-add-action.png)](../media/3-9-add-action.png#lightbox)

Search for get manager and select **Get manager (V2).**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose an action dialog with the Get manager (V2) action selected.](../media/3-91-get-manager.png)](../media/3-91-get-manager.png#lightbox)

In **Get manager (V2)**, select **User Principal Name.**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Get manager (V2) action with Add dynamic content selected and User Principal Name highlighted.](../media/3-92-user-principal-name.png)](../media/3-92-user-principal-name.png#lightbox)

In the **Start an approval** action, for **Assigned To** select **Add dynamic content** and select **Mail** in **Get manager (V2).**

> [!div class="mx-imgBorder"]
> [![Screenshot of the Start an approval action with Add dynamic content selected and Mail highlighted.](../media/3-93-start-approval.png)](../media/3-93-start-approval.png#lightbox)

Select **Flow checker** to confirm there are no errors and then select **Save.**

You've successfully created an email action using Microsoft Outlook with dynamic content from SharePoint.
