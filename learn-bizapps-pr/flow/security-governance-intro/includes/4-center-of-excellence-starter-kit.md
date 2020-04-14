The Power Platform Center of Excellence (COE) Starter Kit is a set of
apps, flows, a custom connector, and a Power BI dashboard that allows
organizations to govern their Power Platform environments. The tool is
freely available for download on
[GitHub](https://github.com/microsoft/powerapps-tools/tree/master/Administration/CoEStarterKit/?azure-portal=true).

The Starter Kit is a great tool for organizations to increase the
visibility of what their makers are doing in their tenant. 
Naturally, this tool immediately applies to two personas: Cyber
Security analysts and Organizational Change Management (OCM) interests.
Makers that are building applications and services that introduce risk
to the organization should be monitored, but makers who are automating
workloads within sanctioned systems and services should be empowered and
encouraged to expand on their efforts.

The Starter Kit does have some prerequisites, including:

-   A global tenant admin, Power Platform Service admin, or Dynamics 365 service admin role is required
    to access the tenant resources.

-   A Power Apps premium license for accessing Common Data Service.

-   An environment with Common Data Service because the Starter Kit solution 
    will need to store metadata about the apps and flows that are detected 
    within an environment.

-   Power BI Desktop to view the reports and visualizations that
    highlight app and flow use within the tenant.

Within the Starter Kit, administrators will discover the tools
and features that are discussed in the following sections.

### DLP Strategy

By using the DLP Editor app, an administrator can explore existing DLP policies
and evaluate the impact of moving a connector from one data group to
another. If a change to a data group has an impact on an existing
app, that will be highlighted in the **Affected Power Apps** list. Then, an
administrator can send an email, through an in-app experience, to the
owner of that application and warn them of the upcoming change.

This current, in-product DLP editor experience doesn't provide this
type of *what-if* analysis, so we recommend that you use the DLP Strategy app that comes
with the COE Starter Kit when making DLP changes.
Using the DLP Strategy app will also help you understand the impact
to existing apps when DLP changes are made and help you reduce the chance of
unknowingly breaking someone's app.

![COE DLP editor](../media/4-coe-dlp-editor.png)

### Catalog tenant resources, visualize data in Power BI

While Admin Analytics, which is found in the Power Platform Admin center,
provides some insight into the use of Power Apps and Power Automate,
it does so within the context of an environment. This parameter makes
developing a holistic picture of usage difficult. However,
using the tools that are provided in the COE Starter Kit brings all these
insights together by using Common Data Service, a model-driven
Power App, and a Power BI dashboard. These assets, plus the
inclusion of flows that will sync data from Office 365 Security and
Compliance logs and through the Power Platform management connectors
into Common Data Service entities, provide the greatest level of 
visibility for administrators.

The Power BI dashboard connects to Starter Kit Common Data Service entities and
contains tabs that provide the following reports:

-   **Overview** - Includes the total number of apps and
        flows that have been created, including a breakdown based on
        the maker's location and the number of apps/flows that they have
        created.

-   **Environments** - Highlights the number of environments that
        have been created and includes the type of environment (Default,
        Production, Sandbox, Trial), and then identifies the creators of the
        environments and when the environment was created.

-   **Apps** - Provides insights into the usage of apps, including
        the number of sessions and users that the app has been shared
        with. This report also breaks down usage by department by pivoting data
        based on the department that has been specified inside of a
        user's Office 365 profile.

 -   **App detail** - Examines the specifics of the app, including
        the connection type and when the app was last published.

-   **Flows** - Displays a flow creation trend that will break down
        when flows were created. This report will also pivot data based
        on the user's department and includes a breakdown of the flows
        that were created by environment.

 -   **Custom Connectors** - Lists all the custom connectors that
        exist within a tenant. This report also lists the users that created the connectors and
        then trends the month that they were created in.

 -   **Makers** - Identifies all the makers within the environment
        and identifies how many apps and flows they have built. A slicer
        exists that allows a consumer of this report to filter based
        on the maker's department.

 -   **Connections** - Displays the number of connections that have
        been established, by connector. This report provides great
        insight into the popularity of specific connectors within your
        tenant.

        ![Center Of Excellence PBI](../media/5-coe-pbi-1.png)

### App Audit

The main purpose of the Sample App Audit process is to demonstrate how an admin 
could identify overshared or often used resources and gather further information, 
like business justification and business impact of an outage, for those apps. 
Having a platform that provides democratized access to technology is
only useful if people don't create many redundant or low-value
applications. Situations might also occur where people create
temporary applications for proof-of-concept purposes. These apps can
clutter an environment if they are not cleaned up. Within the COE
Starter Kit, app makers can be prompted to attest their application
to ensure that it addresses business justification requirements. If
the application doesn't address these requirements, makers can have their 
application removed from the environment.

![COE development compliance center](../media/6-coe-dev-compliance-center.png)

![COE development compliance center](../media/7-coe-dev-compliance-center2-1.png)

### App Catalog

The App Catalog application acts as a catalog that helps with discoverability of apps. 
Users can explore featured apps and browse apps by category. The app catalog can be a 
great entry point to launch apps for end users and makers can explore to see if an 
application already exists before they create another app that provides similar functionality. 
An Admin decides which apps are featured in the App Catalog by completing the **App Audit** process. 
After an app has been approved by the **App Audit** process, these apps can be featured in 
the app catalog.

### Set Owner

Administrating access to applications can be done by the **Owner**
of the application. However, circumstances might occur where you
want an administrator to provide access. By using the **Set Owner** app, you can 
allow for this situation by selecting an app, adding users,
and then indicating whether they should be able to view the app or edit
the app.

![COE email](../media/8-coe-email.png)

### Welcome email to new makers

Power Apps and Power Automate can be discovered virally within an
organization's tenant through the Office 365 portal.
Makers might be confused about whether they are allowed to use these
tools or not. 
    
Detecting when a maker has created their first app or flow
and sending them some useful information to accelerate their
journey will immediately imply that these tools are the ones that they are
permitted to use. Now, they will have a list of resources that can ease
their transition into using these tools.

![Set app owner](../media/9-set-app-owner.png)
