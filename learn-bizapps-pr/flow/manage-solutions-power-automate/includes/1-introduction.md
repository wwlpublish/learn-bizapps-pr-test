Solutions allow you to package features such as apps from Microsoft Power Apps (canvas and model-driven), site maps, flows, entities, forms, custom connectors, web resources, option sets, charts, and fields, to transport from one environment to another. Only the metadata, such as entities and their columns and configuration data, are transported. No business data is transported.

Solutions are part of the overall application lifecycle management (ALM) practice of Microsoft Power Platform. Solutions are important mechanisms for implementing ALM. For more information, see [Overview of application lifecycle management with Microsoft Power Platform](https://docs.microsoft.com/power-platform/alm/overview-alm/?azure-portal=true).

### Power Automate flows

Microsoft Power Automate (previously known as Flow) is a service that allows you to create workflows that are either automated or manually triggered by a user. Several templates are already available that either fully match your requirement or require minor changes. Other options include creation from a Microsoft Visio template, UI, or business process flows.

The designer feature that's included with Power Automate is user-friendly. However, drawing your flow logic on a Visio diagram can occasionally help you design a better workflow; hence the integration of Power Automate with Visio. In Visio, you can use the Business Process Modeling Notation (BPMN) basic shapes to design the flow and export it. You can then import that file into Power Automate, after which you have the flexibility to make further enhancements.

UI flows bring Robotic Process Automation (RPA) directly into Power Automate. This functionality comes with either a desktop or a web app that you use to record the user interface, including selections and keyboard input. This feature is useful for when you are working with legacy applications that don't have available APIs.

Business process flows are built by using Power Platform and Common Data Service. You can also use Power Automate workflows. The business process is a series of steps that the user needs to complete in a specific stage. The business process flow will visually guide the user through various stages. These flows are created and managed by using Power Automate, and several templates are readily available. These templates can use the entities that are already available, or you can use custom entities that you have created.

Power Automate flows that you create in a solution are known as solution-aware flows. You can build a new flow directly inside a solution. In addition, you can edit and delete that flow.

### Connection references

A connector is a user-friendly way to allow a service to connect with Power Automate. Each connector comes with a set of operations that are classified as **Actions** and **Triggers**. After you have connected to the service, these operations can be used within your Power Automate workflow.

The three separate categories of connectors are: Standard, Premium, and Preview. Custom connectors and connectors for Microsoft Azure Logic Apps fall under the Premium category.

You can add connectors to a solution. Additionally, you have the option to add existing connectors to a solution or create a new one that automatically becomes part of that solution.

### Environment variables

Previously, it was a common practice for all stored data to be available in a single environment only. Now, because of environment variables, you have the flexibility to transport your configuration data from one environment to another within the same tenant. After creating environment variables in Common Data Service for apps, you can consume them by retrieving data from the **Environment Variable Definition** and **Environment Variable Value** entities.

You can add environment variables in a solution. Additionally, you have the option to add an existing environment variable in a solution or create a new one that automatically becomes part of that solution.

## Managed and unmanaged solutions 

Solutions are mechanisms for implementing ALM in Power Apps and Power Automate. A solution can be managed or unmanaged.

Unmanaged solutions are used while you are still in your development environment in the initial design, building, and testing phase. Unmanaged solutions should be considered your source for Microsoft Power Platform assets. When an unmanaged solution is deleted, only the solution container of any customizations that are included in it is deleted. All unmanaged customizations will remain in effect and belong to the default solution.

Managed solutions are used to deploy to any environment that isn't a development environment for that solution. This factor includes test, User Acceptance Testing (UAT), System Integration Testing (SIT), and production environments. To help make the process easier and faster, managed solutions can be created independently from other managed solutions in the same environment. As an ALM best practice, managed solutions should be generated by exporting an unmanaged solution because a managed solution is considered a build artifact.

Changes can only be made to unmanaged solutions. If you need to modify a managed solution, you need to add them to an unmanaged solution. When you do so, you will create a dependency between your unmanaged customizations and the managed solution. When a dependency exists, the managed solution can't be uninstalled until you remove the dependency.

Some managed components can't be edited. To verify whether a component can be edited or not, view the **Managed** properties.

You can't export a managed solution. Also, when a managed solution is deleted (uninstalled), all customizations and extensions that are included with it are removed.

## Create a new solution(s)

The following scenario considers a Common Data Service entity, called Volunteer Requests, that saves all requests that are submitted. A Power Automate flow is created to send an email notification to team members of certain departments.

1. In Power Automate, select **Solutions** and then **+ New solution**.

	> [!div class="mx-imgBorder"]
	> [![Select Solutions and + New solution](../media/click-flow-solution-ssm.png)](../media/click-flow-solution-ssm.png#lightbox)

1. Add the **Display name**, select **CDS Default Publisher**, and then add a **Description**. Select **Create**.

	> [!div class="mx-imgBorder"]
	> [![select Create](../media/save-solution-information-ss.png)](../media/save-solution-information-ss.png#lightbox)

Congratulations, you have created your new solution.

> [!div class="mx-imgBorder"]
> [![your new solution](../media/new-solution-created-ssm.png)](../media/new-solution-created-ssm.png#lightbox)

## View an existing solution(s) 

You can view your solutions from Power Apps or Power Automate. 

1. Sign in to either Power Apps or Power Automate to find the **Solutions** option, which is available in the lower-left corner of the vertical navigation pane.

	> [!div class="mx-imgBorder"]
	> [![View solution from Power Apps or Power Automate](../media/view-solution-ssm.png)](../media/view-solution-ssm.png#lightbox)

1. Select **Solutions**, where you'll see the list of solutions that you've previously built, including the new one called **Volunteer Request**.

	> [!div class="mx-imgBorder"]
	> [![the list of solutions you previously built](../media/view-existing-solutions-ssm.png)](../media/view-existing-solutions-ssm.png#lightbox)
