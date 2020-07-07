Obtain a [trial environment](https://powervirtualagents.microsoft.com/?azure-portal=true) to assist you in completing training, evaluating the product, and other areas. Select Try free to begin to deploy a Power Virtual Agent trial.

> [!NOTE]
> You will need to sign in with a work email address as personal Microsoft accounts are not currently supported.

## Understanding how environments impact PVA bots

Many organizations today have a global presence and service customers in multiple regions, countries, or continents. This can result in needing different types of interactions based on factors such as different data being available and resolutions based on departments or locations. Your organization may need to deploy similar bots in different regions that interact with systems and data for those areas. Power Virtual Agents accommodates this by letting you create bots in different environments and easily switch between them.

Environments represent space to store, manage, and share your organization\'s business data. Each bot you create is stored in an environment. Items like model-driven and canvas applications, as well as Power Automate Flows are also stored in environments. Each environment may have different roles, security requirements and target audiences. Individual environments are not created in PVA. They are created in a separate location. Once created, PVA bots can be created in that environment.

Depending on business needs, organizations can leverage environments in many ways, including:

-   **Departmental:** By creating an environment that corresponds with specific organizational teams or departments, created bots will contain relevant information for that audience.

-   **Locational:** Since the data displayed may be different based on geographic regions, you might define separate environments for different global branches of your company.

You only need multiple environments if your company is global and you are supporting regions with specific data privacy and storage requirements like China, Germany, the EU, Singapore, etc. In that case, you will need to establish environments for each region as you would for any other service that uses and stores data for customers in that region.

## Creating environments

The first time you sign into Power Virtual Agents and create a new bot, a default environment is created. Unless specified otherwise, any additional bots will be created in the default environment. If additional environments are needed, such as for different regions, organizational needs, or other circumstances, they can be added through the [Power Platform Admin Center](https://docs.microsoft.com/power-platform/admin/create-environment/?azure-portal=true).

Once in the admin center, environments are added by navigating to the Environments tab and selecting New to open the new environment panel.

For each environment, you will need to provide the following:

-   **Name**: A unique name for the environment.

-   **Environment:** Defines the type of environment to create such as a production, trial, or sandbox.

-   **Region:** Defines the [support data region](https://docs.microsoft.com/power-virtual-agents/data-location/?azure-portal=true) where the environment will be created.

> [!div class="mx-imgBorder"]
> [![name, environment and region for environment](../media/pva-2-1-ssm.png)](../media/pva-2-1-ssm.png#lightbox)

If you want to have a Common Data Service (CDS) database created for the environment to leverage entities like Accounts, Contacts, and other business-related data, you can set the Create a database for this environment field to Yes. **You should also select yes, if you are using Power Virtual Agents in conjunction with other Dynamics 365 applications.** Data from CDS can be used in bots to provide tailored customer experience. Once created, new bots can be deployed to the environment from the Power Virtual Agents Portal.

More information on [creating environments](https://docs.microsoft.com/power-virtual-agents/environments-first-run-experience#create-a-new-environment-for-your-bots/?azure-portal=true). 
