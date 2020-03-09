In this unit, we will discuss some of the templates that allow
administrators to automate the governance of their environments.

### Template #1 - List New Microsoft Flow Connectors

The first template that we will discuss is called **List New Microsoft Flow Connectors**. 
This template will help us discover new connectors that have been deployed in a Power 
Platform environment. You can provision this template by accessing the 
[List new connector template](https://preview.flow.microsoft.com/galleries/public/templates/5a6ef26db3b749ed88b7afb377d11ecf/list-new-microsoft-flow-connectors/?azure-portal=true)
directly, or searching for it in the Template gallery.

![List new connectors](../media/3-list-new-connectors.png)

Once you select this template, you will find a description of what the
flow does and will be prompted to establish new connections for the
connectors that are used by the flow. If you already have existing
connections for these connectors, you can click on the **Continue** button.

![continue](../media/4-continue.png)

After clicking on the **Continue** button, the flow will be loaded into the
Power Automate designer experience. From here, you can modify the flow to
suit your needs. For example, this flow is configured to run every day at
9am. The flow allows you to select an environment and the flow then checks 
to see if there are any connectors that have been provisioned within the 
past 24 hours. You can modify this expression to include a broader duration 
if you wish.

![Provisioned flow](../media/5-provisioned-flow.png)

There are no additional configuration changes that you need to make. You
can now run this flow, and if new connectors have been deployed in the
past day, you will receive an email like the following. In this case, we
have a custom connector that has been recently deployed in our environment.

As an administrator this is an important email as I can now go ahead and
adjust my DLP policies to ensure this connector has been placed in the
correct data group.

![sample email](../media/6-email.png)

> [!NOTE]
> Depending upon what environment you are running this flow in,
you may encounter a DLP error based upon activities performed in
previous modules. Modify or remove DLP policies as appropriate.

### Template #2 - Get list of new PowerApps, Flows, and Connectors

Another useful template that administrators can take advantage of is 
**Get list of new PowerApps, Flows, and Connectors**, which can be found by
searching in the template gallery or by selecting the
[template](https://preview.flow.microsoft.com/galleries/public/templates/0b2ffb0174724ad6b4681728c0f53062/get-list-of-new-powerapps-flows-and-connectors/?azure-portal=true) here.

This template is like the template that we just discussed, with the
exception that it will search all environments within the tenant and
will also identify new apps and flows, in addition to connectors.

![Get apps flow](../media/7-get-apps-flows.png)

When you select this template, you will also have to create connections
to the connectors used in the flow, if they have not already been
established. Once your connections have been established, you can click on
the **Continue** button to provision the flow.

![List new apps flows](../media/8-list-new-apps-flows.png)

This flow is also configured to run daily and there is a variable called
**reportingperiod** that can be modified. This value indicates the number of
days back that the flow should evaluate when looking for new apps, flows, and 
connectors. The default value is -7, which means that this flow will
look for new assets created in the past seven days.

![configure flow](../media/9-configure-flow.png)

When you run this flow, a report will be generated that identifies every
new flow, app, and connector that has been created in your tenant over the
past seven days. Depending upon how many environments and apps and flows you
have in your tenant, this flow can take several minutes to complete execution.

![output report](../media/10-flow-output.png)

### Template #3 - Monitor Office 365 audit logs for specific details and send alerts

The last template that we are going to discuss is called **Monitor Office
365 audit logs for specific details and send alerts**. It can be found by
searching for it in the template gallery or by directly selecting the 
[template](https://preview.flow.microsoft.com/galleries/public/templates/4a7ea95259f1404e95855f6b053360b1/monitor-office-365-audit-logs-for-specific-details-and-send-alerts/?azure-portal=true) here.

![monitor](../media/11-monitor.png)

The purpose of this template is to search the [Office 365 Security and Compliance](https://protection.office.com/unifiedauditlog/?azure-portal=true) logs for Power Automate events on a configured interval. The events that are captured in these logs include:

-   Created flow

-   Edited flow

-   Deleted flow

-   Edited flow permissions

-   Deleted flow permissions

-   Started a Flow paid trial

-   Renewed a Flow paid trial

![events](../media/12-events.png)

Before you can use this flow, you need to establish connections to
SharePoint and Office 365 Outlook. The reason for this is that you will
store the names of events that you want to subscribe to in SharePoint and
you will use the Office 365 Outlook connector to send your results out to
your intended audience. Once you have created your connections, you can
click on the **Continue** button to edit the flow.

![provision flow](../media/13-provision-flow.png)

Before you configure your flow, you need to create a custom SharePoint list
where you can store the operations that you will pass into the Office 365
API. In our scenario, you are interested in knowing when there are new
flows created. As a result, we will add a record that includes a Title
of CreateFlow. A complete list of supported operations can be found in this
[blog post](https://flow.microsoft.com/blog/accessing-office-365-security-compliance-center-logs-from-microsoft-flow/?azure-portal=true).

![SharePoint](../media/14-sharepoint.png)

With your SharePoint list created, you can edit your flow so that you can
connect to your list. While you are in the flow designer, there are a few
actions that you need to configure including the Recurrence trigger that
indicates when our flow will run. We also need to populate a SendTo
variable, which represents an email address that you want to send your
output to. Should you want a different duration of events to query for, 
you can modify the expressions in the FromDate and ToDate variable.

![Configure part 1](../media/15-configure-part-1.png)

When connecting to the Office 365 Security and Compliance API, we need 
to provide our Office 365 admin credentials. You will do so by
populating the **Username** and **Password** that are found in the
**advanced options** in the **HTTP** action.

![HTTP](../media/16-http.png)

You are now ready to run your flow. Provided you have created a flow within
your tenant in the past 30 days, you should receive an email that looks
like the following:

![email](../media/17-email.png)
