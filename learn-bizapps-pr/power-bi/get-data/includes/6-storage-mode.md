The most popular way to use data in Power BI is to import it into a
Power BI dataset.  This means the data is housed in the Power BI file
and gets published along with the Power BI reports. This makes it easy
to interact directly with your data. 

In our example, you are building Power BI reports for the
Sales department at your company, TradeWind Traders. The first task you
need to do is to retrieve your datasets into Power BI so you can build
visuals and other report elements. Sales has many different datasets of
varying sizes. For security reasons, you are not allowed to import local
copies of the data into your reports so importing data directly is no
longer an option. So, you need to be able to create a direct connection
to the Sales data source. Let's look at how we can
ensure these business requirements are satisfied when importing data
into Power BI.  

When there are no security or size limitations, you can sometimes import
data from a local copy of a data source directly, which makes it easy to
interact directly with your data in its original form. This is the most
popular way to retrieve data into Power BI.  

However, as in the case at TradeWind Traders, there may be security
requirements around your data that make it impossible to directly import
a copy. Or your datasets may simply be too large and would take too long
to load into Power BI, and you want to avoid creating a performance
bottleneck. Power BI solves for these issues using DirectQuery, which
allows you to query the data in the data source directly and not import
a copy into Power BI. DirectQuery is particularly useful as it ensures
you are always viewing the most recent version of the data.  

These different ways of importing data into Power BI can be chosen
through Storage Modes in Power BI. Let's take a closer look. 

There are three different types of storage modes you can choose from:  

-   Import 

-   DirectQuery 

-   Dual (Composite) Mode 

You can access Storage Modes by toggling to the Model view, clicking on
a data table, and in the resulting Properties pane, scrolling down to
Advanced and then to Storage Mode where you can choose which mode, as
seen in the following visual.  

[![showing storage mode](../media/6-storage-mode-ssm.png)](../media/6-storage-mode-ssm.png#lightbox)

Let's take a closer look at the different types of Storage Modes.  

### Import Mode 

This mode allows you to create a local Power BI copy of your datasets
from your data source. You can use all Power BI Service features with
this storage mode, including Q&A and Quick Insights. Data refreshes must
be done manually. Import mode is the default when creating new Power BI
reports.  

### DirectQuery 

Using this option is useful when you do not want to save local copies of
your data, as your data will not be cached. Instead, you can query the
specific tables you will need using native Power BI queries, and the
required data will be retrieved from the underlying data source. You are
essentially creating a direct connection to the data source
itself. Using this model ensures that you are always viewing the most
up-to-date data, and that any security requirements are satisfied.
Additionally, this mode is perfectly suited if you have huge datasets to
pull data from - instead of slowing down performance by having to load
large amounts of data into Power BI, DirectQuery will just create a
connection to the source, solving data latency issues as well.   

### Dual (Composite Mode) 

In Dual Mode, you can identify some data to be directly imported, and
other data that must be queried. Any table brought in to your report is
a product of both import and direct query. Using this mode allows for
Power BI to choose the most efficient form of data retrieval.  

Now that you know this information about the different storage modes,
you can satisfy Sales' requirements and create a data connection in
Power BI directly to the data source. If in the case that Sales did not
have any security requirements around importing their datasets, you
could use Import mode to directly import copies into your reports. On
the other hand, if they had specific datasets that they do not want you
to save a local copy of and others you can, then the best option to use
would be Dual or Composite Mode.  By having the ability to choose from
different import options through Storage Modes, Power BI provides an
easy way to satisfy business requirements.  

For more information regarding Storage Modes, please refer to [Storage
Modes](https://docs.microsoft.com/power-bi/transform-model/desktop-storage-mode/?azure-portal=true). 
