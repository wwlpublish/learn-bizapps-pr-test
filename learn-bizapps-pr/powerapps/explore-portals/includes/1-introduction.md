When provisioning a Power Apps portal, one of the most important choices is to consider the audience and workload, and choose a specific portal template that would best align with the particular business requirements.

There are a number of portal templates available that can be provisioned. These will accelerate the configuration of a portal based on the intended audience and workload.  

![Portal Templates](../media/2-1-portal-templates.png)

If you are building a custom business application using the Common Data Service without Dynamics 365 apps enabled, your only choice is the Portal from blank option.

If you are using Dynamics 365 first-party apps such as Dynamics 365 Sales or Dynamics 365 Service, you have a choice of five additional portal templates:

- Community Portal
- Customer Self-Service
- Employee Self-Service
- Partner Portal
- Custom Portal (Dynamics 365 Supply Chain Management)

> [!NOTE]
> Specific features and components of one specific starter portal can be added to another Starter Portal as required.

## Portal templates

| Portal template       | Audience          | Workload                                                     |
| --------------------- | ----------------- | ------------------------------------------------------------ |
| Community             | Partner, Customer | Choose this option to provision a portal focused on an online community.  This portal will contain features such as forums, ideas, blogs, and case management. |
| Customer self-service | Partner, Customer | This option provides the ability for portal users to search knowledge articles, submit cases and participate in discussion forums to resolve issues. |
| Employee self-service | Employee          | This portal allows employees to be able to access a centralized knowledge article and also submit cases. |
| Partner               | Partner           | Choose this option to build a portal where external partners can manage and collaborate on Accounts and Opportunities. Addons are available for Dynamics 365 for Field Service or Dynamics 365 for Project Service. |
| Portal from blank     | Other             | The portal from blank is meant for unique line-of-business scenarios where the other templates are not a good fit. The portal can be configured to address a variety of requirements. If portal from blank is provisioned within a Common Data Service environment with Dynamics 365 apps enabled, specific features from the other portals can be incorporated into the portal later on. |
| Customer Portal       | Enterprise B2B    | The Dynamics 365 Supply Chain Management Customer portal is a template that provides portal access to Dynamics 365 Supply Chain Management data using dual-write Common Data Service entities. |

> [!IMPORTANT]
> Review current licensing guides to determine the licenses, subscriptions and capacity required for internal and external authenticated users as well as anonymous page views. Please refer to the [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/p/?LinkId=866544) or the 
[Power Apps Licensing Guide](https://go.microsoft.com/fwlink/?linkid=2085130).  Integration to other services such as SharePoint, Power BI or Azure Blob Storage will require appropriate capacity and licensing for these services.

You will need to define the type of audience who will visit the new portal. This will determine what options of portals you will be given.

## Portal features

All portal templates are built on a common foundation (portal base) and include the following features:

* Ability to configure the portal using the Portal studio
* Content management including content publishing, design, theming, search, multi-lingual support, templating.
* Extensibility built on Web Pages, Templates, Entity Forms, Entity Lists, and more. 
* Security based on identity management, integration with authentication providers, web roles, content permissions, entity permissions.
* Common features like Ads, Polls, Ratings, and Comments. These features are not standalone and can be used throughout other parts of the implementation. For example, ratings and comments can be enabled for a page, ads can be included as part of a template.  Some features will require Dynamics 365 apps to be enabled. For example, Knowledge Articles require a Dynamics 365 first-party app.

Where the portal templates are different is around the functional areas targeting *specific business processes* such as Case Management. These features are deployed as additional managed solutions making it easier to add missing ones if necessary.

| Feature                                | Portal from blank | Customer self-service | Partner | Employee self-service | Community |
| -------------------------------------- | :-----------: | :-------------------: | :------------: | :--------------------------: | :--------------: |
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

<sup>^</sup> Support for Azure AD as authentication provider is included in portal base. Azure AD Authentication feature, as used by Employee Self-Service Portal, is different. In Employee Self-Service Portal, the login process validates that the user has a required Dynamics 365 license and access is denied if the user does not have a Dynamics 365 license assigned.

If a particular feature, for example Case Management, is available in two different templates, it will be the **same** feature offering the **same** functionality.

## Additional Considerations

### Dependencies

Some portal templates have prerequisites for their installation, so an installation will fail if the prerequisites are not met. For example, to install the Partner Field Service for a partner portal, the Partner Portal and Field Service solutions must have already been installed. If you attempt to install the Partner Field Service first, the installation will fail and give you an error message.  If Dynamics 365 apps are not enabled, the only portal template available will be Portal from blank.

### Employee Portal Access 

When an employee accesses the portal functionality, appropriate Dynamics 365 or Power Apps license may be required. The easiest way to assess the licensing requirements is to keep in mind that the requirements do not change depending on method of access. They are the same regardless whether employee accesses Dynamics 365 using a portal or via one of the Dynamics 365 first-party Apps. 

For example, if an employee has a Dynamics 365 Customer Service license assigned, they cannot manage opportunities using Partner Portal as access to opportunities require Dynamics 365 Sales license.

License required depends on the entities and functionality accessed. See [Dynamics 365 Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=866544&clcid=0x409) or [Power Apps Licensing Guide](https://go.microsoft.com/fwlink/?LinkId=2085130&clcid=0x409)for more details.

### Third-party Solutions

Some third-party solutions add features to the portal that can greatly enhance user experience. Some of these capabilities may be agnostic to the choice of a template, for example: 

* Live Chat and Cobrowse
* Click to Call
* Customer Journey tracking

On the other hand, Power Platform and Dynamics 365 ISVs and System Integrators offering Power Platform and Dynamics 365 vertical solutions often may include portal extensions designed for their solution needs. When working with a vendor who offers portals as part of their overall solution, it would be sensible to discuss portal requirements and the portal template selection beforehand.
