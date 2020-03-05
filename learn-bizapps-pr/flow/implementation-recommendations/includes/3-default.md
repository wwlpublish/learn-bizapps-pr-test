In the introduction module of this learning path, we introduced the 
DLP **Business data only** and **No business data allowed** data groups. 
We can use these data groups to separate connectors that share similar 
characteristics when it comes to their applicability to the business. 
For flows and apps that are processing business-related data, you will 
want to ensure these connectors are placed within the **Business data only** 
data group. When you have connectors that don't support valid business 
use cases, these connectors are best placed in the **No business data allowed** 
data group.

When a DLP policy is created, Microsoft will designate a default data group 
which will be automatically assigned to the **No business data allowed** 
data group.

![default](../media/1-default.png)

An administrator can change the default data group by clicking on the
ellipses **(...)** found beside the data group that they would like to
designate as the default data group.

![new default](../media/2-new-default.png)

Changing the default data group does have implications so administrators
should understand the impact their action will have. Whenever a new
connector is made available for Power Automate (and Power Apps), it will
automatically reside within the default data group. These new connectors
can come from a variety of sources, including: Microsoft, third party
connector providers, and Custom connectors from inside your organization.

When a new Microsoft, or third-party connector, is published, it is
automatically available for use by makers within the environment that
the connector was deployed to. Administrators need to be mindful of this
behavior as it has an impact on DLP policies. For example, let's assume
an organization has encouraged users to build flows that take advantage
of Office 365 connectors. In addition, administrators have tried to
prevent makers from sending business data from Office 365 systems to
consumer-based services like email and file sharing. 

As a result of this strategy, consumer-based connectors have been placed 
into the **No business data allowed** data group, which is also our default 
data group. Suppose Microsoft introduces a new Office 365 connector, it will
be placed into the default data group as a result. This means that a
maker can build a flow that includes data from this new Office 365
service and send that data to a consumer-based email or file sharing
service.

It is important that Administrators understand the behavior of the
default data group to avoid undesirable data leakage. Administrators can
be made aware of new connectors that have recently been published by
provisioning a flow template that detects when new connectors have been
published. We will discuss this template, and others, in a later module of
this learning path.

Custom connectors also pose a challenge for administrators. Much like
Microsoft and third-party connectors, custom connectors will also be
placed in the default data group. However, they will not be visible,
which can create challenges. 

The good news is that by using PowerShell or the Power Platform Management 
connectors, an administrator can add Custom connectors to a data group. 
Once a connector is added, the connector can be managed through the Power 
Automate Admin center. We will discuss this topic further in the 
**Configure DLP for Custom connectors** unit later in this module.