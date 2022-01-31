In the previous exercise, you created a business process flow that includes logical
branching for vehicles that were made in 1971 or before and all others that were made in
1972 and beyond. Now, you’ll enhance that flow by adding a simple instant flow in
Power Automate. Instant flows can connect to hundreds of cloud services, extending your business
process flow beyond data entry and basic logic. You'll create an instant flow that sends an email to
the store manager (you) when a new customer check-in record is created.

1. Sign in to [Power Automate](https://preview.flow.microsoft.com/?azure-portal=true) and select **My flows**.

1. Select **+ New** in the ribbon in the left corner of the screen.

1. Select the **Instant cloud flow** option.

    ![Screenshot of Power Automate with New selected and the Instant--from blank option highlighted.](../media/18-create-instant-flow-dialog.png)

1. Select the **Skip** button to open the cloud flow designer.

    ![Screenshot of the Build an instant flow dialog with Flow name and Choose how to trigger this flow options. The Skip button is highlighted.](../media/19-select-skip-button-enter-flow-designer.png)

1. First you need to define a trigger, or an event that will precipitate your flow. Search **Microsoft Dataverse** and select **When a row is added, modified, or deleted**.

    ![Screenshot of the search results for Dataverse with the When a record is created option highlighted.](../media/20-search-common-data-service.png)

1. Choose the change type **Added** and the table used in your business process flow, in this case **Customer Check In**. You must also choose a scope.
A scope determines whose actions trigger the flow, whether anyone in the organization, in your business unit, or yourself (user). For now, you can choose
**User** since you have yet to test this process. Once complete, select **+ New step**.

    ![Dataverse When a record is created trigger with the three values filled in and the New step button highlighted.](../media/21-fill-out-record-created-trigger.png)

1. Search for and select **Send an email (V2)**.

    ![Search for Send Email action by typing send email in search dialog.](../media/22-send-email-action.png)

1. Enter the following information into the **Send an email notification (V3)** action:

    - **To** - Enter your email address to receive an email and test the instant flow.

    - **Subject** - Enter **A record was added to the Customer Check In entity**.

    - **Email Body** - Enter **A new record for** and select the **First Name** and **Last Name** fields from the list of fields under the Dynamic content option, and then type **was entered today!**

1. Select **Save**.

    ![Send an email notification with values added for To, Subject, and Email Body.](../media/23-fill-out-send-email-action.png)

## Run the instant flow

1. Close the instant flow that you created and then select **My flows** and **Business process flows**.

1. Run the **Customer Check In** business process flow.

1. Enter some values in the first stage fields and then enter a value in the
**Name** field on the main screen (the field is on the **General** form under
the Business process flow diagram) so that values are in the record before you save it.

1. Save the record. An email will appear in your inbox similar to the one in the following figure.

   ![Received email notification message in Outlook email message.](../media/24-received-email-notification.png)

Congratulations, you’ve now created an instant flow that works with your business process flow.
