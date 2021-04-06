Inbound data integration is concerned with getting data into Microsoft Dataverse so that it is available to apps and flows.

## API

The Web API is one of two web services you can use to work with data and metadata in Dataverse. The other is the Organization Service.

The Dataverse Web API provides a development experience that can be used across a wide variety of programming languages, platforms, and devices. The Web API implements the OData (Open Data Protocol), version 4.0, an OASIS standard for building and consuming RESTful APIs.

All data operations that use the Dataverse APIs, whether using the Web API or the Organization Service, are converted into messages that follow the platform's event framework. This framework allows processes such as classic workflow and Power Automate cloud flows to be initiated, and allows developers to add custom plug-in steps that can be executed to perform validation and further processing.

## Event vs Batch

The solution architect should categorize the data that is required in Dataverse. A key category is event or batch based. The following diagram compares these two approaches.

![Diagram of inbound integration approaches.](../media/3-inbound.png)

## Push pattern

When considering getting data into Dataverse, there the solution architect will need to determine if data is pushed into Dataverse by another system, or is pulled into Dataverse.

The general push pattern for inbound integration into Dataverse is to use the Web API with the other system making the Web API calls. However, allowing other systems to write directly into Dataverse requires the other systems to understand the data model in Dataverse and how the processes in the Power Platform solution operate. It is often a good idea to create a layer for external systems to access:

- Event-based processing: Power Automate and Azure Logic Apps are a good approach for individual transactions triggered by changes in the source system.
- Batch processing: Batch is often abstracted by third-party tooling such as KingswaySoft or by using Azure Data Factory.
- Azure Functions: Azure Functions can abstract the need to implement business logic within your enterprise integration layer.
- Custom API: Create your own API for other systems to call.

> [!NOTE]
> Power Automate is often used to synchronize data between Dataverse environments.

When designing integration solutions consider using multiple threads to overcome latency effects and service limits.

## Pull pattern

The Pull pattern can be effective for data augmentation. You can use the pull pattern to get the data from external system on-demand when rows are retrieved in Dataverse. Virtual entities can be a good fit for this pattern.

## Alternate Keys

In Dataverse tables, rows are uniquely identified using a GUID. Other systems that need to integrate with Dataverse will either need to record the GUID in the database or have to query Dataverse to find the row that needs to be updated. This is inefficient. Dataverse provides the capability to create alternate keys on tables.

An alternate key allows external systems that need to read and write rows to efficiently access the rows without having to first run a query to find the GUID. For example, accounting systems often have an alphanumeric account number that uniquely identifies the account. You can define the account number field in the Dataverse table to be an alternate key so that the accounting system can read and write the account using the data it holds in its own system.

## Upsert

You can reduce the complexity involved with data integration scenarios by using the Upsert message. When pushing data into Microsoft Dataverse from an external system, you may not know if a record already exists in Dataverse. In such cases, you will not know if you should use an Update or a Create operation. You first need to perform a query to determine if it exists before performing the appropriate operation. You can now reduce this complexity and load data into Dataverse more efficiently by using the Upsert message.

Upsert is used with Alternate Keys. You provide enough information in the Upsert call. Dataverse will look up the row and either create or update the row as shown in the following diagram.

![Diagram that shows the use of upsert logic.](../media/3-upsert.png)

## Custom APIs

Custom APIs are newly released functionality that you can abstract and consolidate a group of operations into an API that the other systems can call.

Custom APIs are defined by creating a custom API record as shown in the following screenshot.

![Screenshot of custom API record.](../media/3-custom-api.png)

A Custom API can be a Function or an Action. You should use a Function, which is a GET request, to get information, and an Action when you want to modify data.

A plug-in is used to perform the actual data operation for the Custom API.

> [!NOTE]
> For more information, see [custom APIs](https://docs.microsoft.com/powerapps/developer/data-platform/custom-api).

## Azure Functions

Azure Functions enables developers to create complex reusable custom logic and integrate with the other systems. Azure Functions can be consumed with Webhooks or wrapped inside a Custom Connector. Using Azure Functions, developers can create reusable components for functional consultants and app makers to use in their apps and flows. Azure Functions can also be accessed by other applications to push and pull data into Dataverse. The Azure Function can connect to Dataverse and access the data.

You can create an API for your solution using Azure Functions to create with custom server-side logic and expose the API securely through Azure API Management (APIM).
