Many organizations want to create bot topics that leverage existing content. This can provide them with several advantages from the time saved in authoring the topic, to ensuring that topics are aligned with the types of issues that are being reported. 

There are two ways organizations can automatically generate topics for a bot:
- From Customer Service Insights topics.
- For existing web content such as FAQ pages. 

Power Virtual Agents uses Artificial Intelligence (AI)-assisted authoring to help organizations automatically extract and insert relevant content from existing web content topics into your bot. This eliminates the need to copy and paste or manually recreate content into topics.

The Artificial Intelligence evaluates the page and determines both the structure and content. It isolates content blocks that relate to a support issue or question and classifies them into topics. Each topic identified will follow the same structure as other topics. They will contain [trigger phrases identified during the process, as well as an initial Message node](https://docs.microsoft.com/power-virtual-agents/authoring-create-edit-topics/?azure-portal=true). These topics appear as suggested topics that can be modified and deleted like other topics.

## Extracting content from Customer Service Insights 

Dynamics 365 Customer Service Insights uses artificial intelligence to automatically group your organizations cases into topics.  Since topics are already defined based on your organization’s caseload, it would make sense to align the topics in a customer support bot with those topics. When considering which topics to automate from Customer Service Insights, typically the topics are: 
- Items that are straightforward to resolve.  This makes it more likely a bot can handle or resolve the issue.  For example, a topic that has lower average resolution time, higher resolution rate, and/or fewer escalations is one that could be considered straightforward to resolve.
- Topics that have a high volume.  This allows the automation to potentially bring you more business benefit and impact. 

For more information, see[automating topics from Customer Service Insights](https://docs.microsoft.com/dynamics365/ai/customer-service-insights/automate-topics).

## Extract content from webpages

There are three main steps involved with auto-creating topics:

1. Extract content from existing FAQ or support pages

1. Add the suggested topics to your bot

1. Enable the topics in your bot

The first step in creating topics from existing content, is to extract topic suggestions from existing pages you want to use that contain support content. This is done by using the suggested topics command in Power Virtual Agents. The suggested topics command is built to run on webpages that are in the form of FAQ pages or support sites. After the extraction is complete, the suggested topics are displayed for you to review further.

Content can be extracted using the suggested tab on the Topics page. When you are first getting suggestions, this page will likely be blank. Once topics have been extracted the list will be displayed. To suggest topics, you will need to enter a URL for each webpage you want to extract content from. The URLs must be secure (they must start with *https://*). If you add a page by mistake, you can remove it by selecting Delete.

> [!div class="mx-imgBorder"]
> [![Suggest topics is built to run on webpages formatted as FAQ pages or support sites. Pages not following that structure might not work as expected.](../media/4-1.png)](../media/4-1.png#lightbox)

Depending on the complexity of the pages as well as the number of pages you add, it can take some time to extract the content. The message "Getting your suggestions, this may take several minutes" appears at the top of the screen while the extraction is in progress. If any errors are encountered during this process, the tool provides explicit feedback about errors so that you can understand and address the issue. For example, you might be unable to extract content because the site you are referencing is down. Once the content has been extracted, suggestions will appear that you can review and decide if they should be added to your bot.

> [!div class="mx-imgBorder"]
> [![Suggested topics are not actual topics that can be consumed by the bot. They must be added to the bot before use.](../media/4-3.png)](../media/4-3.png#lightbox)

### Add suggested topics to an existing bot

Extracted topics are not automatically added as topics in your bot. After the extraction process has been completed, any topic suggestions will appear on the Suggested tab. This will allow you to review them and determine if they are topics that you want to have included in your bot. You can also review the trigger phrases and message nodes that were created and make any edits that you want.

There are three options for dealing with the topic.

- **Add to topics and edit**: Opens the topic so you can edit the trigger phrases or enter the authoring canvas to make changes to the conversation flow. Once completed, the topic will be removed from the list of suggestions.

- **Add to topics:** Topic is automatically added to the list of topics and removed from the list of suggested topics.

- **Delete suggestion:** Does not add to your list of topics and deletes the topic from the suggested topics.

> [!div class="mx-imgBorder"]
> [![Suggest topics and add to topics](../media/4-4.png)](../media/4-4.png#lightbox)

### Enable topics in your bot

Once a suggested topic is added to the Existing tab, the status set to Off. This will make sure that it is not prematurely added to your bot before you have had time to make the necessary changes to it, such as modifying trigger phrases or adding additional conversation nodes to enhance the topic as required. When a topic is ready to be used, set the Status to On.

> [!div class="mx-imgBorder"]
> [![Once added, the topic moves to the existing list. Turn on the topic so the bot can consume it.](../media/4-5.png)](../media/4-5.png#lightbox)
