# Getting started with Power Apps portals

Business with either Dynamics 365 or a custom Common Data Service solution already in place can quickly build a secure portal, and their entire website, with no developers required. 

A Power Apps portal is not automatically provisioned when a new Common Data Service environment is created. You will need to provision a Power Apps portal and determine the name, default URL (Universal Resource Locator), language and template.

Power Apps portals evolved from Dynamics 365 Portals.  Going forward, Dynamics 365 Portals are referred to as Power Apps portals.  The key difference is that there are a number of additional portal templates available for Dynamics 365-enabled environments.  

> [!IMPORTANT]
>
> To provision a portal, you must be assigned to the System Administrator role of the Common Data Service environment selected for the portal.

## Starter Templates

Starter templates are pre-configured portal solutions available to accelerate deployment.  Unlike model-driven and canvas apps, makers will start with a starter template to build and customize their portal apps. 

Power Apps portals are all customizable but a starter portal will provide a pre-configured environment immediately suitable for specific scenarios. Available templates are: 

* Portal from blank 
* Custom Portal (Dynamics 365 Apps)
* Community Portal (Dynamics 365 Apps)
* Customer Self-Service Portal (Dynamics 365 Apps)
* Employee Self-Service Portal (Dynamics 365 Apps)
* Partner Portal (Dynamics 365 Apps)
* Supply Chain Management Customer Portal (Dynamics 365 Apps)

Partner Portal also includes optional Field Service and Project Service addons that are available if your Dynamics 365 environment includes Dynamics 365 Field Service and Dynamics 365 Project Service solutions.

Each of the starter portals include particular set of features designed to *accelerate* solution development targeting the selected audience. 

## Portal Features 

Power Apps portals is a *platform* and includes a long list of components and features out of the box. Let's see how these features map into the key capability areas of Power Apps portals:

| Content                          | Extensibility          | Security                   | Functionality                              |
| -------------------------------- | ---------------------- | -------------------------- | ------------------------------------------ |
| Accessibility                    | Web Forms              | Profile Management         | Case Deflection                            |
| Bootstrap Design                 | Web Templating         | Web Roles                  | Case Management                            |
| Branding                         | Entity Forms           | Invitations                | Knowledge Management                       |
| Content Publishing               | Entity Lists           | Content Permissions        | Discussion Forums                          |
| Responsive Design                | Entity Actions         | Entity Permissions         | Ideas, Blogs                               |
| Web Pages                        | Automation    | Identity                   | Customer, Account & Opportunity Management |
| Faceted Search and SEO           | Charts & Graphs        | Authentication             | Delegated Administration                   |
| Multi Lingual Portals            | Azure Integration      | Auth Providers integration | Multi-Partner Collaboration                |
| Ads, Polls, Ratings and Comments | SharePoint Integration |                            | Entitlements & SLAs                        |
| Theming  | Power BI Integration   |                            | Localization into 43 Languages             |
| Web Files | Client side JavaScript |||
|| Liquid Templates |||
|| Web API |||

 

All components and features listed under **Content**, **Extensibility**, and **Security** form the portal *foundation*. The are part of the base solution and included in all starter portals. Features from the **Functionality** area focus on the specific needs of the target audience. Starter portal selection defines what subset of the functional features is are included.  

> [!NOTE]
>
> Do not feel threatened that the starter portal selection will potentially lock you into a specific set of features. Portal features are deployed into the target Dynamics 365 environment as managed solutions. Portal features can be added or removed later. 

## Provision a Portal

Only one Power Apps portal can be provisioned per Common Data Service environment.

The high-level steps to provision a starter portal are:

* Navigate to https://make.powerapps.com
* Select a target environment using the environment selector in the upper right corner
* On the left menu, click **+ Create**
* Select **Portal from blank**. If you have Dynamics 365 apps deployed in your Common Data Services environment, additional portal templates such as Customer Self-service will be available
* Provide the portal with a name
* Provide the portal with a unique address (URL)
* Select the language
* Click **Create** to start the portal provisioning process
* Once portal provisioning completes, the portal will appear in the list as the app of type Portal 
* Click on the ellipsis next to the portal app name then click Browse to open the portal website

> [!VIDEO "../media/provision-portal.mp4"]
>
> <video src="../media/provision-portal.mp4"></video>
>
> 

Step-by-step instructions to provision a portal are available in [Provision a portal](https://docs.microsoft.com/dynamics365/customer-engagement/portals/provision-portal).