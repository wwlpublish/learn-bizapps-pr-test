## Share an app
Now that you know how to build an app, you'll learn how to share it. You can share an app with specific users or groups, or with your whole organization. When you share an app with other people, they can run it in a web browser from Microsoft Dynamics 365, or in Microsoft PowerApps Mobile for Microsoft Windows, Apple iOS, or Google Android. 

Even better, if you give someone contributor permissions, that person can also update the app.

### Prepare to share an app
You must save apps to the cloud before you can share them with anyone.

1. In PowerApps Studio, on the **File** menu, select **Save**.
1. Under **Save as**, select **The Cloud**. PowerApps apps must be saved to the cloud before they can be shared.
1. Give the app a meaningful name and description, so that your team knows what your app does and can easily find it in a list.
1. Select **Save**.
1. Select **Share this app**.
1. On the **Share** tab, specify the users or groups you want to share the app with. To add everyone in your organization, select the **Add everyone in my org** check box.
1. To notify users by email, select the **Send an email invitation** check box. Then everyone you shared the app with will receive an email that has a link to Dynamics 365. App contributors will also receive a link to web.powerapps.com.

    Only people who follow the link to Dynamics 365 will see the app there. But the app will also be in Microsoft AppSource. Anyone who didn't follow the link will have to add the app from AppSource to Dynamics 365 themselves.

1. In the **Shared with** list, in the **Permissions** list on the right, specify how the users or groups can interact with the app:

    * **Can edit**: Users can make changes to the app by using PowerApps Studio.
    * **Can use**: Users can view and use the app, but they can't make changes to it.

1. Select **Save**.

Keep in mind that if you make changes to a shared app, the people you shared it with will see your changes as soon as you save them. Although this can be great if you improve the app, it can also negatively affect other users if you remove or significantly change features.

### Permissions and licensing
We won't go into detail about permissions and licensing, but we want to cover a couple of basics related to sharing:

- Users and contributors need permissions to any data connections and gateways that a shared app uses. Some permissions come implicitly with the app, but others must be explicitly granted.
- If the app uses Common Data Service for Apps entities, users and contributors need access to the Common Data Service for Apps database. Contributors also need a PowerApps "P2" license if they work directly with entities.

Sharing apps is easy, and it's a great way to take an app that you find useful and make it available to people across your organization. 