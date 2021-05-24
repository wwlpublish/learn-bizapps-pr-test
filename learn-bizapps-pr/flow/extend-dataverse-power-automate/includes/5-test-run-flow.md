Now that you have a useful flow, it's time to test it.

Start by selecting **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow with the Save button highlighted.](../media/9-save.png)](../media/9-save.png#lightbox)

Select **Test** in the upper-right corner.

> [!div class="mx-imgBorder"]
> [![Screenshot of the saved flow with the Test button highlighted.](../media/10-test.png)](../media/10-test.png#lightbox)

If you would have triggered the flow previously, you could test automatically. However, because this is the first time that you're initiating the flow, you need to test it manually. Select the **Manually** option and then select **Test**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Test Flow dialog box with Manually selected.](../media/11-manually.png)](../media/11-manually.png#lightbox)

Next, you need to add a record to the table. In a new tab, go [Power Apps](https://make.powerapps.com/?azure-portal=true) and select **Data** and then **Tables**. You can search for the table that you want or select **Contact**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Microsoft Power Apps with Data > Tables selected in the navigation pane and Contact highlighted in the Tables list.](../media/12-data.png)](../media/12-data.png#lightbox)

Select **Data > Edit data in Excel**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Contact table with the Data menu selected and the Edit data in Excel option highlighted.](../media/13-edit-data-excel.png)](../media/13-edit-data-excel.png#lightbox)

Sign in and add at least one row of data. No need to add every field, but try to add at least the first name, last name, job title, and email address. These fields are referenced in the flow. When you're done, select **Publish**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Data connector dialog box.](../media/14-publish.png)](../media/14-publish.png#lightbox)

Switch to the **Power Automate** tab to check on your flow. You should have a success message.

> [!div class="mx-imgBorder"]
> [![Screenshot of the flow showing Your flow ran successfully.](../media/15-success.png)](../media/15-success.png#lightbox)

Check your inbox in Outlook. You should have a new email.

> [!div class="mx-imgBorder"]
> [![Screenshot of the New contact added email.](../media/16-complete-email.png)](../media/16-complete-email.png#lightbox)

Select the ellipsis (**...**) in the lower-left corner and then select **To Do**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Outlook with the ellipsis button selected and the To Do option highlighted.](../media/17-open-to-do.png)](../media/17-open-to-do.png#lightbox)

A new to-do action will display under the list that you specified.

> [!div class="mx-imgBorder"]
> [![Screenshot of Outlook Tasks with the new task added.](../media/18-new-to-do.png)](../media/18-new-to-do.png#lightbox)

Now, you know how to take actions on data that is held in Dataverse.
