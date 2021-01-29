The Microsoft Cloud for Healthcare applications are currently only supported on North American (NAM) Microsoft 365 tenants. 

## The Power Platform

The Microsoft Power Platform provides a foundation for building applications, analyzing data, and automating processes. Robust business and industry applications can be quickly developed using low-code and professional code techniques. Many of Microsoft's flagship business solutions such as Dynamics 365 apps are built on the Power Platform.

Many of the Microsoft Cloud for Healthcare apps are built and extended from existing Power Platform and Microsoft Dynamics 365 solutions.

There are several benefits of providing healthcare applications built on the Power Platform. There is an increased pool of professional solution architects, functional consultants, and application developers that may not have a background in the healthcare industry but can apply their application skills to collaborate on implementing robust healthcare solutions.

The Power Platform can be easily extended, modified, and integrated. This allows for organizations to be able to implement unique application solutions to address specific requirements.

Along with the core capabilities provided with the various healthcare solutions, the Power Platform offers other services that can be utilized, such as custom Power Apps, Power Automate, Power BI, AI Builder, and Power Virtual Agents.

In order to configure the Microsoft Cloud for Healthcare, there are many prerequisite applications that need to be installed and configured before deploying the healthcare solutions. Deployment of the Microsoft Cloud for Healthcare is facilitated in the [Dynamics 365 Solutions Center.](https://admin.solutions.dynamics.com/?azure-portal=true)

## Subscription requirements

Depending on what specific applications and features will be implemented, to install the Microsoft Cloud for Healthcare, the tenant will need a combination of either trial or full subscriptions of the following products:

-   Power Apps per user plan (Care Management only)

-   Dynamics 365 Customer Service Enterprise (Patient Service Center, Patient Access)

-   Dynamics 365 Field Service (Home Health)

-   Dynamics 365 Customer Service Digital Messaging Add-On (Patient Service Center)

-   Dynamics 365 Marketing (Patient Outreach)

-   Power Apps Portals login capacity add-on (Patient Access)

-   Power Apps Portals page view capacity add-on (Patient Access)

-   Dynamics 365 Customer Engagement Plan Trial (30-day trial for Dynamics 365 Customer Service Enterprise and Dynamics 365 Field Service)

-   Microsoft Cloud for Healthcare AddOn (all solutions)

During the deployment, the Dynamics 365 Solution Center will verify the tenant has the appropriate licenses. As the requirements may evolve over time, it is advisable to review the Dynamics 365 Licensing Guide. The guide provides up-to-date information on pricing and licensing requirements for Dynamics 365 applications. Also review the [How to buy the Microsoft Cloud for Healthcare](https://docs.microsoft.com/industry/healthcare/buy/?azure-portal=true) for up-to-date steps on pricing information and how to acquire the Microsoft Cloud for Healthcare AddOn.

## Dataverse environment

A Dataverse environment will need to be provisioned with a database. It is not supported to use the default Power Platform environment. Multiple environments for production, development, and testing need to be considered for healthy application lifecycle management (ALM).

The Home Health, Patient Service Center, Patient Outreach and Patient Access will also require a Dataverse environment with Dynamics 365 apps enabled.

> [!NOTE]
> Dynamics 365 apps such as Customer Service must be enabled when the environment database is created, it cannot be added later.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Platform Admin center deploying a new environment and ensuring that the Dynamics 365 apps are enabled.](../media/enable-apps.png)](../media/enable-apps.png#lightbox)

## Microsoft Cloud for Healthcare applications prerequisites

### Care management

The Care Management solution does not require any dependencies on any existing Dynamics 365 first-party applications. It can be installed and configured on a vanilla Dataverse environment with a database installed. The Care Management solution will be installed with a model-driven Power App and uses the existing Dataverse functionality to integrate with Microsoft 365.

### Patient service center

The Patient Service Center requires the [Dynamics 365 Customer Service](https://docs.microsoft.com/dynamics365/customer-service/?azure-portal=true) app and the [Digital Messaging add-on for Dynamics 365 Customer Service](https://docs.microsoft.com/dynamics365/customer-service/introduction-omnichannel/?azure-portal=true) (also known as Omnichannel for Customer Service).

Dynamics 365 Customer Service provides case management capabilities to track the lifecycle and communication associated with a particular incident related to a customer. Cases can also be routed or managed via queues and a searchable library of knowledge base articles can be reviewed and attached to specific cases.

These features support a healthcare environment by tracking various patient healthcare cases and tracking the communications and interactions between healthcare workers and patients.

The Microsoft Cloud for Health deployment process will configure Dynamics 365 Customer Service for the Patient Service Center app.

The Digital Messaging add-on for Dynamics 365 component enables healthcare agents to interact using various different communication methods with patients. The Patient Service Center can be linked to the Microsoft Health Bot and the Patient Access portal to help automate and facilitate these conversations.

The Digital Messaging add-on will need to be provisioned and have the various channels enabled to be able to deploy the Microsoft Cloud for Healthcare.

See [Provision Omnichannel for Customer Service](https://docs.microsoft.com/dynamics365/customer-service/omnichannel-provision-license/?azure-portal=true) for information on provisioning.

> [!div class="mx-imgBorder"]
> [![Screenshot of Dynamics 365 Administrator Center showing the setup of Omnichannel channels.](../media/provisions.png)](../media/provisions.png#lightbox)

### Patient outreach

The Patient Outreach application requires [Dynamics 365 Marketing](https://docs.microsoft.com/dynamics365/marketing/help-hub/?azure-portal=true).

Dynamics 365 Marketing app allows users to create targeted communication campaigns and customer journeys, manage events and manage subscription lists.

The Patient Outreach app extends these concepts into allowing healthcare professionals to utilize prebuilt patient segments based on Healthcare Effectiveness Data and Information Set (HEDIS) to manage lists of their patients and create healthcare-specific outreach and communication campaigns.

The Microsoft Cloud for Healthcare deployment process will configure Dynamics 365 Marketing for the Patient Outreach application.

### Patient access

The Patient Access application utilizes [Power Apps portals](https://docs.microsoft.com/powerapps/maker/portals/overview/?azure-portal=true), specifically an enhancement of the Customer self-service portal. The Customer self-service portal allows for external stakeholders to interact with the Dynamics 365 Customer Service app.

The Patient Access portal allows patients to log in, request appointments and send and receive confidential communications with their healthcare professionals.

Prior to deployment of the Microsoft Cloud for Healthcare Patient Access solution, a Power Apps portal will need to be provisioned on the Dataverse environment. Ideally, the environment should not have any other portals deployed as the process could overwrite existing portal configurations.

See [Create a portal with Dynamics 365 environment](https://docs.microsoft.com/powerapps/maker/portals/create-dynamics-portal/?azure-portal=true) for information on provisioning the Customer self-service portal.

> [!div class="mx-imgBorder"]
> [![Power Apps maker portal showing screen to deploy the Customer self-service portal on the Dataverse environment.](../media/customer-self-service.png)](../media/customer-self-service.png#lightbox)

### Home Health

The Home Health application utilizes [Dynamics 365 Field Service](https://docs.microsoft.com/dynamics365/field-service/overview/?azure-portal=true). The Dynamics 365 Field Service application is designed to manage onsite service to customer locations. The Home Health application extends this concept to allow health coordinators to effectively schedule care team member home visit appointments, optimize routes and coordinate tasks and processes during the visit. If Dynamics 365 Field Service was not added when the initial Dataverse database was created, it will need to be installed prior to deployment of the Home Health app.

See [How to install Dynamics 365 Field Service](https://docs.microsoft.com/dynamics365/field-service/install-field-service/?azure-portal=true) for information on installing the Dynamics 365 Field Service app.

The Microsoft Cloud for Health deployment process will configure Dynamics 365 Field Service for the Home Health app.

### Virtual visits (Teams)

Virtual Visits is an extension to Microsoft Teams. The deployment process is separate from the Dynamics 365 apps. Virtual visits (Microsoft Teams meetings) can be launched from the Patient Access portal.

The Virtual Visits installation process will allow installers to link to the Epic Electronic Medical Record (EMR) system so that healthcare providers can view and update a patient's medical information during the virtual visit.

## Deployment of Microsoft Cloud for Healthcare

To deploy the Microsoft Cloud for Healthcare apps, the user performing the installation must be assigned a license.

> [!div class="mx-imgBorder"]
> [![Screenshot of Microsoft 365 showing a user being assigned a license the Microsoft Cloud for Healthcare add-on.](../media/assign-license.png)](../media/assign-license.png#lightbox)

With the prerequisites installed and the user licensed, the Microsoft Cloud for Healthcare solutions powered by Dynamics 365 can be deployed.

See [Deploy Microsoft Cloud for Healthcare solutions powered by Dynamics 365](https://docs.microsoft.com/dynamics365/industry/healthcare/deploy/?azure-portal=true) for steps to deploy the solutions.

Most of the provider solutions can be deployed in one process or individually, depending on the requirements.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the Solutions Center with the various MCH solutions available for deployment.](../media/provider-solutions.png)](../media/provider-solutions.png#lightbox)

The process will also verify any prerequisites or configurations required to deploy the Microsoft Cloud for Healthcare solutions. Once all the requirements are met, the deployment process can continue. The deployment process will also allow for the installation of sample data for testing and training purposes.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Solutions center showing the various Dynamics 365 apps and if the installation and configuration requirements have been met.](../media/install-sample-data.png)](../media/install-sample-data.png#lightbox)

The deployment may take several hours. When the process is complete or encounters issues, an email will be sent to the installation user.

The various Microsoft Cloud for Healthcare Dynamics 365 apps will then be available.

> [!div class="mx-imgBorder"]
> [![Screenshot showing the listing of Dynamics 365 published apps including the various Microsoft Cloud for Healthcare apps.](../media/apps-available.png)](../media/apps-available.png#lightbox)

> [!VIDEO https://www.microsoft.com/videoplayer/embed/]

