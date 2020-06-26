Power Automate is a great way to automate AI builder usage and exploit AI model results at scale.

## AI Builder usage in Power Automate

Power Automate offers AI builder actions that enable usage of all model types in flows. Adding AI builder actions in your flow allows you to:

-   Perform model inference using outputs of upstream actions (email attachments received, SharePoint files dropped, records created in a Common Data Service entity, ...)

-   Process model inference results in downstream actions (send by email, store in Common Data Service records, message in Teams, ...)

The following illustration shows a simple flow with three main stages:

1. Reception of an email in Outlook. 
2. Detect sentiment of the email body using AI Builder sentiment analysis model.
3. Send an email notification with the sentiment detected in the email using the output "Overall text sentiment" from the AI Builder model

![A screenshot of a social media post Description automatically generated](../media/01-social-post-flow.png)