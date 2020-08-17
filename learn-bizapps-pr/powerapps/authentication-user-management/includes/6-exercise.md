The purpose of this hands-on-lab is to introduce the Power Apps portal invitation-based user registration process.

The exercises work best when you have some sample data to work with. Depending on if the environment you are working with, you may want to install some sample data to assist with exercises. Dynamics 365 does provide the ability to add sample data as needed. If the environment you are working in does not have any sample data installed, follow steps in [Add or remove sample data](https://docs.microsoft.com/power-platform/admin/add-remove-sample-data/?azure-portal=true) to install the sample data into your environment.

## Learning objectives

At the end of these exercises, you will be able to accomplish the following:

* Customize invitation template
* Create and send invitations to contacts to register
* Redeem invitations
* Extend invitation process by custom workflow

**Estimated time to complete this exercise**: 10 to 15 minutes

## Before we begin

### Prerequisites

This exercise requires the following:

1. A System Administrator access to Dynamics 365 instance with Dynamics 365 for Customer Service solution installed.
1. Provisioned Customer Self-Service, Community, or Customer Power Apps portal.
1. Enabled and working server-side email synchronization.

When you provision a Dynamics 365 for Customer Engagement trial, Office 365 licenses are not provisioned automatically and the email integration will not work. To enable server-side email synchronization:

> [!IMPORTANT]
>
> You must be an Office 365 Global Administrator to complete this configuration

1. Navigate to the [Admin portal](https://portal.office.com/adminportal/?azure-portal=true).
1. Select **Billing > Purchase Services**.
1. Locate **Office 365 E3** product and select **Get free trial** option.
1. Assign Office 365 license to your user account
1. Open [Power platform admin center](https://aka.ms/ppac/?azure-portal=true).
1. Select **Environments**, select your environment, click **Settings**.
1. Select **Mailboxes**.
1. Open your mailbox record, select **Approve Email**.
1. Select **Test & Enable Mailbox**.
1. Ensure that **Outgoing Email Status** field has **Success** value.

## Scenario

Your organization has been using Dynamics 365 for Customer Engagement for some time and have been recording information about customers and suppliers. You have provisioned and configured Power Apps portal. You would like to invite one of your suppliers responsible for your web sites to register as administrative portal user so that they are able to sign-in and administer portal using front-end interface.

## High-level steps

To be able to send invitations to your customers, and for them to be able to redeem the invitations, you need to complete the following tasks.

* Modify Send Invitation template
* Select a contact and create an invitation
* Ensure that invitation contains required information
* Send invitation to the contact

## Detailed steps

### Create a test contact

1. Open [Dynamics 365 Home](https://home.dynamics.com/?azure-portal=true).
1. Select **Power Apps portals** app.
1. Select **Contacts** then click **New**.
1. Create a new record for Nancy Davolio. Fill in her first name, last name and email address (*use an email address where you can receive the email*).
1. Click **Save**.

### Customize workflow

The workflow process sending the invitation email is a generic process and needs to be customized prior to the use.

1. Open the [Power Apps portal](https://web.powerapps.com/?azure-portal=true).

1. Select **Solutions** then locate and select **Default Solution**.

1. Change filter from **All** to **Processes**.

1. Locate and open the **Send Invitation** workflow process.

   > [!TIP]
   >Use search to locate the process

1. Deactivate the workflow.

1. Select **Set properties** for the step **Create an email to act as an email template**.

1. Enter the **Subject** as **Join our community**.

1. Replace the content of the email template with the following. Use the workflow editor to insert values for the field **First Name** from **Invited Contact** and use the hyperlink button to insert the link and **Encoded Invitation Code** value.

   ```al
   Dear {First Name(Invite Contact (Contact));customer}

   invites you to join our community. To redeem your invitation, please follow <hyperlink><name>this link</name><value>https://yourportalurl.powerappsportals.com/register/?returnurl=%2f&invitation={Encoded Invitation Code(Encode Invitation Code)}</value></hyperlink>

   Best regards
   Contoso Team
   ```

1. Activate the workflow.

### Create and Send Invitation

1. Open the Nancy Davolio contact record.
1. Select **Create Invitation**.
1. The invitation will be pre-populated. Click **Save**.
1. Under **Assign to Web Roles** select **Add Existing Web Role**.
1. Search and add **Administrators** role.
1. Select **Flow > Send Invitation**. Confirm.

### Redeem Invitation

1. Open the mailbox for the email you used for Nancy Davolio.

1. Locate and open the invitation email.

   > [!NOTE]
   >Server-side synchronization may take up to 15 minutes to synchronize and send the email

1. Click the link in the email.

1. The **Redeem Invitation** page will open.

1. Select **Register**.

1. Enter username **nancyd** and then a password of your choice.

1. Select **Register**.

1. Your account will be registered and you will be signed-in automatically and redirected to the profile page. Note that front-side editing toolbox will appear and you see **Edit** button when hovering over the elements of the page. That indicates that you have been automatically assigned the role with sufficient front-side editing privileges (Administrators in our case).

1. Switch to Power Apps portals App.

1. Select **Invitations** then select **Completed Invitations** view.

1. Confirm that the invitation **Nancy Davolio** is listed.

1. Open the invitation and confirm that **Status Reason** is now **Redeemed**.
