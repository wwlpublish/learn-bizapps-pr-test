## Share an app
Now that you know how to build an app, in this topic you will learn how to share it. You can share an app with specific users or groups, or you can share it with your entire organization. When you share an app with someone, they can run it from Dynamics 365 in a browser or in PowerApps Mobile for Windows, iOS, or Android. 

Even better, if you give someone contributor permissions, they can also update the app.

### Prepare to share an app
You must save an app to the cloud before you can share it with anyone. 
1. In PowerApps studio, on the **File** menu, select **Save**.
1. Under **Save as**, select **The Cloud**.  Powerapps need to be saved to the cloud before they can be shared.
1. Give the app a meaningful name and description so that your team knows what your app does and can easily pick it out of a list.
1. Select **Save**.
1. Select **Share this app**.
1. On the **Share** tab, specify the users or groups to share the app with.
1. To add everyone in your organization, select the **Add everyone in my org** checkbox.
1. To notify users by email, select the **Send an email invitation** checkbox. If you choose to notify users via email, everyone you shared the app with receives an email with a link to Dynamics 365. App contributors also receive a link to web.powerapps.com.  If someone doesn't follow the link to Dynamics 365, the app will not show up for them there. However, it will be in AppSource, but they'll have to add it to Dynamics 365 themselves.
1. In the **Shared with** list, specify in the **Permissions** list on the right, how the person can interract with the app:
    * **Can edit**: Users will be able to make changes to the  app using PowerApps Studio.

    * **Can use**: Users can only view and user the app, but cannot make changes to it.

10. Select **Save**.

Keep in mind that any changes you make to a shared app will flow through to the people you shared it with as soon as you save the changes. This can be great if you improve the app, but can also impact others if you remove or significantly change features.

### Permissions and licensing
We're not going to get into detail about permissions and licensing, but we want to cover a couple of basics related to sharing:

- Users and contributors need permissions to any data connections and gateways that a shared app uses. Some permissions come along implicitly with the app, but others must be explicitly granted.
- If the app uses Common Data Service for Apps entities, users and contributors need access to the Common Data Service for Apps database. Contributors also need a PowerApps "P2" license if they work directly with entities.

Sharing apps is easy, and it's a great way to take an app that you find useful and make it available to people across your organization. 

