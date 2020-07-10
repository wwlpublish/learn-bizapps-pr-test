After a bot is deployed and customers are interacting with it, statistics related to the bot will become available. You can access this information through the Analytics tab in the side navigation pane. Here, you can find key performance indicators (KPIs) showing the volume of sessions your bot has handled, how effectively your bot was able to engage end-users and resolve issues, escalation rates to human agents, and abandonment rates during conversations. You will also find customer satisfaction information at the KPI level as well as in the Customer Satisfaction tab.

> [!div class="mx-imgBorder"]
> [![Analytics](../media/5-1.png)](../media/5-1.png#lightbox)

You can also view detailed session history and transcripts by selecting Sessions from the Analytics tab. This enables you to download a file with the full session transcript. This can be a helpful way for you to tune the performance of your bot and change the content in your topics to improve your bot's efficiency.

### Analyzing bot performance and usage

The Summary page gives you a broad overview of your bot's performance. It uses artificial intelligence (AI) technology to show you which topics are having the greatest impact on escalation rate, abandon rate, and resolution rate (see the table under [Summary charts](https://docs.microsoft.com/power-virtual-agents/analytics-summary#summary-charts/?azure-portal=true) for more information on these metrics).

> [!div class="mx-imgBorder"]
> [![Analytics summary page](../media/5-2.png)](../media/5-2.png#lightbox)

The Summary page includes a variety of charts with graphical views of your bot's key performance indicators.

**The different charts included are:**

- **[Summary charts](https://docs.microsoft.com/power-virtual-agents/analytics-summary#summary-charts/?azure-portal=true)**: Summarizes KPIs for a specified period and the percent change over the period.

- **[Engagement over time chart](https://docs.microsoft.com/power-virtual-agents/analytics-summary#engagement-over-time-chart/?azure-portal=true)**: Graphical view of the number of engaged and unengaged sessions over time.

- **[Session outcomes over time chart](https://docs.microsoft.com/power-virtual-agents/analytics-summary#session-outcomes-over-time-chart/?azure-portal=true)**: Graphical view of the daily resolution rate, escalation rate, and abandon rate over the specified time period.

- **[Resolution rate drivers chart](https://docs.microsoft.com/power-virtual-agents/analytics-summary#resolution-rate-drivers-chart/?azure-portal=true)**: Displays topics in order of their impact on the resolution rate over the specified time period.

- **[Escalation rate drivers chart](https://docs.microsoft.com/power-virtual-agents/analytics-summary#escalation-rate-drivers-chart/?azure-portal=true)**: Displays topics in order of their impact on the escalation rate over the specified time period.

- **[Abandon rate drivers chart](https://docs.microsoft.com/power-virtual-agents/analytics-summary#abandon-rate-drivers-chart/?azure-portal=true)**: Displays topics in order of their impact on the abandon rate over the specified time period.

For more information see [Analyze bot performance and usage](https://docs.microsoft.com/power-virtual-agents/analytics-summary/?azure-portal=true).

The Engagement Rate Drivers, Abandon Rate Drivers, and Resolution Rate Drivers charts use natural language understanding to group issues as topics. These charts show you the topics that are having the most impact on the performance of your bot.

### Analyze customer satisfaction for Power Virtual Agents bots

The Customer Satisfaction page provides a detailed view of customer satisfaction (CSAT) survey data, including the average CSAT score over time, and the topics that are having the most impact on the CSAT score. The Customer Satisfaction page includes a variety of charts with graphical views of your bot\'s customer satisfaction indicators.

**The different charts included are:**

- **[Customer satisfaction drivers chart](https://docs.microsoft.com/power-virtual-agents/analytics-csat#customer-satisfaction-drivers-chart/?azure-portal=true)**: Uses AI to group related support cases as topics, then displays topics in order of their impact on customer satisfaction over the specified time period.

- **[Scores over time chart](https://docs.microsoft.com/power-virtual-agents/analytics-csat#scores-over-time-chart/?azure-portal=true)**: Provides a graphical view of the average CSAT score over the specified time period.

- **[Average CSAT score](https://docs.microsoft.com/power-virtual-agents/analytics-csat#average-csat-score-chart/?azure-portal=true)**: Provides a graphical view of the average of CSAT scores for sessions in which customers respond to an end-of-session request to take the survey.

- **[CSAT survey response rate](https://docs.microsoft.com/power-virtual-agents/analytics-csat#csat-survey-response-rate-chart/?azure-portal=true)**: Shows the number of CSAT surveys that were presented and the percentage of surveys that were completed.

For more information see [Analyze customer satisfaction](https://docs.microsoft.com/power-virtual-agents/analytics-csat/?azure-portal=true).

### Analyze topic usage in Power Virtual Agents

The topic details page provides a view into the performance of individual topics and how they can be improved. You can display the topic details page by selecting the Detail link in one of the following charts on the [Summary](https://docs.microsoft.com/power-virtual-agents/analytics-summary/?azure-portal=true) and [Customer Satisfaction](https://docs.microsoft.com/power-virtual-agents/analytics-csat/?azure-portal=true) pages:

- **Summary Page**

  - [Escalation rate drivers](https://docs.microsoft.com/power-virtual-agents/analytics-summary#escalation-rate-drivers-chart/?azure-portal=true)

  - [Abandon rate drivers](https://docs.microsoft.com/power-virtual-agents/analytics-summary#abandon-rate-drivers-chart/?azure-portal=true)

  - [Resolution rate drivers](https://docs.microsoft.com/power-virtual-agents/analytics-summary#resolution-rate-drivers-chart/?azure-portal=true)

- **Customer Satisfaction Page**

  - [Customer satisfaction drivers](https://docs.microsoft.com/power-virtual-agents/analytics-csat#customer-satisfaction-drivers-chart/?azure-portal=true)

> [!div class="mx-imgBorder"]
> [![Escalation rate drivers](../media/5-3.png)](../media/5-3.png#lightbox)

The topic details page can also be displayed by opening an individual topic from the Topics page and selecting Analytics at the top of the page. You can also hover over an item and select the go to analytics icon.

> [!div class="mx-imgBorder"]
> [![Analytics can be accessed from the topics page, and from the individual topic.](../media/5-5.png)](../media/5-5.png#lightbox)

The topic details page includes a variety of charts with graphical views of a topic's key performance indicators.

The different charts included are:

- **[Topic Summary charts](https://docs.microsoft.com/power-virtual-agents/analytics-topic-details#topic-summary-charts/?azure-portal=true)**: Summarizes topic performance indicators for the specified time period and the percent change over the period.

- **[Impact Summary charts](https://docs.microsoft.com/power-virtual-agents/analytics-topic-details#impact-summary-charts/?azure-portal=true)**: Summarizes the impact of the topic on key performance indicators for the specified time period.

- **[Topic Volume by Day chart](https://docs.microsoft.com/power-virtual-agents/analytics-topic-details#topic-volume-by-day-chart/?azure-portal=true)**: Provides a graphical view of the number of sessions for the topic over the specified time period.

For more information see [Analyze topics usage](https://docs.microsoft.com/power-virtual-agents/analytics-topic-details/?azure-portal=true).

### Analyze session information in Power Virtual Agents

Having access to session information related to your bot can help to identify potential changes that might need to be made. By default, you can download up to seven days of bot conversation transcript sessions from the past 30 days directly from the Power Virtual Agents portal.

Session transcripts are available by navigating to analytics and selecting the sessions tab. In the sessions tab you will be able to see all the different sessions that have been run for it. A session represents a conversation that someone had with the bot. If your bot had a high number of sessions, they will be broken down into multiple rows to make it easier to manage the sessions. Each row will contain 2500 sessions. You can click on each row to download the session transcripts for the specified time frame.

> [!div class="mx-imgBorder"]
> [![Analytics sessions for download](../media/5-6.png)](../media/5-6.png#lightbox)

The downloaded file contains the following information:

- **SessionID:** A unique identifier per session.

- **StartDateTime:** Time at which the session started. Entries are sorted by this column in descending order.

- **InitialUserMessage:** First message typed by the user.

- **TopicName:** Name of the last authored topic that was triggered in this session.

- **ChatTranscript:** Transcript of the session in the following format:

  - User says:" "; Bot says:" "; structure

  - Conversation turns are separated by semicolons

  - Bot says doesn't include the options presented to the user.

- **SessionOutcome**: Outcome of the session (Resolved, Escalated, Abandoned, Unengaged).

- **TopicId:** A unique identifier of the last authored topic triggered in this session.

For more information on analyzing session information, see [Analyze session information.](https://docs.microsoft.com/power-virtual-agents/analytics-sessions/?azure-portal=true)
