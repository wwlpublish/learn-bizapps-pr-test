Azure Analysis Services is an Azure product that allows you to ingest data from multiple data sources, build relationships between the data, and creates calculations on the data.   Those calculations are built using data analysis expressions (DAX).  In fact, Azure Analysis Services is very similar to the data modeling and storage technology in Power BI.  
 
To resume the scenario, Tailwind Traders uses Azure Analysis Services to store financial projection data. You’ve been asked to compare this data with actual sales data in a different database. Getting data from Azure Analysis Services cubes is similar to getting data from SQL Server, in that you can:

- Authenticate to the server.
- Pick the cube you want to use.
- Select which tables you need. 
 
Notable differences between Azure Analysis Services cubes and SQL Server are:

- Analysis Services cubes have calculations already in the cube, which will be discussed in more detail later.
- If you don’t need an entire table, you can query the data directly. Instead of using Transact-SQL (T-SQL) to query the data, like you would in SQL Server, you can use multi-dimensional expressions (MDX) or data analysis expressions (DAX). 
- You don’t need to use the **Get Data** button in Power BI Desktop.
 


### Connect to data in Azure Analysis Services  

As previously mentioned, you use the **Get data** feature in Power BI Desktop. When you select **Analysis Services**, you are prompted for the server address and the database name with two new options: **Import** and **Connect live**.

> [!div class="mx-imgBorder"]
> [![Azure Analysis Services server and database](../media/7-analysis-services-connection-ss.png)](../media/7-analysis-services-connection-ss.png#lightbox)

**Connect live is a new option in** Azure Analysis Services. . Azure Analysis Services uses the tabular model and DAX to build calculations, similar to Power BI. These models are compatible with one another. Using the **Connect live** option helps you keep the data and DAX calculations in their original location, without having to import them all into Power BI. Azure Analysis Services has a fast refresh schedule feature, when data is refreshed in the service, Power BI reports are immediately updated, without the need to initiate a Power BI refresh schedule. This process improves the timeliness of the data in your report. 
 
Similar to a relational database, you can choose the tables that you want to use.  If you want to directly query the Azure Analysis Services model, you can use DAX or MDX. 
 
Because you want to get data to other data in your organization , you will likely import the data directly into Power BI. An acceptable alternative is to import all other data that you want (from Excel, SQL Server, and so on) into the Azure Analysis Services model and then use a live connection. Using this approach, the data modeling and DAX measures are all performed in one place, and is a much simpler and easier way to maintain your solution.

For more information on connecting Power BI to Azure Analysis Services,
please refer to [Connect with Power BI documentation.](https://docs.microsoft.com/azure/analysis-services/analysis-services-connect-pbi/?azure-portal=true) 

