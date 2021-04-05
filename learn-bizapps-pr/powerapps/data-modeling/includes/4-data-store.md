In this unit, we will compare data stores for your apps.

## Where's the data?

When designing your solution, it is important to understand existing data sources for your solution.

### New data

If your app is creating data that does not already exist anywhere, such as in situations where the existing business process was done using paper, we recommend storing the data in Dataverse.

### Read/write from existing system

This is a type of data where you need to retrieve the latest information from an existing database or system. In these cases, data needs to be requested at the time you need it.

### Make a copy of existing data

In situations where original data should never be modified or overwritten, you can copy the data to another data store such as Dataverse. This ensures that the data in the original system won't be changed, yet your app can work with it. This scenario is common when working with data in accounting and revenue-related systems.

## Where to store data

Data modeling on the Power Platform should look at the whole data architecture picture and include a logical look at data from Dataverse, Data Lakes and external sources using connectors.

### Dataverse

Dataverse uses abstracts you and your apps from how data is stored. All data in Dataverse is accessed via REST APIs. Currently the tables in Dataverse are relational tables but this may change in the future. Dataverse stores its data in a mixture of stores and formats:

- Azure SQL Server Elastic Pools
- Azure CosmosDB
- Azure Storage
- Azure Data Lake in CDM folders

### Existing Data

Power Apps apps have three ways of using existing data:

- Connector: A connector allows the app to connect to various systems and sources—such as SharePoint, SQL Server, or Office 365—and directly retrieve data from them or save data to them.
- DataFlow: DataFlows extract, transform, and load data from another system to Dataverse or Azure Data Lake storage. Unlike a connector, it fetches data in a scheduled batch. Instead of just retrieving the data as-is from the data source, you can use Power Query Online to manipulate, cleanse, and transform data before you store it to the target storage.
- Virtual Tables: A virtual table is a custom table in Dataverse that contain data from an external data source. Virtual tables appear in your app to users as regular table rows, but contain data that is sourced from an external database, such as an Azure SQL Database. Virtual tables are no longer read-only and apps can create and write data to Virtual tables.

### Choosing where to store data

When choosing where to store data for your solution here are some recommendations:

Dataverse: For transactional data your apps are going to consume and manipulate.
Azure Data Lake: Good for data from other systems, read focused, and brought into a common data model structure.
Connectors: Connectors: Good for leaving existing data where it is and accessing other services that make their data available.
