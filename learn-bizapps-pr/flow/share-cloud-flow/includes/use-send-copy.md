So far in this module, we've talked about sharing the same cloud flow definition with other users. When you use Send a copy to share a flow, the users receive their own copy. You can initiate **Send a copy** when you have a cloud flow selected in the list or from the flow detail page.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the send a copy icon on the flow detail page.](../media/send-copy.png)](../media/send-copy.png#lightbox)

You must be one of the owners of a cloud flow to use the Send a copy feature. You also must have successfully run the flow since it was last modified before you can send a copy.

:::image type="content" source="../media/group.png" alt-text="Screenshot showing sending a copy to a group.":::

If you send a copy to an individual user, they'll receive an email like the following to launch creating the flow. An email isn't sent when you send a copy to a group. Instead, group members will be able to access the copy on the flow portal.

> [!div class="mx-imgBorder"]
> [![Screenshot of the email notification that a flow is sent to you as a copy.](../media/email.png)](../media/email.png#lightbox)

Users, both individual and from groups, can see and use the flow template by navigating to **Templates** > **Shared with me**.

![Screenshot showing how to find the templates on the portal under templates shared with me.](../media/shared.png)

Once you've sent a copy, you can't recall or remove it. If you need to send an update, make the title unique so the receiving users can differentiate which one is new. The following is an example of sending the same title twice.

![Screenshot showing an example of sending the same title twice. Both look the same to the user so use unique titles.](../media/duplicate.png)

When users use the template, they see the following prompt before creating the flow.

:::image type="content" source="../media/template.png" alt-text="Screenshot showing creating the flow from the template.":::

If the flow uses any connectors, the recipient will have to create their own connections and therefore have relevant permissions. For example, if the flow uses the SharePoint connector, then the recipient would need to have the access to SharePoint to be able to recreate the connection. Once created, they're taken to the detail page to edit and manage the flow just like any other flow they own.

## Decide whether you should use Send a copy

Send a copy is the best approach to sharing when you have a cloud flow that would help others but needs personalization. By having their own copy, you don't have to be concerned about them modifying and breaking your flow.

Send a copy is also a good approach for someone to use as a starting point for building their own flow. For example, a sales team may create a set of five flows that they send to all new sales staff to get them started building their own productivity automation.

> [!Important]
> Once you send a copy to a user or group, it's impossible to recall, change, or remove it. Avoid sharing flows with sensitive information.

For flows that frequently change a single shared flow works better. When you share using a copy, the changes would have to be made in each copy individually.

Send a copy allows the user to create the flow in the same Power Platform environment your flow is in. If you want to have the flow run in a different Power Platform environment, review the solutions unit later in this module.

Send a copy works seamlessly in the default environment because everyone has access. If you send a copy of a flow to a user from an environment they don't have access to, they'll get an error when they try to create the flow. To avoid errors, make sure the same users and groups have access to the environment you're sending the flow from prior to sending.
