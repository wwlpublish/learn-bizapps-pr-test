When provisioning a Power Apps portal, one of the most important choices is to consider the audience and workload and choose a specific starter portal that would best align with the particular business requirements.

There are a number of starter portals available that can be provisioned. These will accelerate the configuration of a portal based on the intended audience and workload.  

If you are using Dynamics 365 first-party apps (For example; Dynamics 365 Sales or Dynamics 365 Service) you have a choice of five different starter templates;

- Community Portal
- Customer Self Service
- Employee Self-Service
- Partner Portal
- Custom Portal

If you are building a custom business application using the Common Data Service without Dynamics 365 apps enabled, your only choice is the *Portal from Blank* option.

> [!NOTE]
> Specific features and components of one specific starter portal can be added to another Starter Portal as required.

## Starter Portal types

| Starter Portal        | Audience          | Workload                                                     |
| --------------------- | ----------------- | ------------------------------------------------------------ |
| Community Portal      | Partner, Customer | Choose this option to provision a portal focused on an online community.  This portal will contain features such as forums, ideas, blogs and case management. |
| Customer Self Service | Partner, Customer | This option provides the ability for portal users to search knowledge articles, submit cases and participate in discussion forums to resolve issues. |
| Employee Self-Service | Employee          | This portal allows employees to be able to access a centralized knowledge articles and also submit cases. |
| Partner Portal        | Partner           | Choose this option to build a portal where external partners can manage and collaborate on Accounts and Opportunities. Addons are available for Dynamics 365 for Field Service or Dynamics 365 for Project Service. |
| Custom Portal         | Partner, Customer | The custom portal is meant for unique line of business scenarios where the other starter portals are not a good fit. The custom portal can be configured to address a variety of requirements.  Specific features from the other starter portals can be incorporated into the starter portal. |
| Portal from blank     | Partner, Customer, other external stakeholder | The portal from blank is similiar to the custom portal.  This template is meant for unique line of business scenarios where Dynamics 365 apps are not enabled. The Portal from blank can be configured to address a variety of requirements. |

> [!IMPORTANT]
> Review current licensing guides to determine the licenses, subscriptions and capacity required for internal and external authenticated users as well as anonymous page views. Please refer to the [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/p/?LinkId=866544/?azure-portal=true) or the 
[Power Apps Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130/?azure-portal=true).  Integration to other services such as SharePoint, Power BI or Azure Blob Storage will require appropriate capacity and licensing for these services.


You will need to define the type of audience who will visit the new portal. This will determine what options of portals you will be given.

## Starter Portal features

All starter portals are built on a common foundation (portal base)  and include the following features:

- Ability to configure the portal using the Portal studio
- Content management including content publishing, design, theming, search, multi-lingual support, templating.
- Extensibility built on Web Pages, Templates, Entity Forms, Entity Lists, and more. 
- Security based on identity management, integration with authentication providers, web roles, content permissions, entity permissions.
- Common features like Ads, Polls, Ratings, and Comments. These features are not standalone and can be used throughout other parts of the implementation. For example, ratings and comments can be enabled for a page, ads can be included as part of a template.  Some features will require Dynamics 365 apps to be enabled (e.g. Knowledge Articles require Dynamics 365 Service)

Where the starter portals are different is around the functional areas targeting *specific business processes* such as Case Management. These features are deployed as additional managed solutions making it easier to add missing ones if required.

| Feature                                | Custom Portal or Portal from blank | Customer Self-Service | Partner Portal | Employee Self-Service Portal | Community Portal |
| -------------------------------------- | ------------- | --------------------- | -------------- | ---------------------------- | ---------------- |
| Portal Base                            | •             | •                     | •              | •                            | •                |
| Knowledge Management                   |               | •                     | •              | •                            | •                |
| Support/Case Management                |               | •                     | •              | •                            | •                |
| Forums                                 |               | •                     | •              | •                            | •                |
| Azure AD Authentication <sup>^</sup>   |               |                       |                | •                            |                  |
| Ideas                                  |               |                       |                |                              | •                |
| Blogs                                  |               |                       |                |                              | •                |
| Partner Pipeline                       |               |                       | •              |                              |                  |
| Project Service Automation Integration |               |                       | •              |                              |                  |
| Field Service Integration              |               |                       | •              |                              |                  |

Support for Azure AD as authentication provider is included in portal base. Azure AD Authentication feature, as used by Employee Self-Service Portal, is different. In Employee Self-Service Portal, the login process validates that the user has at least a Dynamics 365 Team license and access is denied if the user does not have a Dynamics 365 license assigned.

If a particular feature, for example Case Management, is available in two different starter portals, it will be the **same** feature offering the **same** functionality.

## Additional considerations

### Dependencies

Some starter portals have prerequisites for their installation, so an installation will fail if the prerequisites are not met. For example, to install the Partner Field Service for a partner portal, the Partner Portal and Field Service solutions must have already been installed. If you attempt to install the Partner Field Service first, the installation will fail and give you an error message.  If Dynamics 365 apps are not enabled, the only portal template available will be *Portal from blank*.

### Employee Portal access 

When an employee accesses the portal functionality, appropriate Dynamics 365 or Power Apps license may be required. The easiest way to assess the licensing requirements is to keep in mind that the requirements do not change depending on method of access. They are the same regardless whether employee accesses Dynamics 365 using a portal or via one of the Dynamics 365 first-party Apps. 

For example, if an employee has a Dynamics 365 Customer Service license assigned, they cannot manage opportunities using Partner Portal as access to opportunities require Dynamics 365 Sales license.

License required depends on the entities and functionality accessed. See [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409) or [Power Apps Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=2085130&clcid=0x409/?azure-portal=true)for more details.

### Third-party solutions

Some third-party solutions add features to the portal that can greatly enhance user experience. Some of these capabilities may be agnostic to the choice of a starter portal, for example: 

- Live Chat and Cobrowse
- Click to Call
- Customer Journey tracking

On the other hand, Power Platform and Dynamics 365 ISVs and System Integrators offering Power Platform and Dynamics 365 vertical solutions quite often may include portal extensions specifically designed for their solution needs. When working with a vendor who offers portals as part of their overall solution, it would be sensible to discuss portal requirements and the starter portal selection beforehand.

