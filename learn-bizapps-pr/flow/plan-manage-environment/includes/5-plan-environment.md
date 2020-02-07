Environment design is highly dependent upon organizational design.
Considerations include size, locations, regulatory environment, and
appetite for adoption. While environment design is organization-dependent, the following recommendations will aid you in designing the
right landscape for your organization.

> [!NOTE]
> In Module 1, we discussed the default environment. If you
recall, every user within the tenant will automatically have access to
this environment. Since there is no way to remove access to this
environment, it is a common pattern to rename this environment to be
called Personal Productivity to imply this environment is a general use
environment. Administrators should also be aware of the location of this
environment to ensure there are no issues from a data privacy
perspective.

Another important consideration is the aspect of centralization. For
examples, does your organization have a centralized IT function? Are
they responsible for the administration and governance of Power Platform
environment? Or, does your organization have a decentralized
organization where some aspects of technology are managed outside of an
IT department? There are also important considerations when establishing
environment design.

### Sample configurations

The following sections outline sample configurations that may be used
based upon your organization's design and goals.

### Single region organization (centralized)

In this organization, environments are centrally managed and include
isolation for personal productivity, development, testing, and production
purposes. The personal productivity environment can be used to support
scenarios like email notifications, team-based approvals, adhoc data
collection, and the integration with Office 365 services. The central
team that manages environments will also provide access into non-default
environments.

Since this organization operates in a single region, we do not have data
residency concerns and do not require further segregation from other
regions.

![single region](../media/1-single-region.png)

### Single region organization (decentralized)

In this organization, environments are independently managed, and the
administrative responsibilities have been assigned to individual
business units to manage. Once again, this organization operates within
a single region and the default environment has been renamed to be
called Personal Productivity. Additional environments have been created
for respective business units like HR, Finance, Operations, and IT.

![single region decentralized](../media/2-single-region-decentralized.png)

### Multi-region organization (centralized)

In this organization, environments are centrally managed and include
isolation for personal productivity, development, testing, and production
purposes. The personal productivity environment can be used to support
scenarios like email notifications, team-based approvals, adhoc data
collection and the integration with Office 365 services. The central
team that manages environments also provides access into non-default
environments.

Since this organization operates in multiple regions throughout the
world, environments must be created within the region that the
organization operates. To address this requirement, a default
environment has been created within the home region where the tenant was
created. This environment has been renamed Personal Productivity
(default). In addition, Dev, Test, and Production environments have also
been created within this region (North America). To address requirements
in other regions, and to provide symmetry, Personal Productivity, Dev,
Test, and Production environments have also been created in the Asia and
Europe regions.

Since the behavior of the default environment is that all licensed users
are makers in this environment. There is no way to remove users from
this default environment. But, to create a workspace for users to build
adhoc apps and flows, Personal Productivity environments are also
created in Asia and Europe so that users can build these assets without
being concerned with data drifting away from their home region.

Regional teams can apply their IT Change Management practices to these
environments so that business-critical apps and flows can be promoted
through environments to address any compliance requirements.

![multi-region centralized](../media/3-multi-region-centralized.png)

### Multi-region organization (decentralized)

In this organization, their environments are independently managed, and
the administrative responsibilities have been assigned to individual
business units to manage. Once again, this organization operates in
multiple regions and the default environment has been renamed to be
called Personal Productivity and resides within the same region as the
tenant (North America). Within this home region, additional environments
have been created for different business units that provide them with
the autonomy that they require. To illustrate this concept, we have
created environments for the HR, Finance, Operations, and IT business
units.

Since the behavior of the default environment is that all licensed users
are makers in this environment. There is no way to remove users from
this default environment. But, to create a workspace for users to build
adhoc apps and flows, Personal Productivity environments are created in
Asia and Europe so that users can build these assets without being
concerned with data drifting away from their home region.

In addition, we will create environments for business units in Asia and
Europe to ensure they have the autonomy to build apps and flows without
a central authority.

![multi-region decentralized](../media/4-multi-region-decentralized.png)

### Managing exceptions

In the previous four examples, we illustrated configurations that
organizations may choose to implement that address productivity and
governance needs of their organization. However, since every
organization is unique, there may be circumstances where you need to
support exceptions. For example, you may have a tenant-wide DLP policy
that prevents joining SharePoint and Twitter connectors within the same
app or flow. For many job functions, having the ability to retrieve data
from SharePoint and then publish it to Twitter is not a valid business
scenario. But for a business unit like Corporate Communications, this
may be a perfectly valid use case to support.

If users have a need to use a connector like Twitter, but an
organization would like to restrict its use to a broader audience,
governance tools can be layered on top of the out-of-box DLP
capabilities. In this scenario, the Twitter connector can be moved into
the same data group as SharePoint, but we can govern its use. More
specifically, the Power Platform for Admins and Flow management
connectors can aid in the detection of newly created or edited flows
that use this combination of connectors.

When a new or updated flow event occurs, the Flow management connector
can retrieve the flow definition and examine if the Twitter connector is
being used. When this does occur, an administrator can enable their own
governance process. For example, an administrator may restrict accessing
the Twitter connector for a certain group of people, which can be
managed in a security group. Alternatively, an approval can be included
in the flow logic where an administrator can approve enabling the
maker's flow. Should the administrator choose to reject the request,
they can use the Disable Flow as Admin action that is part of the Flow
management connector and it will prevent the flow from running. The
administrator can include additional automation including notifying the
flow maker, via email, indicating this action is not permitted in the
environment. For a detailed walkthrough of a similar governance
scenario, please refer to the [Automating Microsoft Flow Governance blog post](https://flow.microsoft.com/blog/automate-flow-governance/?azure-portal=true).
