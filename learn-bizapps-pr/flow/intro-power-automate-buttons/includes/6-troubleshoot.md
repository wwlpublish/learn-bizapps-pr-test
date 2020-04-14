A flow can fail due to one of the following three reasons:

- User authorization

- Data connections

- Power Automate actions or conditions

### User authorization

The flow works only for users of your tenant. Hence, you need to confirm that 
the user's Office 365 account is active. If the account is active, then
confirm that the user's account has a Microsoft Power Automate license.

### Data connections

Connectors need both authentication and authorization. Depending on the
connector, you'll need a URL as well. Consequently, you need to confirm that 
all connections are correct for the flow to run.

To validate your connector, follow these steps:

1. Sign in to your [Power Automate](https://flow.microsoft.com/?azure-portal=true) 
    tenant.

2. On the left vertical pane, expand **Data** and then select 
    **Connections**. Verify the **Status** of each connector.

When you share a button, you can allow people with whom you've 
shared the button to use all connections that your button uses. 
You can also require them to use their own connections. 
If you allow others to use your connections, they can't access 
the credentials in your connection or reuse them in any other flow.

### Power Automate actions or conditions

In the app, select the activity on the bottom horizontal menu and
find your flow. Check to see if a red exclamation icon is on your flow.
If so, the flow has an error and you will see that Power Automate has failed.

![Late to work flow](../media/late-at-work-flow.png)

Select the flow to determine where the error has occurred. The **Summary** section
will tell you which action has failed. You can select **More** to get
more information, which should provide all the details that you
need to fix the flow. Additionally, you can select the other steps to see how
the action ran and view the schema of the inputs and outputs.

![Late to work flow](../media/late-at-work-flow2.png)

By selecting the flow name, you will be redirected to another screen that gives
you the following options:

-   Enable flow

-   Edit flow

-   Owners

-   Users and connections

-   Run history

-   Save as

-   Delete flow

Selecting the run history will provide you with additional clues such as how many
times the flow has failed, whether it failed at the same action or condition every
time, and so on. You can then select **Edit flow** and fix the issue.
