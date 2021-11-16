Sending telemetry from a Power Apps canvas app requires the follow steps:

-   Provision an Azure Application Insight resource at the [Azure portal](https://portal.azure.com/?azure-portal=true)

-   Edit your canvas app to configure the Instrumentation key and publish the app

Now, when users run your published app outside of Power Apps Studio it will send telemetry to Application Insights

In the following video, we walk through configuring a Power Apps canvas app and Application Insights.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWP06z]

In the rest of this topic, we will dive deeper into some of the options to consider when configuring Application Insights for your app.

## Managing usage and costs for Application Insights

The pricing for Application Insights is a pay-as-you-go model based on data volume ingested and optionally for longer data retention. Each [billing account](/azure/cost-management-billing/manage/view-all-accounts/?azure-portal=true) includes 5 GB of log data ingestion so you might find for low usage apps that don't log much data there is no extra ingestion cost. Find more details on [log data ingestion costs](https://azure.microsoft.com/pricing/details/monitor/?azure-portal=true).

When you configure your Application Insights resource, you will choose either the default Log Analytics workspace or you can create a custom workspace. You can read more details on [designing your Log Analytics workspaces and the trade-offs of multiple workspaces](/azure/azure-monitor/logs/design-logs-deployment/?azure-portal=true).

## Multiple apps in one Application Insights resource

You can configure multiple Power Apps to log data to the same Application Insights resource by configuring each to use the same Instrumentation key. Contained in the details of the events logged you will find a ms-appId property that will be tracked to keep each app data identifiable. The default visualizations will mix the data from all the apps making it hard to analyze a single app. You can however see the combined usage of all apps in one place.

When you configure multiple apps to each have their own Application Insights resource and Instrumentation key, the event data is separated. This makes it easy to visualize single app usage patterns but not usage across a set of apps.

If you plan to use Application Insights for multiple apps take your time to consider how you will consume the data.

## Moving from development to production

Once an instrumentation key has been configured on your app, the app has been saved and published, anytime the published app is run it will send telemetry to Application Insights. By default, if you transport the app to test and production environments the app will use the same instrumentation key and log to the same Application Insights resource. The only time the app will not send data is if it is run from Power Apps Studio while you are building the app.

Environment variables are not currently supported for configuring the Instrumentation key.

If you are using the Power Platform CLI to unpack and pack an application that has the Instrumentation key configured, the key is unpacked into a file named AppInsightsKey.json. The CLI along with a source control strategy could be used to allow the app to have different keys.

## No access to my company Azure subscription

You can still use the Application Insights is capability even if you don't have permissions to configure the required Azure resources. Ask your Azure administrator to create the Application Insights resource in the company Azure subscription. The administrator would then share the Instrumentation key with you to use in the application. The administrator can also grant you access to the Application Insights resource so you can view and analyze the data that has been collected.