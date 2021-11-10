In this exercise, you will be configuring live chat for **Dynamics 365 Omnichannel for Customer Service**. Omnichannel for Customer Service offers a suite of capabilities that extend the power of Dynamics 365 Customer Service Enterprise to enable organizations to instantly connect and engage with their customers across digital messaging channels.

In the following tasks, you will complete the following:

1. Assign Omnichannel agent security role

1. Create an Application User using the **MCH Application Id** and your **Bot ID**

1. Configure Queues for Bot and Agent Users

1. Configure a Context Variable and Routing rule to route the message either to a Bot or Agent.

## Task 1: Assign Omnichannel Agent Security Role

1. While in the In-Private or Incognito window, navigate to <https://make.powerapps.com>.

1. Select your environment from the upper right **Environment** drop-down.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Environment page navigation bar.](../media/29-enviornment.png)](../media/29-enviornment.png#lightbox)

1. Select the **gear icon** in the upper right corner and navigate to **Advanced Settings**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Environment Setting menu with Advance Settings selected.](../media/30-advanced-settings.png)](../media/30-advanced-settings.png#lightbox)

1. A new window should open and navigate to Dynamics 365. If loading takes a while, reload the page. It will land you in the Business Management section of Dynamics 365.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Dynamics 365 Business Management section.](../media/31-business-management.png)](../media/31-business-management.png#lightbox)

1. On the top command bar next to Dynamics 365, select **Settings** to open the drop-down, then select **Security** in the third column under System.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Business Management Settings page with the Security option highlighted in the System menu.](../media/32-security-settings.png)](../media/32-security-settings.png#lightbox)

1. Under Security, select **Users**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the System Security Users option.](../media/33-security-users.png)](../media/33-security-users.png#lightbox)

1. Switch the view drop-down from Omnichannel Users to **Enabled Users** for the grid view so that your user will show in the list.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Omnichannel Users menu with Enabled Users option highlighted.](../media/34-enabled-users.png)](../media/34-enabled-users.png#lightbox)

1. While in the Enabled User list, scroll to **find your user** or use the **Search** bar.

    > [!NOTE]
    > If you are in an official training, search for you assigned user--IAD User \[x\]*

    > [!div class="mx-imgBorder"]
    > [![Screenshot of searching for user in enabled user list](../media/35-search-bar.png)](../media/35-search-bar.png#lightbox)

1. Select your user for the training and select **Manage Roles** on the top command bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of te Dynamics 365 Settings Manage Roles menu with the Omnichannel agent Role name selected.](../media/36-manage-roles.png)](../media/36-manage-roles.png#lightbox)

1. Select the Omnichannel Agent roles to assign to your user and select **OK**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Manage User Roes with the Omnichannel agent Role Name selected.](../media/37-manage-user-roles.png)](../media/37-manage-user-roles.png#lightbox)

**Congratulations!** You assigned the proper omnichannel agent role to your user to allow you to be a live agent in omnichannel.

## Task 2: Create Health Bot User in Dynamics 365 Customer Service

We need two users to configure in Omnichannel for Dynamics 365 Customer Service:

- **Health Bot User** - This is the Azure Health Bot user we created in the previous exercise.

- **Omnichannel Agent** **User** -This is your current user whom you are logged into Dynamics 365. This will allow you to be a live agent in Customer Service who receives messages from portal users through Azure Bot escalations.

In this task, you'll create a **Bot User** which helps connect **Azure Health Bot** with **Omnichannel live Chat**.

1. While in Dynamics 365 in the User page, switch the view to **Application Users**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Search results menu with Application Users option selected.](../media/38-application-users.png)](../media/38-application-users.png#lightbox)

1. Select (**+) New** button to create a new Application User.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Settings Application Users menu.](../media/39-new-application-user.png)](../media/39-new-application-user.png#lightbox)

1. Change the **form type** from User to **Application User** above the New User name.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the User dropdown menu with the Application User option selected.](../media/40-application-user.png)](../media/40-application-user.png#lightbox)

1. You'll see a new form appear that aligns to an Application User.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Application User new form Summary Account and User Information.](../media/41-new-user-form.png)](../media/41-new-user-form.png#lightbox)

1. On the **New User** record, enter or select the following information:

    a.  **Application ID**: This is the Application (client) ID you obtained in the Azure portal for the supplied MCH Application ID.

    b.  **User type**: Select **Bot application user**. This will *display a new field* to store the Bot application ID.

    c.  **Bot application ID**: This is the Azure Health BotId you copied when enabling the Teams channel. This field is displayed once the User Type is selected to be Bot application user.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New User record with the Bot Application ID included.](../media/42-bot-application-identification.png)](../media/42-bot-application-identification.png#lightbox)

1. Select **Save**. It will auto populate the other values in the record.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Application User form with auto filled Account and User information.](../media/43-saved-summary.png)](../media/43-saved-summary.png#lightbox)

1. Select **Manage Roles** on the command bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Application User page with the Manage Role option highlighted in the top navigation bar.](../media/44-application-manage-roles.png)](../media/44-application-manage-roles.png#lightbox)

1. Assign the **Omnichannel Agent** **role** to the Bot User as you did for your own user in the previous task. This will allow the bot to act as an omnichannel agent like your user.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Manage User Roles screen with the Omnichannel agent option selected.](../media/44-omnichannel-agent.png)](../media/44-omnichannel-agent.png#lightbox)

**Congratulations**! You successfully created a Bot User and assigned to it the Omnichannel Agent role.

## Task 3: Create and Configure Omnichannel Queues

In this task, you'll create and configure the omnichannel queues necessary to communicate with the correct bot or agent depending on the situation.

1. In <https://make.powerapps.com/>, open the **Omnichannel Administration** app.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Apps menu with the Omnichannel Administration option selected.](../media/45-omnichannel-administration.png)](../media/45-omnichannel-administration.png#lightbox)

1. Select **Queues** on the left navigation bar.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Queues and Users menu with the Queues option selected.](../media/46-queues.png)](../media/46-queues.png#lightbox)

1. Open **Default Messaging Queue**.

    > [!div class="mx-imgBorder"]
    > [!Screenshot of the Omnichannel queues with the Default messaging queue selected.](../media/47-default-messaging.png)](../media/47-default-messaging.png#lightbox)

1. We'll now associate the Default messaging queue with the Bot User so it will respond to incoming messages from customers without agent (human) intervention.

    Select **Add Existing User** on the **User (Agents)** subgrid to add the Bot user you previously created.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the default messaging queue Summary tab.](../media/48-add-existing-user.png)](../media/48-add-existing-user.png#lightbox)

1. In the Lookup Records pane, search for your **Bot User** (MCHApplicationId) created in the earlier task.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Lookup Records with MCH in the search feature and MCH user results returned.](../media/49-lookup-records.png)](../media/49-lookup-records.png#lightbox)

1. **Select** **the** **record** from the list and click **Add**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Lookup Records with MCH Application record and the Add button.](../media/50-add-lookup-records.png)](../media/50-add-lookup-records.png#lightbox)

1. You should now see the Bot User (MCH Application ID) in the Users (Agents) list. If your current user is also in the subgrid, remove it.

    > [!NOTE]
    > If your user does not populate after adding, make sure you have assigned the bot user the correct omnichannel agent security role from the previous task (it may take up to 15 minutes for changes to take effect)*

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Default messaging queue Summary page with Name, Priority and Queue type populated.](../media/51-default-messaging-summary.png)](../media/51-default-messaging-summary.png#lightbox)

1. Go back to the **Omnichannel queues** grid. Click **+** **New** to create a new Queue.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Omnichannel queue menu with the New button highlighted in the top navigation bar.](../media/52-new-omnichannel-queues.png)](../media/52-new-omnichannel-queues.png#lightbox)

1. Give the new Queue the following details:

    a.  **Name**: "Escalate To Human"

    b.  **Priority**: 1 (lower than default queue)

    c.  Click **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Queue summary with Name entered as Escalate to Human, Priority is 1 and Queue type is Messaging.](../media/53-save-new-queue.png)](../media/53-save-new-queue.png#lightbox)

1. A User (Agents) **subgrid should appear** on the right and your **user should be automatically added** to the list. If your user account is not on the list, add it through the Add Existing User button now.

    The queue **Escalate To Human** is created to manage and redirect the incoming messages from a user to a Customer Service (human) Agent when Bot sends the user through to a live agent.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Escalate to Human queue Summary page.](../media/54-escalate-to-human.png)](../media/54-escalate-to-human.png#lightbox)

**Congratulations!** You have created the necessary queue to escalate to human agent and added the appropriate users to each messaging queue.

## Task 4: Update Live Work Stream with Context Variables and Routing Rules

In this task, we'll set up basic chat routing. This will allow for users to chat with a bot user in certain cases and a live human agent in other scenarios. The routing rules will allow chat to behave as follows:

- **Route to Bot:** Initial customer conversation is through Health Bot in the default messaging queue. When the chat bot is first opened, route to Default queue, which only contains the bot user (agent).

- **Human Routing Rule**: When context variable **EscalateToAgent** is present and set to 1, we route to the queue that has only human users (agents) who can take over conversation.

1. Navigate to **Work Streams.**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Work Distribution Management menu with the Work Streams option selected.](../media/55-work-streams.png)](../media/55-work-streams.png#lightbox)

1. Select and edit the **Live chat workstream**.

        > [!div class="mx-imgBorder"]
        > [![Screenshot of the Active work streams menu with the Live chat workstream option selected.](../media/56-live-chat-workstream.png)](../media/56-live-chat-workstream.png#lightbox)

1. In the **Live chat workstream** record, select the **Context Variables** tab. Select **+ New**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Live chat workstream record Context Variable tab.](../media/57-context-variables.png)](../media/57-context-variables.png#lightbox)

1. Create the new Context Variable with the following details:

    a.  **DisplayName:** EscalateToAgent

    b.  **Name:** EscalateToAgent

    c.  **Type:** Number

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Quick Create Context variables with Display Name, Name, Owner and Type fields populated.](../media/58-escalate-context-variable.png)](../media/58-escalate-context-variable.png#lightbox)

1. Select **Save and Close**.

1. You should now see the new Context Variable in the Live chat workstream.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Context Variable Escalate to Agent added to the Context Variable Display name column.](../media/59-live-chat-context-variables.png)](../media/59-live-chat-context-variables.png#lightbox)

1. Select the **Routing Rules** tab. Click **+ Add** to create a new routing rule.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Live chat workstream Routing Rules tab.](../media/60-routing-rules.png)](../media/60-routing-rules.png#lightbox)

1. Create the new Health Bot routing rule with the following details:

    a.  **Name:** ToHealthcareBot

    b.  **Queue**: Default messaging queue

    c.  No Conditions.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Rule Item General information page.](../media/61-new-rule-item.png)](../media/61-new-rule-item.png#lightbox)

1. Select **Save & Close.** On the Live chat workstream, select **+ Add** to add another new Routing Rule.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Live chat workstream Routing Rules page.](../media/62-add-routing-rule.png)](../media/62-add-routing-rule.png#lightbox)

1. Create the new Omnichannel Agent routing rule with the following details:

    a.  **Name:** ToAgent

    b.  **Queue:** EscalateToHuman

    c.  **Add Condition:** Context Variable "**EscalateToAgent = 1"**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Rule Item General Information page with Name, Queue, Add Condition and Add Condition fields pooulated.](../media/63-new-rule-general.png)](../media/63-new-rule-general.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Condition section of the New Rule Item General tab.](../media/64-condition.png)](../media/64-condition.png#lightbox)

1. Select **Save & Close.**

1. On the Live chat workstream, you should now see the two **Routing Rules** we created for **Bot** (ToHealthcareBot) and **Agent** (ToAgent).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Routing Rules tab with To Healthcare Bot and To Agent Rule items added.](../media/65-bot-agent-rule.png)](../media/65-bot-agent-rule.png#lightbox)

**Congratulations!** You have created the proper context variable and routing rules that will allow customers to begin conversation with a health bot and escalate to a human agent.

## Task 5: Create Chat Widget for Health Bot

1. Navigate to Chat.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the left navigation pane Channels menu with the Chat option selected.](../media/66-chat.png)](../media/66-chat.png#lightbox)

1. Select **+New** Chat Widget.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Chat horizontal navigation bar with the New option selected.](../media/67-new-active-widget.png)](../media/67-new-active-widget.png#lightbox)

1. Give the Chat Widget a **Name** (ex: Patient Portal Chat Widget).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Chat Widget General settings tab with sample Patient Portal Chat widget information populated.](../media/68-chat-widget-name.png)](../media/68-chat-widget-name.png#lightbox)

1. Select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the New Chat Widget horizontal navigation bar with the Save option selected.](../media/69-save-chat-widget.png)](../media/69-save-chat-widget.png#lightbox)

1. After the record is saved, a **Widget Code Snippet** will be generated. **Copy** the code snippet and store it for later use.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the sample Patient Portal Chat Widget General Settings tab with the Code snippet section highlighted.](../media/70-widget-code-snippet.png)](../media/70-widget-code-snippet.png#lightbox)

> **Congratulations!** In this exercise, you have successfully configured Customer Service Omnichannel Live chat by creating the necessary Users, Queues, Work Streams, Context Variables, Routing Rules, and Chat Widget. These all work together and allow patients to chat with a virtual health bot with the option to escalate up to a human agent if needed.
