A common use of Power Automate is to get a notification when something happens. Notifications can be emails, text messages, or push notifications on your phone.

In this unit, you'll create a flow that generates a push notification whenever you receive an email from your manager.

## Get the mobile app

It's easy to create a flow that sends push notifications to your mobile device. Keep in mind that you'll need the Power Automate mobile app to receive push notifications. The mobile app is available for [Google Android](https://play.google.com/store/apps/details?id=com.microsoft.flow), [Apple iOS](https://itunes.apple.com/app/apple-store/id1094928825), and [Windows Phone](https://www.microsoft.com/p/microsoft-flow/9nkn0p5l9n84).

If you're using an unsupported mobile device, consider using Short Message Service (SMS) messages (that is, text messages) instead of push notifications to receive notifications.

## Create a flow that sends push notifications

Power Automate comes with many templates to get you started with creating flows. Let's create a flow by using a template.

1. Sign in to [Power Automate](https://ms.flow.microsoft.com) by using your organizational account.

1. Select **My flows**.

1. Select **New**, and then select **Create from template**.

    ![Create from template](../media/Flow-notification-boss.png)

1. Scroll down, and select **Get a push notification when you receive an email from your boss**.

    You can also quickly find this template by entering *notifications* in the search field.

1. Select **Create Flow**. The flow will automatically render and open to the details and run history page. 

1. To edit the flow and see the steps which will be used to get your email profile and your boss's, select **Edit**.

1. Scroll to the bottom of the flow steps to find the **Check if it is my manager** section. Expand it by clicking on the title of that section. Your email address and your manager's are automatically filled in from the profile information that you entered. If your organization does not store your manager information in the active directory, you can manually input your manager's email here. Only administrators have the right to change this information so you cannot edit this portion of your profile data unless you have administrator rights.

1. In the **Send a push notification** section, select the title bar to change the text of the notification that you'll get when an email is received from your boss.

    ![Edit parameters for the push notification](../media/flow-check-my-manager.png)

1. To change the text of the email, in the **Text** field, enter a new message. You can also select dynamic content fields in the list.

    ![New message text](../media/flow-change-text.png)

1. Select **Save** to save and test the flow.

Now, when emails arrive from your boss, you'll get a push notification on your phone.
