Solutions allow you to package features, such as apps in Microsoft Power Apps (canvas and model-driven), site maps, flows, entities, forms, custom connectors, web resources, choices, charts, and fields, to transport from one environment to another. Only the metadata, such as entities and their columns and configuration data, are transported. No business data is transported.

Solutions are part of the overall application lifecycle management (ALM) practice of Microsoft Power Platform. Solutions are important mechanisms for implementing ALM. For more information, see [Solutions for implementing ALM](https://docs.microsoft.com/power-platform/alm/overview-alm/?azure-portal=true).

## Learn the basics: Power Apps, Power Automate flows, connection references, and environment variables

### Power Apps

Power Apps is a no-code/low-code platform for building apps that builds from concepts that are similar to formulas in a Microsoft Excel workbook like SUM and TEXT. You can use Power Apps to build simple solutions like vehicle inspection forms and status reports or complex business solutions for purchasing processes and inventory management. If you can envision an app to solve a business problem, then you can use your existing skills to build it. Though Power Apps is geared toward business users who have little background in computer science and coding, Power Apps offers advanced functionality and the ability for seasoned developers to design complex applications with ease.

Power Apps can create three types of apps: canvas, model-driven, and portals. Each is suited to different scenarios and users.

Canvas apps are great options when you want to build an app from a blank canvas. You can start by choosing the screen size (tablet or mobile), and then you will have a blank screen from which to build. You can interact with data in your app by adding data sources. Drag and drop various controls and add the desired functionality by writing Excel style formulas. Canvas apps provide you with complete flexibility when you are building apps.

Model-driven apps build from data in Microsoft Dataverse. Power Apps will build you an attractive, fully functional app to add, edit, and view data. With model-driven apps, you don't have to choose the app size; it's responsive, meaning that it works on mobile or tablet with no extra work needed by you. You can define the relationships, forms, views, business rules, and more at the data layer, in Dataverse, giving you enough control to get your business result without writing all formulas yourself.

Portals bring the power of no-code solutions to building externally facing websites. Through the Power Apps interface, you can build an anonymous or authenticated website that allows users to interact with data that is held in Dataverse. The same drag-and-drop experience that you enjoy when building apps is available for you to build these rich, interactive websites.

### Power Automate flows

Microsoft Power Automate (previously known as Flow) is a service that allows you to create workflows that are either automated or manually triggered by a user. Several templates are available that can fully match your requirements or require minor changes. Other options include creation from a Microsoft Visio template, UI, and business process flows.

The designer feature that comes with Power Automate is user-friendly. Occasionally, drawing your flow logic on a Visio diagram can help design a better workflow; thus, the integration of Power Automate with Visio. In Visio, you can use BPMN Basic Shapes to design the flow and export it. Then, you can import that file into Power Automate, after which you have the flexibility to make further enhancements.

UI flows bring robotic process automation (RPA) directly into Power Automate. This functionality comes with either a desktop or a web app that you can use to record the UI, including clicks and keyboard input. This feature is handy when you're working with legacy applications that don't have available APIs.

Business process flows are built by using Microsoft Power Platform and Dataverse. You can also use Power Automate workflows. The business process is a series of steps that the user needs to complete in a specific stage. The business process flow visually guides the user through various stages. These flows are created and managed by using Power Automate, and several templates are readily available. These templates can use the entities that are already available, or you can use custom entities that you've created.

Power Automate flows that you create in a solution are known as solution-aware flows. You can build a new flow directly inside a solution, and you can also edit and delete that flow.  

### Connection references

A connector is a user-friendly way to allow a service to connect with Power Automate. Each connector comes with a set of operations that are classified as **actions** and **triggers**. After you have connected to the service, these operations can be used within your Power Automate workflow.

Three separate categories of connectors are: Standard, Premium, and Preview. Custom connectors and connectors for Microsoft Azure Logic Apps fall under the Premium category.

You can add connectors to a solution, and you can add existing connectors to a solution or create new ones that automatically become part of that solution.

### Environment variables

Previously, it was a common practice for all stored data to be available in a single environment only. Now, thanks to environment variables, you have the flexibility to transport your configuration data from one environment to another within the same tenant. After creating environment variables in Dataverse for apps, you can consume them by retrieving data from the **Environment Variable Definition** and **Environment Variable Value** entities.

You can add environment variables in a solution, and you can add an existing environment variable in a solution or create a new one that automatically becomes part of that solution.

## Managed and unmanaged solutions

Solutions are mechanisms for implementing ALM in Power Apps and Power Automate. A solution can be managed or unmanaged.

Unmanaged solutions are used while you're still in your development environment in the initial design, build, and test phases. Unmanaged solutions should be considered your source for Microsoft Power Platform assets. When an unmanaged solution is deleted, only the solution container of any included customizations is deleted. All unmanaged customizations will remain in effect and belong to the default solution.

Managed solutions are used to deploy to any environment that isn't a development environment for that solution. These environments include test, user acceptance testing (UAT), system integration testing (SIT), and production. To make it easier and faster, managed solutions can be created independently from other managed solutions in the same environment. As an ALM best practice, managed solutions should be generated by exporting an unmanaged solution as managed and then considered a build artifact.

Changes can only be made to unmanaged solutions. If you need to modify a managed solution, you need to add them to an unmanaged solution. As a result, you will create a dependency between your unmanaged customizations and the managed solution. When a dependency exists, the managed solution can't be uninstalled until you remove the dependency.
Some managed components can't be edited. To verify whether a component can be edited, view the **Managed** properties.

You can't export a managed solution. Also, when a managed solution is deleted (uninstalled), all included customizations and extensions are removed.
