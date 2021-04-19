Chatbots, if used, are a powerful tool for increasing customer interaction with your solution. A solution architect must ensure that the chatbots are correctly built and meet the requirements.

This section contains recommendations around designing and deploying chatbots.

## Planning

When planning a chatbot the solution architect should:

- Define the scope of the chatbot
- Define the purpose of the chatbot
- Define which channels the bot will be deployed to
- Define the key metrics and success criteria
- Verify the topics, entities, and conversational flows.

A chatbot supports three different types of topic:

- Informational
- Tasks
- Troubleshooting

A good Power Virtual Agents chatbot will have a high business impact that is, a high level of traffic, a low level of integration complexity, and will achieve a high  level of conversation completion without the need for escalation to a human agent.

A well-designed chatbot will have a well defined set of goals. Each topic is linked to a business process and has trigger events, a clear set of rules, a set of documents, and a series of tasks that will be performed.

The solution architect may need to provide guidelines for creating topics and trigger phrases for chatbot authors to follow.

## Escalations

With Power Virtual Agents, you can hand off conversations to live agents seamlessly and contextually.

When you hand off a conversation, you share the full history of the conversation (the context) and all user-defined variables. Having access to this context means live agents that are using any connected engagement hub can be notified that a conversation requires a live agent, see the context of the prior conversation, and resume the conversation.

> [!IMPORTANT]
> You need to have an engagement hub that is being used by live agents, such as Omnichannel for Customer Service, and you need to configure the connection.

![Power Virtual Agents escalation to an engagement hub.](../media/4-escalation.png)

The solution architect should determine when escalation should occur and how escalation will be handled.

Power Virtual Agents chatbots come with telemetry built-in so that you can monitor how your chatbots are being used. Key KPIs are the rates of abandonment and escalation to a human agent. You should monitor your chatbots and change your chatbot to increase its effectiveness.

## Variables

Variables let you save responses from your users in a conversation so that you can reuse them later in conversations.

The response for each question asked in a conversation is stored as a variable. You can then pass the variable to a Power Automate flow or use the variable later in the topic, or even in other topics, to control the questions being asked. For example, you can use a variable to decide to skip a question if you have the information you need at that point.

Variables can be defined as either of the following:

- Topic: The variable can only be used within its topic.
- Bot: The variables can be used by any topic.

The solution architect should encourage the use of variables by chatbot authors to improve conversational flow.

## Authentication

You can enable user authentication directly within a Power Virtual Agents bot conversation. User authentication means you can get a user's basic properties such as name and ID in bot variables, but also prompt a user to sign in using an authentication node, retrieve a user token for that user, and then use that token to retrieve the user's information from a back-end system.

Power Virtual Agents supports the following authentication providers:

- Azure Active Directory.
- Any identity provider that is compliant with the OAuth2 standard, , Microsoft Account or Facebook.

Power Virtual Agents supports single sign-on (SSO), which means chatbots can sign the user in if they're in to the page where the bot is deployed. You will need to register the web app in Azure Active Directory to enable SSO.

![Screenshot of single sign on in Power Virtual Agents.](../media/4-sso-authentication.png)

> [!NOTE]
> SSO is only supported on the live website publication channel and the Teams channel

The solution architect should determine if authentication is required for bots and the identity provider used. In many situations, the organization may already have identity providers configured in Azure Active Directory. If creating chatbots for Microsoft Teams then this is simple to configure with the "Only for Teams" option, however if creating chatbots for customers you may need to consider Azure B2B and Azure B2C for authentication.

## Capacity

When you purchase a Power Virtual Agents license, you gain capacity for the specified number of billed sessions. Power Virtual Agents pools this capacity across the entire tenant.

You can monitor how many billed sessions have been used from the Analytics tab in the Power Virtual Agents portal.

![Screenshot of Power Virtual Agents Billed Sessions.](../media/4-analytics-billed-sessions.png)

The solution architect will need to estimate the number of sessions required and ensure that monitoring is implemented to track bot usage and costs.

## Rate limits

Quotas are applied to chatbots to limit how often messages can be sent to the chatbot. The purpose of quotas is to throttle the service load and protect the service from being overloaded.

Quotas for Power Virtual Agents chatbots are defined as requests per minute (RPM). A request is a message from the user to the chatbot, or a message from an Azure Bot Framework Skill, in a single chat session.

The Quota is 600 RPM in the North America region and 800 RPM for the rest of the world.

## Solutions

Power Virtual Agents is solution aware and can be included in solutions and application lifecycle management processes.

> [!IMPORTANT]
> Bots contain many sub-components, such as Topics, that must all be exported and imported together. You should consider creating segmenting your solution and have bots and their sub-components separate in a separate solution from other components.

> [!NOTE]]
> You can only import and export bots with the Power Virtual Agents web app. The feature is not available in the Power Virtual Agents app in Microsoft Teams.

## Deployment

Power Virtual Agents is created in a selected environment. You should ensure that you are using the correct environment for development, test, and production purposes when creating chatbots.

If you are using skills, then you need to define environment variables for each skill.

Post deployment of your bot via a solution there are manual tasks that may need to be performed:

- Power Automate cloud flows: Configure any connections for the first time and visit the Power Virtual Agents portal and select the bot.
- Skills: Add the values for the skills’ environment variables.
- End-user authentication: Configure end-user authentication in the bot so it can take actions on the user’s behalf.
- Escalations: Configure external services that hand off bot escalations to a human agent.
- Multichannel: Configure external channels, such as Facebook, and internal non-Power Virtual Agents services, such as Microsoft Teams.

The solution architect should ensure that these steps are included in the deployment plan for the solution.
