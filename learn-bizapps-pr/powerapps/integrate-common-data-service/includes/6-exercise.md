The purpose of this hands-on lab is to introduce extending entity forms with additional actions.

Exercises work best when you have some sample data to work with. Depending on the environment you are working with, you may want to install some sample data to assist with exercises. The Power Platform does provide the ability to add sample data as needed. If the environment you are working in does not have any sample data installed, follow the steps in [Add or remove sample data](https://docs.microsoft.com/power-platform/admin/add-remove-sample-data/?azure-portal=true) to install sample data into your environment.

## Learning objectives

At the end of these exercises, you will be able to accomplish the following:

* Create a new workflow for a case entity
* Configure a new workflow action for entity forms
* Add a user prompt for a workflow action
* Apply a conditional filter to an action button

**Estimated time to complete this exercise**: 15 to 20 minutes

## Before we begin

### Prerequisites

* System Administrator access to a Common Data Service instance with the Dynamics 365 Customer Service app installed.
* Provisioned Customer Self-Service, Community, or Partner portal template. If you do not have a Power Apps portal available, follow the [Create Portal](https://docs.microsoft.com/powerapps/maker/portals/create-portal/?azure-portal=true) instructions to create one.

## Scenario

Your organization has provisioned a Power Apps portal template to extend the case management capabilities of the Dynamics 365 Customer Service app.

The business would like to enable customers to place an active case on hold.

* When a portal user presses the button, they should receive a confirmation message.
* Only active cases that are not already on hold should display the interface to portal users.

## High level steps

To finish the exercise you need to complete the following tasks.

1. Create a real-time workflow for the Case entity that sets the case status to On Hold.
1. Add a workflow action button to the existing case edit form.
1. Add a confirmation message.
1. Add a filter criteria to show the button only for active cases that are not on hold.

## Detailed steps

### Create workflow process

Before we enable additional actions for the entity form, we need to create a workflow that is called by the form. We choose to create a real-time workflow for immediate visual feedback on the entity form.

1. Open the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true) and sign in.
1. Make sure the selected environment is the one with the portal solution installed.
1. Select **Solutions**.
1. Select **Common Data Services Default Solution**.
1. Select **... > Switch to classic**.
1. In the new window that opens, select **Processes**.
1. Select **New**.
1. Enter the following values:
   * **Process name**: Case On Hold
   * **Category**: Workflow
   * Clear **Run this workflow in the background**
   * **Entity** : Case
1. Press **OK**.
1. Select **As an on-demand process**.
1. Clear **Record is created**.
1. Select **Add Step > Change Status**.
1. Change the record status to: **On Hold**.
1. Press **Activate**.
1. Press **Close**.

### Create an action button

Once the workflow is created we can add a Workflow Action button to the Case entity form and configure this button to call the workflow.

1. Navigate to the [Power Apps maker portal](https://make.powerapps.com/?azure-portal=true).
1. Make sure correct environment is selected in the environment selector in the top right-hand corner.
1. From the list of Apps, locate and open the Portal Management app (Type = Model-driven).
1. Select **Entity Forms**.
1. Select **Customer Service - Edit Case**.
1. Select the **Additional Settings** tab.
1. Press **+ Workflow**.
1. Enter the following values:
   * **Workflow**: Select Case on hold
   * **Button Label**: On Hold
1. Press **Save**.
1. Do not close the window.

#### Test

1. Open your portal in a new browser window: `https://yourportal.powerappsportals.com`.
1. Sign in as an existing customer.
1. If you do not have a customer account, follow theses steps in the **Portals Management** app:
   1. Select **Contacts**.
   1. Select **New**.
   1. Switch form to **Portal Contact**.
   1. Enter the name of your choice.
   1. Press **Web Authentication**.
   1. Enter the username of your choice.
   1. Select **Login Enabled**.
   1. Press **Save**.
   1. Select **Change Password** and enter the new password of your choice.
   1. Add the **Authenticated Users** Web Role to the contact record.
   1. Sign out as a system administrator.
   1. Sign in as the new user.
1. Select **Support** on the top menu bar.
1. Select an existing case. If there are no existing cases, create and save a new case record.
1. The case should be **Active - In progress**.

   > [!div class="mx-imgBorder"]
   > [![Active case](../media/case-active.png)](../media/case-active.png#lightbox)

1. At the bottom of the case window is a new **On Hold** button.

   > [!div class="mx-imgBorder"]
   > [![On Hold button](../media/hold-button.png)](../media/hold-button.png#lightbox)
1. Press the **On Hold** button. The message "The workflow has been initiated" displays.
1. The window refreshes. The case status changes to **Active - On Hold**.

   > [!div class="mx-imgBorder"]
   > [![Case on hold](../media/case-hold.png)](../media/case-hold.png#lightbox)

1. Scroll down and verify that the **On Hold** button is still present.

### Enhance action button

Always having the workflow button visible does not make sense in certain scenarios, e.g. for disabled cases. We can enter some additional information to enhance the user experience.

1. Switch to the Portal Management app.
1. Select **Entity Forms**.
1. Select **Customer Service - Edit Case**.
1. Select the **Additional Settings** tab.
1. Select **Advanced Settings** and locate the **Workflow** action.
1. Enter the following values:
   * **Confirmation required**: Yes
   * **Confirmation**:  Are you sure you want to put this case on hold?
1. In **Filter Criteria** copy and paste the following XML:

   ```xml
   <fetch>
   <entity name="incident" >
      <attribute name="incidentid" />
      <filter type="and" >
         <condition attribute="statecode" operator="eq" value="0" />
         <condition attribute="statuscode" operator="neq" value="2" />
      </filter>
   </entity>
   </fetch>
   ```

   This FetchXML ensures that the button is only visible when the case is active (`statecode eq 0 (Active)`) and the status reason field is not On Hold  (`statuscode neq 2 (On Hold)`).

   > [!div class="mx-imgBorder"]
   > [![Action button enhancements](../media/button-enhancement.png)](../media/button-enhancement.png#lightbox)

1. Press **Save**.

#### Test action button

1. Open the portal and sign in as a user.
1. Select **Support**.
1. Create a new case, and enter data of your choice.
1. Press **Save**.
1. Confirm that the status is **Active - In Progress** and the **On Hold** button is visible.
1. Press **On Hold**. The confirmation displays.

   > [!div class="mx-imgBorder"]
   > [![Confirmation prompt](../media/confirmation.png)](../media/confirmation.png#lightbox)

1. Press **Cancel**.
1. Press **Close case**, and select **Yes** when prompted.
1. The case status should say **Resolved - Problem Solved**.
1. Only the **Reopen Case** button is visible.

## Additional exercise

You may want to add a **Resume** workflow and an action button to the form. The action button should only be visible when the case is on hold.

You see now how Power Apps portals make it easy to extend entity forms, effectively converting simple data entry forms into a part of a web app.
