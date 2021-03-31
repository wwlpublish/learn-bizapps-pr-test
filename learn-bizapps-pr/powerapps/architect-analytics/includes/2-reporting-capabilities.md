The reporting options provided in the Power Platform meet many operational reporting requirements,

![Dataverse reporting options.](../media/2-operational-options.png)

## Model-driven apps

Dataverse provides many reporting options for Model-driven apps:

- Views: Views are stored queries on the tables in Dataverse with selected columns and filters. Many reporting requirements are simple lists of data. Views can often meet many of such requirements.
- Charts: Charts are visualizations of Dataverse data in a View.
- Dashboards: A Dashboard is a collection of Views and Charts. Power BI visualizations can also be added to Dashboards. Standard Dashboards are for viewing of data only. Interactive Dashboards allow users to filter data and take action.

The advantages of these options are:

- Easy access from within apps
- Data is always current
- Security model is enforced
- Included in solution packages
- No special skills are required
- Users can create their own personal views, charts, and dashboards

The disadvantages of these options are:

- Only simple visualizations are available
- Data is limited to a single table and tables in many-to-1 relationships
- Data is always current and cannot look back at a point in time
- Trends cannot be analyzed
- Users must have a license and be an app user
- Charts and dashboards are limited to 50,000 rows
- Views will only show the first 5,000 rows

## Export to Excel

Dataverse provides the ability to Export to Excel. Users can export either as static data or as a dynamic query. The export of data is from a View with columns and filters.

Static data can be provided to users who are not app users. Static data is for when you need to get a snapshot of the data at the current date and time or if you want to share the data with others.

Dynamic query is used to get the most up-to-date information and be able to refresh it in Excel and match what you see in your app at any time. A user must have a license to access an Excel worksheet with a dynamic query. Dynamic queries support either exporting the data as rows or as a PivotTable.

The Export to Excel feature can only include data from Dataverse.

Data can also be edited in Excel Online and saved back into Dataverse to give an immersive editing user experience.

There is a limit for exporting to Excel of 100,00 rows by default. This limit can be increased to 1,000,000 rows with the MaxRecordsForExportToExcel setting.

## Word and Excel templates

Word and Excel templates can both be used for reporting. Word templates are for a single row and all its related rows. Excel templates are for a view, or list, of rows. Excel templates can include visualizations and other analysis provided by Excel.

Access to individual templates can be controlled through security.

> [!IMPORTANT]
> Word and Excel templates cannot be included in a solution package. Document template downloaded from one environment can only be used within that environment. environment to environment migration for Word or Excel templates isn't currently supported.

## Report wizard

The report wizard is an end user reporting generation tool for model-driven apps. The report wizard can create a SQL Reporting Services report from data held in Dataverse. The report can either be tabular or contain a simple chart.

The reports that the wizard generates have a simple layout as shown in the following screenshot.

![Screenshot of report wizard report.](../media/2-report-wizard.png)

You can download and edit these reports, to change their layout. Reports created by the report wizard can be included in a solution package.

## SQL Reporting Services

A data analyst can create reports using SQL Reporting Services and Visual Studio. SQL Reporting Services reports can retrieve multiple datasets from different parts of the data model, which allows for more complex reports than can be created with the options so far described.

> [!NOTE]
> Reports and queries can execute for up to five minutes. When the maximum period is reached, the report will time out and a message is returned to the user. Within the five-minute duration, reports and queries are allowed to span large datasets that are beyond 50,000 rows.

Here are some tips for creating reports:

- Design reports to query smaller datasets over shorter periods of time by adding a time-based filter in the report, such as the current month or quarter, to limit the results.
- Limit the number of tables that are needed to return the result. This helps reduce the time required to run the query and return the result set.
- Reduce the number of rows shown in detailed reports. Suitable filtering can be used to reduce the number of rows returned by the query to reduce timeouts.
- For aggregated or summarized reports, queries must be used to push the aggregation to the database and not fetch detailed rows and perform aggregation in the SQL Server Reporting Services report.

> [!IMPORTANT]
> Running large reports can affect performance for all users. The solution architect should consider offloaded the reporting by exporting the Dataverse data to enable more complex and deeper reporting.

## Export to Azure SQL

The Data Export Service replicates Dataverse data to your own SQL database. You can use Azure SQL or a SQL Server on an Azure VM. Data Export Service is available as an add-on from AppSource.

![Dataverse.](../media/2-data-export-service.png)

> [!IMPORTANT]
> The Data Export Service is only available for Dynamics 365 customer engagement apps.

The Data Export Service intelligently synchronizes the entire data initially and thereafter synchronizes on a continuous basis as changes occur (delta changes) in the system. This helps enable several analytics and reporting scenarios on top of data with Azure data and analytics services. The data in the Azure SQL database is almost real-time. Data Analysts can run SQL queries natively on the Azure SQL database. Error handling and monitoring are provided.

> [!NOTE]
> The Data Export Service leverages the change tracking features of Dataverse. A table must be enabled for change tracking to be exported by the Data Export Service.

An alternative export option is to use Azure Data Lake.

## Export to Azure Data Lake

The Export to Azure Data Lake service enables continuous replication of Dataverse table data to Azure Data Lake Gen 2 which can then be used to run analytics such as Power BI reporting, Machine Learning, Data Warehousing, and other integration scenarios.

![Export to Data Lake.](../media/2-export-data-lake.png)

Export to data lake simplifies the technical and administrative complexity of export tables for analytics. Within a few clicks, customers can  link their Dataverse environment to a Data Lake in their Azure subscription, select tables and export them to data lake. All data and metadata changes (initial and incremental delta) in Dataverse are automatically pushed to the Azure Data Lake Gen 2 without any additional actions.

Data is stored in the Common Data Model format that can be consumed by Power BI and other Azure Analytics services.

## Alternative options

Advanced Find is one of the most useful tools that functional consultants, business analysts, administrators, and even end users should master. Advanced Find allows users to create their own queries and save them as personal views. Advanced Find queries are the basis for many other functions in model-driven apps including Export to Excel, Excel Templates, Bulk Delete, Duplicate Detection, and Dashboards.

Creating a report is not always needed:

- For adhoc reporting, consider using a combination of Advanced Find and Excel.
- For users, consider using out of the box Dashboards and Charts.
- For reporting that must be printed or exported, consider creating Word Templates and Excel Templates.

The solution architect will need to consider any third-party reporting tools that the customer is using.

Power BI should always be considered for reporting and analytics.
