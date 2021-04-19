Power Virtual Agents is available as both a standalone web app, and as a discrete app within Microsoft Teams. Most of the functionality between the two is the same. However, there are different reasons to choose one version or the other based on your requirements.

## Power Virtual Agents Web app

You will use standalone Power Virtual Agents if:

- You are an IT administrator or consultant and want to create bots for your customers to engage with.
- You want to create bots for external customers.
- You have used chatbot services in the past and want to trial or test Power Virtual Agents.
- You are familiar with advanced chatbot concepts, such as entities and variables, and want to create complex chatbots.

Access the [standalone web app](https://powerva.microsoft.com).

## Power Virtual Agents in Microsoft Teams

You will use Power Virtual Agents in Microsoft Teams if:

- You are an employee or member of an organization or team and want to create chatbots to answer common questions posed by other employees or teammates.
- You want to use advanced concepts, such as entities and variables, but have the chatbot available only internally.
- You want to create and distribute a chatbot in the shortest time possible.

![Screenshot of Power Virtual Agents in Microsoft Teams.](../media/6-pva-bot-in-teams.png)

The Power Virtual Agents app in Microsoft Teams supports single sign-on (SSO), which means chatbots can sign the user in silently, without having the user enter their credentials.

Power Virtual Agents in Microsoft Teams does not require more licensing as the license is included with Microsoft 365 subscriptions.

> [!IMPORTANT]
> Access is limited however to the membership of the Microsoft Team that the chatbot is deployed to. The chatbot cannot be deployed to other channels.

### Limitations

Power Virtual Agents in Microsoft Teams has many limitations such as:

- Power Virtual Agents in Microsoft Teams is limited to the standard Power Automate connectors available for flows triggered from Power Virtual Agents.
- Power Virtual Agents in Microsoft Teams can be integrated with Azure Bot Framework skills but require a Power Virtual Agents standalone license.
- Power Virtual Agents in Microsoft Teams cannot integrate Microsoft Bot Framework dialogs and cannot be used with Azure Bot Framework Composer.
- Power Virtual Agents in Microsoft Teams cannot be included in solutions.

### Service limits

Power Virtual Agents in Microsoft Teams is limited to 10 sessions per user every 24 hours.
