Data is at the center of everything a business does today and powers the insights that can drive what it should do tomorrow. To thrive and grow, businesses need to capture, analyze, predict, present, and report data and do it all with a high level of agility.

With the Power Platform, you can either:

- Access data from the platform using Connectors.
- Store data in the platform using Microsoft Dataverse.

## APIs

The Power Platform uses REST APIs to communicate between apps and data, and to perform management activities. REST APIs are built on open standards. You can compose HTTP requests for specific operations or use third-party libraries to generate classes for whatever language or platform you want.

Connectors and Dataverse both use REST API and OData to for requests and data.

## Dataverse vs Connectors

Connectors allow you to take advantage of the Power Platform without moving your data. Power BI, Power Apps, and Power Automate all use connectors allowing you to analyze, act, and automate across data and services.

With connectors:

- Can use existing data sources and services.
- Connect to more than 400 systems and services out of the box.
- Access data stored on-premises systems with the data gateway.
- Create custom connectors for internal and third-party services.

> [!IMPORTANT]
> Not all the public connectors support all the actions the underlying service supports, solution architects should investigate that the actions they require are supported otherwise a custom connector is required.

Connectors allow you to build your apps without having to migrate the data, which can be time consuming or costly.

Microsoft Dataverse should be your data source of choice for new data stores, or where you want to make use of Dataverse capabilities that will be described below or you want to use features of the Power Platform such as AI Builder or Portal Apps.

## Custom Connectors

Where there isn't a connector but the service has a REST API, a custom connector can be created. Creating a custom connector is straight forward with several different methods for defining the custom connector, including:

- Import the Open API definition to describe an existing API.
- Use Postman collection to describe an existing API.
- Create an Azure Functions and use Azure API Management (APIM).
- Create a custom API to define your own actions.

> [!NOTE]
> Many third party services publish an Open API definition for their full API.

Custom Connectors supports OAuth, (including Azure AD), API Key, and basic auth.

Custom Connectors can be packaged and deployed with solutions.

Actions can make it easy for makers to invoke complex custom logic. Consider the processing to register a student for a class. The processing steps are:

1. Check if student exists
1. Create student if not exist
1. Lookup class by course code
1. Check if class over capacity
1. Check if student has class pre-requisites
1. Create class student record
1. Notify user of results

You could create a custom connector for the Learning service with an action called "Register Student for Class" that performs these steps as shown in the following image.

![Diagram showing a custom connector in Power Platform.](../media/4-custom-connector.png)

Makers without the custom connector would need to know the details of the service, by using a custom connector with an action this promotes good architectural design; loose coupling via a contract where the calling system does not need to know the details since they could change.

## Virtual tables

There is one further option for accessing data. Consider the requirement to access data from an external data source and combine it with data in Dataverse. Virtual tables allow you to create a virtual table in Dataverse, define an external data source, and map the table and columns onto the external data source.

There is an OData v4 Data Provider included with Dataverse that allows you to connect to an external OData v4 web service. There is a data provider for the SQL API of Azure Cosmos DB in preview.

> [!NOTE]
> Dataverse requires that all tables have an ID attribute, this ID is known as a unique identifier and the value must be a guid. You can only map ID columns to external columns with the Edm.Guid data type. Hence the external web service must use a guid as its ID column.

Currently, virtual tables only permit read operations.

## Dataverse capabilities

Dataverse is more than just a database. Dataverse includes many features that make building business solutions easier and provide enhanced functionality.

The diagram below illustrates the capabilities provided by Microsoft Dataverse.

![Diagram of Microsoft Dataverse capabilities.](../media/4-dataverse.png)

The solution architect needs to understand the capabilities of Microsoft Dataverse and how these can be applied when creating solutions.

Because Dataverse is built on Azure, it benefits from the Azure platform's powerful security technologies. Encryption of data, at rest and in transit, preserves confidentiality.

Dataverse uses Azure AD identity and access management mechanisms to help ensure that only authorized users can access the environment, data, and reports. Dataverse uses role-based security to group together a collection of privileges. These security roles can be associated directly with users, or they can be associated with Dataverse teams and business units. In Dataverse, individual rows can be shared on a one-by-one basis with another user. Because row-level control of access isn't adequate for some business scenarios, Dataverse has a column-level security feature to allow more granular control of security at the column level. Dataverse also includes security models that can be used for hierarchies: the manager hierarchy and the position hierarchy. The security mode that Dataverse provides is highly configurable.

There are several choices available for applying custom business logic in Dataverse including Business rules, Classic workflows, and Power Automate. Calculated columns and Rollup columns reduce the need for processing and custom code. Dataverse has built-in functionality for duplicate detection and to delete stale data.

