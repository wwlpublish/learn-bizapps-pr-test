Now that we have the initial structure of the bot created, the next step is to begin authoring topics. Topics define how the bot will be interacted with by customers. They typically represent common issues, questions, or tasks that customer may need assistance with. For example, a topic might be created to provide item return instructions to customers. Each topic consists of two primary elements:

1.  **Trigger phrases:** Phrases, keywords, or questions entered by users that relate to a specific issue.

1.  **Conversation nodes:** Define how a bot should respond and what it should do.

Topics can be authored by [customizing provided templates](https://docs.microsoft.com/power-virtual-agents/authoring-template-topics/?azure-portal=true), created from scratch, or suggested from existing sites. Your bot can have up to 1,000 topics.

## Getting Started with Topics

Each created bot will include several pre-defined topics to you get started. These are broken down into two types:

-   **Lesson Topics:** Pre-created user topics that can be used to help understand simple and complex ways of using nodes to create bot conversations.

-   **System Topics:** Prepopulated topics represent common use cases that can occur during a bot conversation.

> [!div class="mx-imgBorder"]
> [![lesson topics and system topics](../media/pva-4-1-ss.png)](../media/pva-4-1-ss.png#lightbox)

## Working with lesson topics

The intent of lesson topics is to provide examples on how to leverage topics to solve specific scenarios and help you become more comfortable as you author bots. Lesson topics range from simple such as providing a user with store hours, to more complex scenarios where it is assisting online shoppers with items in their cart.

There are four included lesson topics:

|     Topic                                                                   |     Description                                                                                                                                                                                              |     Notes                                                                                                                                                                                                                                                                                                                                                                            |
|-----------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     Lesson 1 – A simple topic:                                              |     Walks through creation of a simple topic with one conditional   branch that displays store hours.                                                                                                        |                                                                                                                                                                                                                                                                                                                                                                                      |
|     Lesson 2 – Simple topic with condition and   variable                   |     A   simple topic that contains one conditional branch and a variable that   displays store locations based on the customers preferred store   location.                                                  |     A   variable is a name for an item, which will be used later in the topic flow. In   this example, pva_StoreLocation is the variable to store the user's   response when you ask for their preferred store location.                                                                                                                                                              |
|     Lesson 3 – Topic with conditions,   variables, and a pre-built entity    |     Walks through creation of a topic that includes one conditional   branch, a variable, and an entity. In this lesson, the bot uses the   State entity and will recognize any US state the user enters.    |     Topic entities help identify key information from what the user   types and automatically fill in that information into your variables.  For example, if you type "I want to   buy a red car," the bot doesn't need to ask which color car, because the   bot recognizes the Color entity in what you typed. The bot will then skip the   question where you asked for color.    |
|     Lesson 4- Topic with conditions, variables,   and a custom entity       |     Walks   through creation of a topic with a conditional branch, a variable,   and a custom entity.                                                                                                        |     This   is similar to the previous example, except you create a custom entity to   capture information.  For example, try   testing with "I want a business laptop."                                                                                                                                                                                                              |

## System Topics

System Topics represent scenarios customers are likely to encounter while interacting with your bot such as initiating and ending a conversation or escalating a conversation to a live agent. System topics will have a basic structure already in place based on what it is. For example, the greeting topic will already have predefined triggers and a basic conversation path that you can begin to modify based on your needs.

> [!div class="mx-imgBorder"]
> [![system topics](../media/pva-4-2-ss.png)](../media/pva-4-2-ss.png#lightbox)

## Creating Topics

You will define any additional by selecting Topics in the side navigation pane, and then selecting New topic at the top of the page. Each topic you define should include some trigger phrases. Trigger phrases are examples of text such as questions or utterances that teach the bot when to respond with this dialog. For example, the image below contains a topic called 'Store Hours', which will be used to provide customers with store location hours based on different scenarios.

> [!div class="mx-imgBorder"]
> [![creating topics](../media/pva-4-3-ssm.png)](../media/pva-4-3-ssm.png#lightbox)

Six trigger phrases have been added such as 'What are your hours?' and 'When are you open?'. These will be used to determine when the 'Store Hours' topic should be initiated. The more trigger phrases you add, the more likely it is that the topic will be appropriately used. Triggers phrases should be unique per topic. If you have the same trigger in multiple topics, the bot will not be able to identify which topic to load. Once the initial triggers have been added, select Save topic to add the topic to the topics list. Additional triggers can be added later as needed.

Once your topic has been saved, it is time to define how customers are guided through their conversational interaction with the topic. You define the path by selecting go to authoring canvas. The authoring canvas is a graphical dialog tree editor that allows you to define bot responses and the overall bot conversation. When the canvas loads, the conversation will consist of two nodes:

-   The trigger phrases that will initiate this topic.

-   The initial message that will be provided to the user.

The trigger phrases will be pre-populated with the items defined in the previous step. You will need to provide the initial message to the user such as "Hello, I'm happy to assist with store hours."

> [!div class="mx-imgBorder"]
> [![trigger phrases](../media/pva-4-4-ssm.png)](../media/pva-4-4-ssm.png#lightbox)

## Working with conversation nodes

Conversation nodes help define the path the conversation will take. They can do things such as display messages, ask questions, or execute actions. They are added by selecting the **+** below the node. For example, if you wanted to provide store hours based on where the customer lives, you would add an Ask a question node to identify which store location they want the hours for.

In the image below, we are using the ask a question node to ask them, which store location they want the hours for. In addition, we are providing them with two multiple-choice options to choose from 'Seattle' and 'Bellevue'.

> [!div class="mx-imgBorder"]
> [![conversation nodes](../media/pva-4-5-ssm.png)](../media/pva-4-5-ssm.png#lightbox)

Separate conversation paths are created based on the customer's response. In the forked conversation path, each node has automatically checked for 'Seattle' in one path, and 'Bellevue' in the other path to take the appropriate next step. Additional nodes can be added for each path based on what you want it to do.

The image below, shows that for each path, a Message node is added that provides the store hours for that specific location.

> [!div class="mx-imgBorder"]
> [![message node added](../media/pva-4-6-ss.png)](../media/pva-4-6-ss.png#lightbox)

You now have a simple branching dialog tree. You can begin to create more complex versions of this tree by incorporating [variables](https://docs.microsoft.com/power-virtual-agents/authoring-variables/?azure-portal=true), [entities](https://docs.microsoft.com/power-virtual-agents/advanced-entities-slot-filling/?azure-portal=true), and [Power Automate flows](https://docs.microsoft.com/power-virtual-agents/advanced-flow/?azure-portal=true).

