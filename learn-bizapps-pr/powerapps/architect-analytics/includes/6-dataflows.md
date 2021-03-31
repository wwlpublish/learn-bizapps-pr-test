Dataflows are a cloud based extract, transform, and load (ETL) service that lets you ingest data from various sources and also convert it into an analysis-ready form. Dataflows can be used by Power BI to process and ingest huge volumes of data.

![Diagram of Dataflow process.](../media/6-dataflows-self-service.png)

Dataflows are designed to support the following scenarios:

- Create reusable transformation logic that can be shared by many datasets and reports inside Power BI. Dataflows promote reusability of the underlying data elements, preventing the need to create separate connections with your cloud or on-premise data sources.
- Expose the data in your own Azure Data Lake Gen 2 storage, enabling you to connect other Azure services to the raw underlying data.
- Create a single source of the truth by forcing analysts to connect to the dataflows, rather than connecting to the underlying systems, providing you with control over which data is accessed, and how data is exposed to report creators. You can also map the data to industry standard definitions, enabling you to create tidy curated views, which can work with other services and products in the Power Platform.
- If you want to work with large data volumes and perform ETL at scale, dataflows with Power BI Premium scales more efficiently and gives you more flexibility. Dataflows supports a wide range of cloud and on-premise sources.
- Prevent analysts from having direct access to the underlying data source. Since report creators can build on top of dataflows, it may be more convenient for you to allow access to underlying data sources only to a few individuals, and then provide access to the dataflows for analysts to build on top of. This approach reduces the load to the underlying systems, and gives administrators finer control of when the systems get loaded from refreshes.

Dataflows can transform data using PowerQuery and enrich data using Cognitive Services and Azure Machine Learning as shown in the following diagram.

![Diagram of Dataflow capabilities.](../media/6-dataflows.png)

Once you’ve created a dataflow, you can use Power BI Desktop and the Power BI service to create datasets, reports, dashboards, and apps that use the Common Data Model to drive deep insights into your business data.

Data exported from Dataverse into Azure Data Lake can be imported into Power BI using Dataflows.

## Dataset vs Dataflow

Dataflows are optional but datasets are not. You cannot use a Dataflow directly, the Dataflow populates the dataset.

If you do not use a Dataflow and just use datasets, the dataset prep done over and over again in each dataset. With Dataflows, the Dataflow performs the data prep once and then, then each dataset uses the pre-done prep. Dataflows can also have computed entities that are just the insights needed for report.

You will always will use datasets, but can choose to use a Dataflow if it helps.

## Enterprise BI

Enterprise BI where data is extracted for use in broader enterprise reporting tools has many benefits:

- Reduces load on operational data stores.
- Allows for transformation and historical analytics.
- Allows for use with third-party reporting tools

The following diagram shows using the Data Export Service to extract data from Dataverse and populate a data warehouse that reporting tools such as Power BI can use.

![Diagram of Dataflow process.](../media/6-enterprise-reporting.png)

> [!NOTE]
> You could substitute the Export to Azure Data Lake in place of the Data Export Service.
