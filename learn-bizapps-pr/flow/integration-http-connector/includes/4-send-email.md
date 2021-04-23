Using Power Automates **Office 365 Outlook** and **Mail** connectors you can send emails for workflows, however, emails are sent as if a user sent them.

As you can see below, **To** can be populated using only the user's email address. This workflow is applicable when an email notification is supposed to be sent to and from users.

> [!div class="mx-imgBorder"]
> [![Screenshot of the to field populated with the user's email.](../media/image-12.png)](../media/image-12.png#lightbox)

You can also create flows that send email notifications directly from `SharePointOnline.com`. The **Send an HTTP request to SharePoint** action is used to create emails that come directly from SharePoint Online via the `no-reply@sharepointonline.com` mailbox.

### Video

The following video shows an email notification that is sent directly from SharePoint when a list in the site is used to reserve conference rooms for meetings.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/]