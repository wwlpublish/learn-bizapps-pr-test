When you create a new Power Automate cloud flow, it's only visible, editable, and runnable by you. By sharing, you can allow other users within your organization to run or help edit your automation.

> [!div class="mx-imgBorder"]
> [![Screen image of the Share flow where you can share with other users.](../media/owners.png)](../media/owners.png#lightbox)

Power Automate offers the following types of sharing:

- Share a cloud flow so other users can run the flow.

- Share a cloud flow so other users can edit the flow.

- Package a cloud flow using Dataverse solutions to copy a flow into different Power Platform environments, for example, Test and Production.

- Share a copy of a cloud flow.

The type of cloud flow can limit the kind of sharing available. For example, only instant cloud flows can be shared allowing the user to only run the flow without giving the permission to edit the flow also. Instant, automated, and scheduled cloud flows can be shared using co-ownership, Dataverse solution, or by sending a copy.

You can choose an individual user or group when sharing a cloud flow. Sharing with a user is a good approach for informal sharing with a few people. When possible, sharing with a group is a better option when you want to share multiple flows with the same group of people. Group sharing makes it easier to manage who has access to flows.

Groups can be Azure Active Directory Security Groups or Office Groups. For example, an easy way to create an Office group is to create a team in Microsoft Teams.

You can share with users outside your organization if they've been [added as a Guest user](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal/?azure-portal=true) in your Azure Active Directory. There are some limitations on what an external user can do with flows that are shared with them.

## Where to find shared flows

When a cloud flow is shared with you individually, you'll receive an email. The email will indicate if you've been added as a co-owner that can edit or if you're a run-only user. When you share a flow with a group of users, they won't receive an email.

If you're a co-owner of a cloud flow, the flow won't show in your **My Flows** > **Cloud flows** list but will show in the **My Flows** > **Shared with me** list.

> [!div class="mx-imgBorder"]
> ![Screenshot showing My Flows Shared with me list.](../media/shared-me.png)

If you don't recognize a flow and want to know who shared it with you, select the flow name. The detail page will list the original flow owner.

> [!div class="mx-imgBorder"]
> ![Screenshot showing the flow detail page so you can find the original owner.](../media/flow-details.png)

For instant cloud flows that you access as a run-only user, you'll only see it in the app that supports the flow's instant trigger. For example, a button flow would show in the Power Automate mobile app. A Microsoft Teams selected message would show in Microsoft Teams and Dataverse when a record is selected in the Power Apps model-driven app. When you're a run-only user, the flow won't appear in **My Flows** > **Shared with me** list.

You can add a user or a group as a co-owner. This allows the user or any member of the group to edit the flow. Once you add a co-owner, your flow will no longer be in the **My Flows** > **Cloud flows** list but will show in **My Flows** > **Shared with me**. It will remain on the shared list even after you remove everyone the flow was shared with.

Cloud flows shared as run-only will still appear on your **My Flows** > **Cloud flows** list.

## Check before you share

Before you share your cloud flow with other users, you should make sure it's a good candidate for sharing.

**Start by evaluating if your flow would be helpful to those you're sharing with.** For example, a flow that is set to use your postal address wouldn't be useful to someone who lives or works elsewhere. In some cases, you can make minor changes to your flow to make it more useful to others before you share it.

**Does the flow have a name that is meaningful to others?** Once you share a flow with others, it will show up in their lists of flows. For example, a flow named ***Check WAO*** might mean something to you but, if you shared it with others, they would be confused. A better name would be ***Check Weather at Office***. Also, make the first 20 or so characters of the name meaningful, because that is what users see when space is limited.

**Does the flow send you notifications or emails?** It's common if you're building a flow to improve your productivity to include a notification or an email to yourself. That means every time someone else runs the flow; you'll receive an email notification. Instead of specifying your own email address, you can use an action like **Get My Profile (V2)** in **Office 365 Users** connector to retrieve the email address of the user running the flow and send an email to them instead.

**Will the user need any special licenses or subscriptions?** Users you share a cloud flow with will need an appropriate Power Automate license or [equivalent use rights](/power-automate/create-team-flows?azure-portal=true#prerequisites). If you use other services by using an action from other connectors, they may have their own license requirements. For example, if you choose to let users you share with use your connection instead of requiring their own can be important. You'll also learn about these two options in the connection unit of this module.

In the rest of this module, we'll explore more details on how sharing a cloud flow works and options you can take advantage of when you use the feature.
