The use case for your custom connector will determine how you want to manage the lifecycle as it evolves. These are the primary scenarios and a high-level overview of how they are handled.

-   **Single environment usage** - This is commonly used for productivity apps built and used in the same environment. In this scenario, you are not concerned with moving it between different environments or sharing it with other people outside your company. You still would have some concern for breaking changes and should follow some of the versioning update guidance. Using solutions will help your future transportability if you want to move it to other environments in the future. Typically for this scenario a formal ALM process is not implemented.

-   **Multiple environments usage** - This scenario covers usage when you want to install the connector privately in multiple environments and are not interested in open-sourcing or certifying the connector. The connector should be created and managed in the context a solution, which is the primary mechanism to copy custom connectors between the environments. Your connector will benefit from all the lifecycle management aspects of the solution framework. To track changes in the connector, you could use version control of the solution components.

-   **Open sourcing/certifying** - This scenario covers when you are open-sourcing or certifying your connector to make it available publicly for others to install or use. In this scenario, you will manage the individual files that make up the definition of the connector and use the Power Platform command-line tool for importing and exporting. Since publishing these connectors require the individual definition files and also requires more metadata to be captured, it is more common to source control the exported files and not a solution.

In this module, we will be diving deeper into how to manage these different scenarios using the tools and capabilities of the platform.

## What is ALM?

ALM is the lifecycle management of application components that make up a complete application, which includes governance, development, and maintenance. Moreover, it includes these disciplines: requirements management, architecture, development, testing, maintenance, change management, continuous integration, project management, deployment, and release management.

The application lifecycle is the cyclical development process that involves these areas: plan and track, develop, build, and test, deploy, operate, monitor, and learn from discovery.

> [!div class="mx-imgBorder"]
> [![Diagram of the cyclical development process of application lifecycle.](../media/diagram-application-lifecycle.png)](../media/diagram-application-lifecycle.png#lightbox)

When you open source and/or certify your custom connector, the deploy phase is more than just moving it to another environment. There is a specific set of procedures to follow you can read more on [Instructions on submitting your connector to Microsoft](https://docs.microsoft.com/connectors/custom-connectors/certification-submission/?azure-portal=true).

## Power Platform ALM

The Power Platform provides ALM tools to support a healthy lifecycle management process. These tools rely upon Microsoft Dataverse and solutions. Solutions are the mechanism for implementing ALM in Power Apps and Power Automate. Custom connectors can be created in and transported between environments using solutions.

A key aspect of Power Platform ALM is using environments for specific purposes during different phases of the lifecycle. For example, in a basic ALM setup you would have dev, test and production environments. Learn more about [developing an environment strategy](https://docs.microsoft.com/power-platform/alm/environment-strategy-alm/?azure-portal=true).

Another key aspect of ALM is applying source control to track changes made over each release of the custom connector or other components. Using the Power Platform build tools you can automate taking a snapshot of a solution containing your connector and version controlling it to track what changed with each revision.

You will learn more about using solutions and the build tools later in this module.

## Open sourcing/certifying ALM

When open-sourcing and/or certifying your custom connector, you are primarily working with a predefined ALM process involving the [Power Platform Connector GitHub repository](https://github.com/Microsoft/PowerPlatformConnectors/?azure-portal=true). While you could open source to any public location for example, your own public GitHub repository or download location, there are specific benefits like visibility and ease of import that makes the Power Platform Connector GitHub repository the recommended approach.

While it is possible to also use the Power Platform ALM approaches and tools in addition to the CLI and GitHub, it does not simplify or add significant value if your goal is open-sourcing and/or certification.