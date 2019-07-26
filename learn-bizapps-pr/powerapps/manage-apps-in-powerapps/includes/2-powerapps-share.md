You can share an app with specific users, groups, or your 
whole organization. When you share an app with other people, they can run it in a browser, from the Microsoft Dynamics 365 home 
page, or in Microsoft PowerApps Mobile for Microsoft Windows, Apple iOS, or Google Android.

Even better, you can give someone permission to update the app.

## Prepare to share an app

To complete the following steps, open the app that you want to share in **Edit** mode.

1. In PowerApps Studio, select the **File** menu and then select **App settings**. Give the app a meaningful name and a description so that your team knows what your app does and can easily find it in the apps list.

2. On the **File** menu, select **Save as** and then select **The cloud**.

    You must save an app to the cloud before you can share it.

3. Select **Save** and then select **Share this app**.

4. On the **Share** tab, specify the users or groups with whom you want to share the app. To add everyone in your organization, type **Everyone** and select **Everyone in Company Name**. If you need to share with a large group of users, a best practice is to share through an Azure Active Directory Security Group.

    By default, the user receives the User permission. If you want the user to also be able to edit the app, then 
    select the co-owner check box. The following is a description of both permissions:
    
    - **Co-owner** - Users can use, edit, and share the app, but can't delete or change the owner.
    - **User** - Users can view and use the app, but they can't change it.

    Security-group considerations
    - If you share an app with a security group, existing members of that group, and anyone who joins it, will have the permission that you specify for that group. Anyone who leaves the group loses that permission unless they belong to a different group that has access or if you give them permission as an individual.
    - Every member of a security group has the same permission for an app as the overall group does. However, you can specify greater permissions for one or more members of that group to allow them greater access. For example, you can give Security Group A permission to run an app, but you can also give User B, who belongs to that group, Co-owner permission. Every member of the security group can run the app, but only User B can edit it. If you give Security Group A Co-owner permission and User B permission to run the app, that user can still edit the app.

5. To notify users by email, leave the **Send an email invitation** check box selected.

    If you elect to notify the users by email, everyone you shared the app with will receive an email message that has a link to the app. People whom you granted **Co-owner** permission for the app will also receive a link to Edit App in PowerApps Studio.

6. Select **Share**.

    If you make and save changes to a shared app, the people whom you shared it with will see your changes as soon as you publish them. This can be useful if you improve the app, but it can also negatively affect users if you remove or significantly change features. Remember to create a notification plan for alerting your users of major updates. 

## Permissions and licensing

Basic information about permissions and licensing that you should be aware of are:

- Users and contributors need permissions to any data connections and gateways that a shared app uses. Some permissions come implicitly with the app, but you must explicitly grant others. If you create an app based on Common Data Service, you must also ensure that the users with whom you share the app have the appropriate permissions for the entity or entities on which the app relies. Specifically, those users must belong to a security role that can perform tasks such as creating, reading, writing, and deleting relevant records. In many cases, you'll want to create one or more custom security roles with the exact permissions that users need to run the app. You can then assign a role to each user as appropriate.
- People who have **Co-owner** permission also need a PowerApps P2 license to work directly with entities in Common Data Service.

Sharing an app is simple, and it's a great way to make an app that you find useful available to people across your organization.
