While importing data into Power BI, you may encounter a very wide variety of errors. This variety is the result of several factors: 

-   Power BI imports from a wide number of data sources 

-   Each data source may have dozens (and sometimes hundreds) of
    different error messages 

-   Other components can cause errors, like hard drives, networks,
    software services, and operating systems 

-   Data can often not comply with any specific schema.   

Below we will cover some of the more common error messages you may see in Power BI. 

### Query Timeout Expired 

Relational source systems often have many users, concurrently using the
same data in the same database.  Some relational systems and their
administrators seek to limit a user from hogging all the hardware
resources by setting a query timeout.  These timeouts can be configured
for any timespan, from as little as five seconds to as much as 30
minutes or more.   

For instance, if we're pulling data from our organization's SQL Server,
we might see the following error: 

> [!div class="mx-imgBorder"]
> [![data import errors for query timeout](../media/9-data-import-query-timeout-ss.png)](../media/9-data-import-query-timeout-ss.png#lightbox)

### Power BI Query Error: timeout expired

This is an indicator that you've pulled too much data according to your
organization's policies.  Administrators are doing this to avoid slowing
down a different application or suite of applications that may also be
using that database.

You can resolve this by pulling fewer columns or rows from a single
table.  While writing SQL statements, it is a common practice to include
groupings and aggregations.  You can also join multiple tables in a
single SQL statement.   Finally, you perform complicated subqueries and
nested queries in a single statement.  These complexities add to the
query processing requirements of the relational system and can greatly
elongate the time of execution.    

But what if you need all of those rows and columns and complexity? 
Consider taking small chunks of data and then stitch it back together
using Power Query.  For instance, you can take half the columns in one
query and the other half in a different query.  Power Query can merge
those two queries back together after the fact. 

### We couldn't find any data formatted as a table 

Sometimes you may encounter this  error while importing data from
Microsoft Excel.  Luckily, this error is pretty self-explanatory.   
Power BI is expecting to find data formatted as a table from Excel.  The
error event tells you the resolution. Perform the following steps:

1.  Open your Excel workbook, highlight the data you wish to import.   

1.  Type CTRL-T. The first row will likely be your column headers.   

1.  Verify that is how you'd like to name your columns.  Then try to import data from Excel again.  This time, it works!  

	> [!div class="mx-imgBorder"]
	> [![Power BI Excel error: We couldn't find any data formatted as a table](../media/9-format-as-table-excel-ss.png)](../media/9-format-as-table-excel-ss.png#lightbox)

### Could not find file 

While importing data from a file, you may get the error "Could not find file."   

> [!div class="mx-imgBorder"]
> [![The Could not find file error screen](../media/9-file-location-ss.png)](../media/9-file-location-ss.png#lightbox)

This is usually caused by either the file moving locations or the
permissions to the file changing.  If it's the former, you'll have to
find the file and change the source settings.  Open Power Query by
selecting the Transform Data button in Power BI.  Highlight the query
that is creating the error.   On the left, under Query Settings, choose
the gear icon next to source. 

> [!div class="mx-imgBorder"]
> [![The query settings pane](../media/9-query-changes-ss.png)](../media/9-query-changes-ss.png#lightbox)

### Change the file location to the new location.  

> [!div class="mx-imgBorder"]
> [![The file location settings pane](../media/9-file-location-new-location-ss.png)](../media/9-file-location-new-location-ss.png#lightbox)

### Data type errors 

Sometimes when you import data into Power BI, the columns appear blank. 
This can be because of an error in interpreting the data type in Power
BI.  The resolution to this error is unique to the data source.  For
instance, if you are importing data from SQL Server and see blank
columns, you may try to convert to the correct data type in the query. 
Instead of this query: 

```
SELECT CustomerPostalCode FROM Sales.Customers Use this query: 
SELECT CAST(CustomerPostalCode as varchar(10)) FROM Sales.Customers 
```

By specifying the correct type at the data source, you can eliminate
many of these common data source errors. 

There are many errors you may encounter in Power BI, caused by the
wide-variety of data source systems where your data may reside.  If you
encounter an error you did not find here, search the Microsoft
documentation for the error message.  You may find your resolution
there. 
