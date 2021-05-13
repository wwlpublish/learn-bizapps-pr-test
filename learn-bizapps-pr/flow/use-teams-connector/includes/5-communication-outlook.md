Now that you've gone through an approval and have updated your legacy app if approved, you need to alert the invoice sender of the approval outcome. To begin, select **Add an action** under the **If yes** branch and then search for and select **Reply to email (V3)**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Choose an operation dialog box with Reply to email (V3) highlighted.](../media/13-send-email-if-yes.png)](../media/13-send-email-if-yes.png#lightbox)

For the first field, find the **Message ID** of the original email in the **Dynamic content** menu. The body will be a combination of text and dynamic content, as shown in the following image. Expand the fields by selecting **Show advanced options** and then enter **Your invoice is approved** in the **Subject** field.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Reply to email dialog box with Dynamic content for the Message ID.](../media/14-approval-email.png)](../media/14-approval-email.png#lightbox)

Now, you have the approval email and only need to add the rejection email. To do so, ensure that you are under the **If no** branch and then select **Add an action**. Search for and select **Reply to email (V3)**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the If no branch with the Choose an operation dialog box showing search results for Reply to email.](../media/15-send-email-if-no.png)](../media/15-send-email-if-no.png#lightbox)

For the first field, find the **Message ID** of the original email in the **Dynamic content** menu. The body will be a combination of text and dynamic content, as shown in the following image. Expand the fields by selecting **Show advanced options** and then enter **Your invoice is rejected** in the **Subject** field.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Reply to email (V3) dialog box.](../media/16-rejection-email.png)](../media/16-rejection-email.png#lightbox)

Select **Save**.
