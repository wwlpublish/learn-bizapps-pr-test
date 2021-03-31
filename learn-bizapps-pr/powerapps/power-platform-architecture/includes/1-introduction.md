A Power Platform Solution Architect Solution Architect is responsible for the overall design of the solution. Understanding the architecture of the Power Platform, how it is designed, and its limits are very important when designing solutions based around the Power Platform.

As you consider your solution's design, you need to understand the components and capabilities of the Power Platform and how these control the design of your solution.

## Power Platform Components

The Power Platform is Microsoft’s low-code, rapid business application development platform. The Power Platform contains several different independent, yet closely related tools:

- Power Apps: Allows anyone to build custom web and mobile apps using low-code or no-code techniques.

- Power Automate: A cloud workflow tool to connect cloud and desktop applications together to automate business processes.

- Power BI: A self-service analytics service that allows users to gain insights into their data. Power BI allows data to be merged from various sources and to create models, visualizations, reports, and dashboards.

- Power Virtual Agents: Allows anyone to create chatbots without writing code from within a browser interface.

![Low code tools.](../media/1-components.png)

The Power Platform includes a number of other components that support the Power Platform tools that the solution architect can leverage:

- Microsoft Dataverse (formerly known as the Common Data Service): Provides a no-code environment to create tables, relationships, and business logic.

- Data Connectors: Connectors define the services and data sources that the Power Platform tools can access.

- AI Builder: A set of AI model types that can use data in Dataverse to create, tailor, and train AI models that can be used by the other components of the Power Platform.

The diagram below illustrates how the components of the Power Platform are related.

![Screenshot of Power Platform.](../media/1-power-platform.png)

> [!NOTE]
> This module describes the architecture of the Power Platform. There are other modules that examine the details for Power Apps, Power Automate, Power BI, and Power Virtual Agents.

## Cloud

Power Platform is a cloud based Software-as-a-Service (SaaS) service that is available from within an Azure Active Directory tenant. The Power Platform is licensed through Microsoft 365 and secured by Azure Active Directory. The Power Platform runs on Microsoft Azure and therefore is highly scalable and is available globally.

## Capabilities of Power Platform

Typically solutions that a solution architect designs will make use of many of the components provided by the Power Platform. The individual components provide great capabilities on their own but are more powerful when combined.

Power Apps allows users to act on data and drive business processes. Power Automate can automate apps and act on behalf of the user in response to metrics and events. Power BI can analyze the data captured by apps. Power Virtual Agents can assist users. Power Automate flows can be called from Power Apps, Power Virtual Agent actions, and Power BI alerts. Power BI dashboards and tiles can be displayed in Power App screens. Power Apps can be embedded in Power BI dashboards.

![Low code tools.](../media/1-low-code-tools.png)

## What do we mean by the platform

When most people refer to the Power Platform, they are thinking of the four components, Power Apps, Power Automate, Power BI, and Power Virtual Agents. These tools allow you to build apps and create solutions.

Data is at the center of everything a business does today. With the Power Platform, we can either connect to data where it lives using Connectors, or store data in Microsoft Dataverse. There are connectors for Office 365 services, such as email and SharePoint, Azure services, such as Azure SQL, as well as many non-Microsoft sources such as Twitter, SendGrid, Dropbox, and Mailchimp. Power Apps and Power Automate use the Connectors to access the data where it lives. Microsoft Dataverse is more than a database, it a platform for building business apps and solutions.

Microsoft Dataverse controls security, implements logic, enables integrations, and has a wealth of capabilities that enable powerful business solutions to be created. These capabilities will be explored further in this module.

Before we can look at Dataverse, we first need to describe how Dataverse is accessed through environments.
