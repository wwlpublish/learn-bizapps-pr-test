In the previous unit, we discussed steps that can be taken to support
communicating with users once you are ready to make governance changes.
However, it is important to understand what the impacts of an upcoming
change are before sending out communications. In this unit, we'll discuss 
how the Power Platform Admin Analytics feature can aid administrators in 
understanding how Power Automate is being used in your organization to help
you avoid undesirable impacts.

There are six Power Automate reports that are available inside of the
Power Platform Admin Center including:

-   Runs

-   Usage

-   Created

-   Errors

-   Shared

-   Connectors

Let's discuss each of these reports and highlight how administrators can 
leverage them to gain insights about how their users are utilizing Power 
Automate.

To access the Admin Analytics feature, go to the [Power Platform
Admin Center](https://admin.powerplatform.microsoft.com/) using an
account that has environment or tenant admin privileges. Once you have
logged in, expand the **Analytics** drop-down from the left navigation
section and click on **Power Automate**.

![Power Automate analytics](../media/1-ppac.png)

Earlier in this learning path, we discussed environment and tenant scopes. 
When it comes to Admin Analytics, everything is in the context of an environment.
There is currently no way to see aggregated analytics, across a
tenant, in this experience. A tenant administrator will be able to see
analytics on a per-environment basis. Environment administrators will
only see analytics for the environments that they are admins in. 
To change the environment, an administrator can click on the filter icon in
the upper right-hand corner. From there, they can select their desired
**Environment** and the **Time period** that they would like to see
analytics for.

The Power Platform Admin Center will store analytics for up to 28 days,
but administrators can filter based upon the last 14 and 7 days. In
addition, the analytics are not aggregated in real time. Administrators
can expect up to a three-hour delay before the latest analytics are
published.

![filters](../media/2-filter.png)

Let's look at each of the reports that are available in the Power
Automate Analytics feature, starting with the Runs report. Within the Runs report,
administrators will be able to determine the number of flow runs within
that environment per Day, Week, and Month. In addition, Power BI embedded
slicers allow an administrator to filter data based upon whether the
run was successful, failed, or canceled.

For organizations who are adopting Power Automate, this report can
provide insights that help determine the level of adoption within the
organization. The people who are responsible for change management can
use this data to help support training and adoption campaigns by being
able to show measurable progress.

![Runs feature](../media/3-runs.png)

The Usage report outlines the Types of flows in use, including whether
or not the flow is Scheduled, Button clicked, or System Event driven. In
addition, for each flow in use, the number of Runs are aggregated so an
administrator can see how frequently the flows run and what is the most
frequently run flow. The Flow creator email is also captured so that if
an administrator needs to contact this person, they have their email
address. Lastly, there is a trend that highlights the number of unique
flows in use per day based upon the Time period filter.

![Usage report](../media/4-usage.png)

When looking to identify new flows, the Created flow report will
identify these new assets. Once again, these flows will be broken down
by their Type: Scheduled, Button clicked, or System Events. The flows
that have been recently created will also be listed in a table that
includes the Created date and the Flow creator email address. Lastly, a
trend of when these flows were created is also displayed.

This report is interesting for people responsible for change management. 
Perhaps the organization has recently provided Power Automate training 
and wants to see if people are putting these new skills to use.

![Created date](../media/5-created.png)

For Administrators, detecting when makers are experiencing errors with
their flows can become a great concern if a flow continues to fail and
supports an important business process. The Errors report will help
administrators identify flows that are failing and will display the
Error count, the Last occurred timestamp and the Flow creator email. In
addition, a pie chart will break down the Error types that will
highlight the different types of errors that makers have been
experiencing.

![error types](../media/6-errors.png)

The Shared report will identify the Types of flows shared, including
System Events, Button clicked, and Scheduled. In addition, a table will
be displayed that includes the Flow name that was shared, the number of
Shares and the Flow creator's email. Lastly, a trend will display what day
the flow was shared on within the configured time period.

This report is useful for identifying makers who are sharing their work with 
others within the organization. These makers are often referred to as champions 
who should be empowered so they can drive further business results.

![Shared report](../media/7-shared.png)

The last report to discuss is, often times, the most important
report to consider when evaluating DLP changes. The Connectors report
identifies all the connectors that have been involved in Flow runs
and how many Connector calls have been made. Much like you would expect
with a Power BI embedded experience, an administrator can filter out
connectors as required. 

For example, consider a situation where an administrator wants to make a 
DLP connector change that involves the SharePoint connector. They can click 
on the SharePointOnline connector from the Connectors by flow runs visualization. 
As a result, the Connectors by connector calls visualization will be updated. In
addition, we will see a table updated called Flows using connectors. In
this visualization, we will see all the flows that use the SharePoint
connector and the Flow creator email address. This will help us identify
all of the makers that we should proactively reach out to before making
any DLP changes.

This report is useful in both governance and change management
situations. It allows administrators to identify if connectors are being
used that are not in the best interests of the organization and allows
administrators to work with those people to better understand why they
are using those connectors, and potentially implement actions that
prevent further usage.

On the other hand, if an administrator discovers there is lots of
utilization around a particular connector, like Microsoft Forms, perhaps
they want to evangelize its usefulness with other business units in an
attempt to scale the organization and reap more benefits for the
organization.

![Connectors report](../media/8-connectors.png)