Microsoft Power Platform Center of Excellence (CoE) is a collection of templates that has components and tools to help you get started with developing a strategy for adopting and supporting Microsoft Power Platform, with a focus on Power Apps and Power Automate. CoE is an extension of the admin center and falls within the templates and customizations category.

A Center of Excellence is designed to drive innovation and improvement. As a central function, a CoE can break down geographic and organizational silos to bring together like-minded people who have similar business goals to share knowledge and success while simultaneously providing standards, consistency, and governance to the organization. A CoE can be a powerful way for an organization to align around business goals rather than individual department metrics.

This learning document focuses on getting started with the initial configuring of the CoE kit in your tenant, focusing on the core setup components, governance components, audit log data, and the Microsoft Power BI report.

Make sure that you meet the following requirements before you begin this module:

-   Admin account

    -   Microsoft Power Platform service admin, global tenant admin, or Microsoft Dynamics 365 service admin for access to all tenant resources through the Power Apps APIs

    -   This solution will work for environment admins, but the view will be restricted to only the environments that an environment admin has access to

    -   This account must be email enabled

-   Premium licenses are required to use the CoE Starter Kit. Depending on what components you will use, your organization size, and the existing licenses that are available in your organization, you will require a Power Apps per user or per app license, a Power Automate per user or per flow license, or a combination of these licenses.

-   Environment with a Microsoft Dataverse instance, where the user who is installing the solution has the System Administrator security role

-   The environment must have a data loss prevention (DLP) policy that allows:

    -   [Dataverse (legacy)](/connectors/commondataservice/?azure-portal=true) 

    -   [Dataverse](/connectors/commondataserviceforapps/?azure-portal=true) 

    -   [Office 365 Users](/connectors/office365users/?azure-portal=true), 

    -   [Microsoft Power Platform for Admins](/connectors/powerplatformforadmins/?azure-portal=true)

    -   [Power Automate Management](/connectors/flowmanagement/?azure-portal=true) 

    -   [Office 365 Outlook](/connectors/office365/?azure-portal=true) 

    -   [Power Apps for Admins](/connectors/powerappsforadmins/?azure-portal=true) 

    -   [Power Apps for Makers](/connectors/powerappsforappmakers/?azure-portal=true) 

    -   [SharePoint](/connectors/sharepointonline/?azure-portal=true) 

    -   [Azure Active Directory (Azure AD)](/connectors/azuread/?azure-portal=true) 

    -   [Power Automate for Admins](/connectors/microsoftflowforadmins/?azure-portal=true) 

    -   [RSS](/connectors/rss/?azure-portal=true) 

    -   [Office 365 Groups](/connectors/office365groups/?azure-portal=true) 

    -   [Approvals](/connectors/approvals/?azure-portal=true) and HTTP to be used together

    > [!NOTE]
    > Those connectors must be in the business data-only bucket of the DLP policy for this environment. If you're using the [audit log](/power-platform/guidance/coe/setup-auditlog/?azure-portal=true) solution, the custom connector that is used to connect to the Microsoft 365 audit log must be included in your business data-only bucket as well.

-   If multiple DLP policies apply to the same environment, then all of them must have the connectors that the CoE Starter Kit uses in business data only or, if you have a policy that applies to all environments that you don't want to change, you can exclude the CoE environment from that policy. For more information, see [DLP policy scope](/power-platform/admin/wp-data-loss-prevention?azure-portal=true#policy-scope).

-   You've downloaded the CoE solution and CoE Power BI dashboard files to your device. The entire content package can be downloaded directly at [aka.ms/CoEStarterKitDownload](https://aka.ms/CoEStarterKitDownload/?azure-portal=true).

    > [!NOTE]
    > The Admin | Sync Template flows search through all resources that are stored in Microsoft Power Platform and copy details in each resource (for example, apps and flows) to Dataverse (table definitions are provided in this solution). All data that is displayed in most of the starter kit components must be in Dataverse, which means that the sync template must be configured for everything else to work. The sync flows run daily overnight. When you first set up the CoE Starter Kit, you can manually start the Admin | Sync Template v2 flow, which will start the process of searching and storing the information in Dataverse.

