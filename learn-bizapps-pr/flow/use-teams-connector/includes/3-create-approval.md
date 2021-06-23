To add the actions that will post to Teams, ensure that you are still in the **Apply to each** screen and then select **Add an action**. Search for and select the **Post a choice of options as the Flow bot to a user** option.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Apply to each action with the Add button selected and Choose an operation showing a search for post a choice of options.](../media/4-post-teams.png)](../media/4-post-teams.png#lightbox)

In the **Options Item - 1** field, enter **Yes**. Select **Add new item** and then enter **No** in the **Options Item - 2** field. Add your email address in the **Recipient** field. You can change the recipient later to follow conditional logic or to someone other than you, but we recommend that you enter your own email for testing.

The **Message** box should be a combination of text and dynamic content from the AI model. Use the following image to create the message. Remember to add dynamic content by selecting the **Add dynamic content** button when your cursor is in the correct place and then selecting the desired content in the flyout menu.

The **Headline** field should read: **Please approve this invoice**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Post a choice of options as the Flow bot to a user dialog box.](../media/5-options.png)](../media/5-options.png#lightbox)

Now that you've posted in Teams, you will want to act on the response. To accomplish this task, select **Add an action** in the **Apply to each** screen. Search for and select **Condition**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose an operation dialog box showing the Actions tab with Condition highlighted.](../media/6-condition.png)](../media/6-condition.png#lightbox)

For the first value, select **selectedOption** from the **Dynamic content** menu.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Condition dialog box with Dynamic content selected and selectedOption highlighted.](../media/7-selected-option.png)](../media/7-selected-option.png#lightbox)

Ensure that the operator field is set to **is equal to** and then enter **Yes** for the second value.

Conditions are case-sensitive, so be sure that you type the same value for the option and the condition.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Condition dialog box with selectedOption set equal to Yes.](../media/8-complete-conditions.png)](../media/8-complete-conditions.png#lightbox)

Now, you've connected to Teams for approval and have set up the condition. The remaining step is to add the actions for approval and rejection.
