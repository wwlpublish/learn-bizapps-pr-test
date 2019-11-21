Before you choose your data source in Power Apps it’s important to understand delegation. By using delegation, Power Apps optimizes its interaction with data sources to minimize the amount of transferred data. Put more simply, Power Apps uses delegation to offload the processing (which includes filtering, searching, and sorting) of data to the data source when available. Delegable processing is dependent on the data source and function being utilized. If you have a lot of data and need to rely on the back-end data source for operations such as filtering, then you might want to consider moving (or replicating) your data into an environment (such as Common Data Service) that works well with delegation. To replicate your data from a different source, you can use the Data Integrator to move data into Common Data Service.

Delegation in action
--------------------

There’s an example to help you understand delegation. You have a list of 5,000 projects stored in SharePoint. The **ProjectStatus**
column stores the values **Active** or **Inactive**. Half (2,500) of
the records are set to each of these values. You could show the list in
a gallery and filter it by using this formula.

> Filter(SharePointList, ProjectStatus = "Active")

Because the **Filter** function is delegable to a SharePoint data
source, Power Apps would send your formula to SharePoint. SharePoint
would process all 5,000 records and return to Power Apps the 2,500
records for which **ProjectStatus** is set **Active**. Those records
would all be available in your gallery. In this scenario, Power Apps
didn't process any data, and only the matching records were sent from SharePoint to Power Apps, which is very efficient.

When delegation isn't available
-------------------------------

Some functions cannot be delegated to some data sources. An example of a
non-delegable action is the **Search** function against the SharePoint
data source. The **Search** function is similar to **Filter**, but you
can use **Search** to check across multiple fields and to find partial
matches. For example, Search(SharePointList, "Rob",
"FirstName","LastName") would return all of the records where the string
"rob" is in either the **FirstName** or the **LastName** column. In this
example, Power Apps would return records for Robert Smith, Rob Jones, and
Suzy Robinson.

Because the **Search** function isn't delegable to the SharePoint data
source, Power Apps has to processes the records locally, which means
first the records are sent from SharePoint to Power Apps. By default, the
data source will only return the first 500 records. It is not the first
500 records that match your formula, but the first 500 records in the
data source. In this example, when you add this formula to your gallery,
SharePoint returns the first 500 records from the list to Power Apps, and
then Power Apps performs the search operation locally. If your list
contained 5,000 items, the other 4,500 records in your data source are
not processed or displayed. You can increase the default of 500 records
to a maximum of 2,000 records in the advanced settings of Power Apps
Studio. Under those circumstances, 3,000 records still would not be
processed or displayed.

Consider delegation when choosing a data source
-----------------------------------------------

The reason there is an entire module dedicated to delegation is that it
is a key consideration when choosing your data source. You need to
consider the types of functions you need, like Search, and the amount of
data you will have as you chose the best data source for your
application.

In the following unit, you will learn more about how delegation works
with various data sources.
