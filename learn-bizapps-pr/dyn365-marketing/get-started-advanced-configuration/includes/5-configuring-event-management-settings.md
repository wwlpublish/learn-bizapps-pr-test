The event management settings let you set up the connections to your webinar provider accounts and set up a few defaults for event
administration.

### Webinar providers

Microsoft does not provide webinar hosting services, so to run a webinar, you must sign up with a third-party provider and then configure Dynamics 365 for Marketing to connect to that provider. Microsoft has
partnered with On24, so Dynamics 365 is prepared to work with On24 right out of the box. Before you can run a webinar, you will need to set up an account with On24.

Each webinar provider that you use must have a record listed on the **Webinar** providers page. For each account that you have with your webinar provider, you must also set up a **Webinar configuration**
record.

### Webinar configurations

After you have set up an account with your webinar provider and set up the provider as described in the previous section, you must enter your account details to enable Dynamics 365 for Marketing to authenticate and interact with it. Even if you use only one webinar provider, you might have several accounts with that provider, and can configure each of them as needed.

> [!Note]
> Each time that you set up an event or session as a webinar (or hybrid), you must choose a webinar configuration. This is how you can control which account you'll be using for that event or session.

To configure a webinar account:
1. Go to **Settings** \> **Advanced settings** \> **Event management** \> **Webinar configurations**
2. To edit an existing configuration, select it from the list. To create a new configuration, select **New**. (You can also delete or deactivate a record by selecting it in the list and then selecting the appropriate button on the command bar).
3. Enter the following:
- **Name** - Enter a name for the account.
- **Webinar provider** - Select the name of the webinar provider record (set up as described in the previous section).
- The following read-only information is also provided here, some of which may be useful for troubleshooting:
    - **Terms of service** - Displays the URL where your provider lists their terms of service. This value comes from the selected **Webinar provider** record. Select the globe button to open this URL in a new browser tab.
     - **Privacy policy** - Displays the URL where your provider details their privacy policy. This value comes from the selected **Webinar provider** record. Select the globe button to open this URL in a new browser tab.
     - **Last metrics update** - Shows the last date and time that your provider returned usage statistics (such as attendance records) to Dynamics 365.
     - **Provider service status** - Shows the current status of the provider service and your connection to it.
     - **Message** - Displays a custom message sent by the provider (typically related to the displayed status).

- Open the **Credentials** tab
    - If you are editing an existing configuration and need to change your credentials, then set **Update credentials** to **Yes** to expose the credentials settings.
    - If you are creating a new configuration, then the credentials settings are already shown here.

- Make the following settings:
    - **Client ID**, **Access token key**, and **Access token secret** - These values identify your account and provide authentication (sign-in) credentials for accessing it and communicating with your webinar provider. You should have received these values when you signed up for the account. Please contact your webinar provider if you need help finding these values.

4. When finished, click **Save & Close**.

### Event administration

The event administration settings are optional settings that allow you to set up standard options for your events, including email options, email templates, and default payment gateway. 

To set your event administration options:

1. Go to **Settings** \> **Advanced settings** \> **Event management** \> **Event administration**
2. To edit an existing configuration, select it from the list; to create a new configuration, select **New**. (You can also delete or deactivate a record by selecting it in the list and then selecting the appropriate button on the command bar)
3. Enter the following: 
	- **Name** - Enter a name for the current event-administration record.
	- **Send mail to purchaser** - Set to **Yes** if you'd like the system to send an automatic email to the purchaser each time that an attendee registers for an event.
	- **Email template for purchaser** - Choose the (hard-coded) email template to send to the purchaser when **Send mail to purchaser** is enabled.
	- **Send mail to event attendee** - Set to **Yes** if you'd like the system to send an automatic email to each new contact that is registered for an event. This includes both self-registering contacts (if allowed) and contacts registered by another purchaser.
	- **Event template for event attendee** - Choose the (hard-coded) email template to send to each registrant when **Send mail to event attendee** is enabled.

> [!NOTE]
> The email templates that you choose with these settings are hard coded, so you can't customize or translate their content. If you require custom messaging, then set up a customer journey with an event, trigger, and email tiles