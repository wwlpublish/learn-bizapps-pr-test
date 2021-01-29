The Microsoft Cloud for Healthcare applications are currently only supported on the North American (NAM) Microsoft 365 tenants. [Other geographies will be supported in the future.]{.underline}

## Microsoft Azure

Microsoft Azure is a cloud-based platform that is the foundation for applications, databases, and services. Microsoft services such as Microsoft 365, Power Platform and other services run on Microsoft Azure. IT professionals can create and provision their own solutions using Microsoft Azure.

The Azure API for FHIR (fast healthcare interoperability resources) and Azure Health Bot are features of Microsoft Cloud for Healthcare that are powered by Microsoft Azure.

The main benefits are that the healthcare features can be easily deployed without the requirement of hardware resources or platform configuration. The foundational capacity can be increased or decreased depending on the needs of the organization.

## Subscription requirements

Many Microsoft Azure services are licensed on a consumption model, meaning the costs are determined by computing resources that have been used during a particular billing cycle. There is no fixed per month cost for The Azure API for FHIR. The Azure API for FHIR can be provisioned on an Azure portal and the monthly costs can be calculated based on projected usage using the [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/?azure-portal=true).

The Azure Health Bot is offered as a free or standard plan. The free plan is only recommended for testing and experimenting with the Azure Health Bot. The standard plan is a fixed monthly fee with a set package of messages and content consumption with additional fees for messages and content required beyond the fixed monthly fee. See [Choosing the right Health Bot plan](https://docs.microsoft.com/healthbot/resources/pricing-details/?azure-portal=true) for details.

## Microsoft Cloud for Healthcare Azure deployment

### Azure API for FHIR

The Azure API for FHIR allows organizations to take data from various medical systems and centralize them in cloud-based systems. The information can then be accessed and updated from Microsoft Cloud for Healthcare applications as well as enabling various AI and analytics features.

The Azure API for FHIR can be deployed by adding a new resource to an existing Azure deployment. The deployment process will provision all the services and APIs to be integrated and accessed from the different electronic medical record systems.

See [Quickstart: Deploy Azure API for FHIR using Azure portal](https://docs.microsoft.com/azure/healthcare-apis/fhir-paas-portal-quickstart/?azure-portal=true) for instructions to provision Azure API for FHIR.

> [!div class="mx-imgBorder"]
> [![Screenshot of Azure API for FHIR deployment screen in Azure.](../media/azure-api-fhir.png)](../media/azure-api-fhir.png#lightbox)

### Azure health bot

The Azure Health Bot Service provides an AI-powered virtual assistant for use with various medical solutions including the Microsoft Cloud for Healthcare. Specifically, an Azure Health Bot can be surfaced on a Patient Access portal and transcriptions of the interaction between patient and bot can be added to a case record in the Patient Service Center.

> [!div class="mx-imgBorder"]
> [![Screenshot of Azure Health Bot setup screen in the Azure portal.](../media/azure-health-bot.png)](../media/azure-health-bot.png#lightbox)

The Azure Health Bot can be deployed by adding a new resource to an existing Azure subscription. The provisioning process will prompt for the choice of subscription plan (free or standard) and deploy the required assets.

See [Create your first Health Bot](https://docs.microsoft.com/healthbot/quickstart-createyourhealthcarebot/?azure-portal=true) for instructions to provision the Azure Health Bot.

When the Azure Health Bot has been deployed, it can be further configured on the Azure Health Bot portal and conversations can be initiated with the bot.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Azure Health Bot portal with the Web Chat screen enabled for a user.](../media/web-chat.png)](../media/web-chat.png#lightbox)

