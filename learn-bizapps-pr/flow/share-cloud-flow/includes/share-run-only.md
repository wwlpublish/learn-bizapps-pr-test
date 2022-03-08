In addition to sharing a cloud flow with co-owners, you can alternatively share it using the run-only option.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4PlRj]

When a flow is shared as run-only, the user can execute the flow but can't make any changes to the flow. Run-only sharing is only available for instant cloud flows. Instant cloud flows are triggered manually from one of the supported applications. The following image shows a few of the available triggers that make a cloud flow support run-only sharing.

> [!div class="mx-imgBorder"]
> [![Screenshot showing instant cloud flow triggers like Flow button for mobile - Power Apps - Power Virtual Agents - For a selected file in SharePoint - For a selected item in Dataverse.](../media/build.png)](../media/build.png#lightbox)

To share an instant cloud flow as run-only, select the **Edit** link in the **Run-only users** section of the detail page to open the share panel.

> [!div class="mx-imgBorder"]
> [![Screenshot showing run only user section in lower right of screen.](../media/run-only.png)](../media/run-only.png#lightbox)

The run-only section is only visible for instant cloud flows. If the run-only section isn't present, the flow isn't using an eligible trigger.

On the share panel that is displayed you can choose to invite one or more users and groups.

:::image type="content" source="../media/invite.png" alt-text="Screenshot showing the share panel that you can choose to invite one or more users or groups.":::

If your flow uses the SharePoint connector, you'll see the SharePoint tab and can select a Site and List that can run the flow. List users must have edit permissions for the list items to be eligible to run the flow.

:::image type="content" source="../media/sharepoint.png" alt-text="Screenshot showing the share panel where you can configure a SharePoint list user to have permission to run the flow.":::

## Connection options

At the bottom of the share panel for each connector used by the flow, you can configure which connection to use when a user runs the flow. You can choose either **Provided by run-only user** or **Use this connection** option.

:::image type="content" source="../media/connections.png" alt-text="Screenshot showing the connections used, allowing you to configure which connection to use for each connector.":::

The default option is **Provided by run-only user** which means the first time a new user uses the flow they'll be prompted to create a connection for the connectors that use that option. In the following example, Dave the flow owner has shared a flow with Julie and the following prompt for connections will show on first use.

> [!div class="mx-imgBorder"]
> ![Screenshot showing the user prompted to configure connections when they run the flow.](../media/run-flow.png)

In the above image, you can see that Julie already had a Microsoft Teams and Office 365 Outlook connection but needs to sign into SharePoint. All connectors for this flow will be in the context of Julie's connections.

In the following example, Dave shared again with Julie, but changed the Microsoft Teams and Office 365 Outlook connection to use the existing connection. By doing this, when the flow executes, those connectors' actions will use Dave's connection and permissions. This allows the flow to take actions the executing user might not have access to do. For example, it can post to a Team channel they aren't a member of.

![Screenshot showing some connections configured as use this connection instead of provided by run only user.](../media/connections-used.png)

> [!NOTE]
> You can change these selections at any time, but they'll apply to all users at the same time. You can't have some users with different options.

With the new connection options when Julie accesses the flow it will now only prompt for the SharePoint connection.

![Screenshot showing the user prompted for a connection.](../media/julie-sharepoint.png)

Sharing an instant flow using the run-time option is a great way to let others use the automation you built but without giving them the full ownership access.