All components created in Dataverse are held as Metadata. This means the components are discoverable and the properties for components are accessible to applications and tools. This metadata is used by Power Apps and Power Automate reducing the effort required to create apps and flows. For instance, the data type of a column and its range of possible values are held in metadata. For example, the Power Apps studio is able to access this metadata and automatically configure the control when a column is added to a form.

The data held in Dataverse is abstracted from the underlying data storage mechanism. The data could be stored in Azure SQL Elastic pools, Azure Storage, Cosmos DB, or Azure Data Lake. The maker does not have to concern themselves with the storage and access the data through the APIs provided by Dataverse. Microsoft decides how to store data different ways depending on type for files, images, and text.

Dataverse provides an event model for integrating with other systems, and there are both import and export data processing capabilities.

Dataverse utilizes Azure Search to enable data held in Dataverse to be searched.

Dataverse is not restricted to apps built with the Power Platform, the APIs allow applications to be built with other tools such as Xamarin to build an external customer facing application.

## Why choose Microsoft Dataverse

Building out the data infrastructure to enable business insight can be both time consuming and expensive. The data originates from a variety of devices, applications, systems, services, and software as a service (SaaS). This large and growing number of sources often consists of multiple data technologies that store different types of data, expose different APIs, and use a mixture of security models. The developers needed to create these technologies can be expensive and hard to find. Developers often must have a deep understanding of how to deploy, configure, manage, and integrate these different data technologies.

Dataverse addresses these concerns with an easy to use, easy to manage, compliant, secure, scalable, and globally available SaaS data service. Dataverse empowers organizations to work with any type of data and any type of app, and use the data within it to gain insights and drive business action.

As part of Microsoft Power Platform, Dataverse requires no or little code to be written, so it can easily be used by everyone from knowledge workers to professional developers.

Standard and custom tables within Dataverse provide a secure and cloud-based storage option for your data. Tables let you create a business-focused definition of your organization's data for use within apps.

If you are not sure whether Dataverse is your best option, consider these benefits:

- Easy to manage: Both the metadata and data are stored in the cloud. You don't need to worry about the details of how they're stored.
- Easy to secure: Data is securely stored so that users can see it only if you grant them access. Role-based security allows you to control access to tables for different users within your organization.
- Access your data: – Data from your Power Platform applications is also stored within Dataverse, allowing you to quickly build apps that use your data.
- Rich metadata: Data types and relationships are used directly within Power Apps.
- Logic and validation: Define calculated columns, business rules, workflows, and business process flows to ensure data quality and drive business processes.
- Productivity tools: Tables are available within the add-ins for Microsoft Excel to increase productivity and ensure data accessibility.

## Extensibility model

Everything in Microsoft Dataverse is exposed as an API call. All tools and apps all access via the Web API as shown in the following diagram.

![Diagram of Microsoft Dataverse Extensibility.](../media/4-extensibility.png)

Dataverse provides extension capabilities at every horizontal layer. As a solution architect, you need to understand the different types of extensibility paradigms. Dataverse has:

- A rich API for integrating with Web Services and OData.
- No code logic with Business Rules, Calculated columns, Rollup Columns, Business Process Flows and more.
- Developer support with full .NET SDK with access to the transactional pipeline
- Client-side scripting with TypeScript and JavaScript
- Integration with Azure Service Bus and Event Hub
- Custom actions
- Custom API

These extensibility capabilities allow complex enterprise applications to be built using the Power Platform. Although a solution architect may not have been a developer, a solution architect needs to be familiar with each of these points and how they can be used in solutions.

## Dataverse API

The Dataverse Web API provides a development experience that can be used across a wide variety of programming languages, platforms, and devices. The Web API implements the OData (Open Data Protocol), version 4.0, an OASIS standard for building and consuming RESTful APIs over rich data sources. The Web API provides a modern, RESTful web service you can use to interact with data and metadata in Microsoft Dataverse using a wide variety of platforms, programming languages and devices.

> [!NOTE]
> When you are using the Dataverse connectors in Power Automate and Power Apps they are making calls to the OData API.

![Diagram of Microsoft Dataverse Web API details.](../media/4-dataverse-api.png)

A developer can add custom plug-in logic at the Pre and Post-Operation stages of a transaction to perform validation, calculations, and integrations using the .NET SDK.

> [!NOTE]
> The App API is also exposed to a SOAP endpoint. The SOAP endpoint is deprecated and should not directly be used for new apps.

Let us look further at creating custom logic.
