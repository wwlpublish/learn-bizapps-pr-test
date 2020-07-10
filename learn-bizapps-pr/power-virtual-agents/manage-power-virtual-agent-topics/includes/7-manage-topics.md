As the number of topics in your bot grows, it becomes more important be able to effectively manage them. This includes understanding which topics are active and can be used by the bot, as well as which ones are still being worked on. Topic management also includes identifying errors that could impact a topics ability to be used. To help assist you effectively manage topics, Power Virtual Agents provides multiple features that help ensure topics are working as intended, and only visible to end users after they have been tested and are ready.

## Manage topic status

Each topic has a status that indicates if the topic can be used in conversation. A topic can either be on or off. When a topic is on, it will trigger as expected. This could be the result of its trigger phrases or from being redirected to it from another topic. Most topics will be in the on state. All topics are set to on when they are created.

> [!div class="mx-imgBorder"]
> [![All topics are on by default when they are created.](../media/7-1.png)](../media/7-1.png#lightbox)

Topics that are off will not trigger at all. Off topics trigger phrases will not work, and they will not be redirected to, even if another topic has specified it. The topic is treated as if it does not exist. In most scenarios, a topic is set to off while being worked on until it is ready to go live. When a bot is published, every topic regardless of if it is set to on or off will be published. However, any topics that are set to off will not be triggered.

## Work with topic errors

While working on a topic, PVA's Topic Checker validates your topic and shows any errors or warnings. Errors or warnings can occur for any number of reasons. Warnings indicate that something is not ideal, but it will not prevent the bot from functioning. Since warnings do not prevent the bot from functioning, they are ignored while processing. Errors on the other hand need be addressed to avoid unexpected behavior or failure during the chat experience. Errors might occur if a node in your topic is incomplete. For example, not providing a message in a message node, or authentication issues with a Power Automate flow that is being launched in an action are both examples that would cause for errors. The Topic Checker will provide details related to the warning or error to make it easier to resolve the issue.

> [!div class="mx-imgBorder"]
> [![Topic checker button](../media/7-2.png)](../media/7-2.png#lightbox)

There are four types of errors that appear in the topic checker and in the authoring canvas:

- **Node:** The entire node is erroneous and is highlighted red.

- **Field:** The field might be missing required data and is highlighted red.

- **Expression:** The expression might be invalid and is highlighted red.

- **Variable deletion:** A variable in a topic was deleted and is highlighted red wherever it was used. This causes the variable to become \"orphaned\", and it must either be removed or replaced.

You can also see the error state of a topic on the Topics list page by clicking on the Topics tab. The Errors column indicates the number of errors found during validation. This only indicates errors and does not include warnings, since they do not prevent the bot from functioning. As you fix the errors, they will disappear from the topic checker, either automatically or after saving the topic. Topics with errors can be saved, however, the errors will persist until they are addressed. You cannot deploy a topic containing errors to production.

> [!div class="mx-imgBorder"]
> [![Errors can impact your bot's ability to perform. They should be resolved as soon as possible.](../media/7-3.png)](../media/7-3.png#lightbox)

## Copy a topic

Once you have created a few topics, you may want to use a previous topic as a baseline when creating new topics. Copying topics saves time a conversation path is already defined. You just need to modify the trigger phrases, and tailor the conversation path to fit your need. On the topic list page, hover on a topic, select the menu icon, and then Make a copy. This will create a duplicate of the selected topic with *(Copy)* appended to the name. All topic content, such as the description, trigger phrases, and the entire conversation is copied over to the new topic.

> [!div class="mx-imgBorder"]
> [![Make a copy menu item](../media/7-4.png)](../media/7-4.png#lightbox)

The new topic appears in the User topics list. All copied topics have a status of Off by default to avoid confusion on which topic will trigger, since it will have the same trigger phrases as the original topic. Once you have finished editing the new topic, you can turn it On to [test it in the Test bot](https://docs.microsoft.com/power-virtual-agents/authoring-test-bot/?azure-portal=true) window and, when ready, publish the new topic.
