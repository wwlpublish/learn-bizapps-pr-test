Determining when delegation will and will not happen is a combination of several variables. The first thing to consider is the data source. The following table shows the different functions and whether they support delegation to a given data source. In this table, “Yes” means the data source does the processing across all of the records, “No” means the data source returns the first 500 (default) records to PowerApps, and PowerApps then processes the function locally.


|               | Common Data Service  | SharePoint   | SQL Server   | Dynamics 365   | Salesforce |
| :-------------| :-------------| :------------| :------------| :--------------| :----------|
| Average       | Yes**       | No           | Yes          | No             | No         |
| Filter        | Yes           | Yes          | Yes          | Yes            | Yes        |
| LookUp        | Yes           | Yes          | Yes          | Yes            | Yes        |
| Max           | Yes**       | No           | Yes          | No             | No         |
| Min           | Yes**       | No           | Yes          | No             | No         |
| Search        | Yes*         | No           | Yes          | Yes            | Yes        |
| Sort          | Yes           | Yes          | Yes          | Yes            | Yes        |
| SortByColumns | Yes           | Yes          | Yes          | Yes            | Yes        |
| Sum           | Yes**       | No           | Yes          | No             | No         |

* For string fields only.

** The aggregate functions are limited to a collection of 50,000
records. If needed, use the Filter function to select 50,000 records
from a larger set before using the aggregate function.

As you can see, that is quite the matrix. But it is the best starting
point when determining your data source. Make sure that your data source
will support you with the functions you need, for the amount of data you
will have. All other data sources that are not listed do not support
delegation and will be limited in the number of records they can return.

Additionally, if you are using the Filter or LookUp function, then you also will use a predicate. This is what allows you to perform the evaluation part of the formula. For example, FirstName = "Rob" is using the = predicate. Some data sources do not support some predicates. For example, Salesforce does not support the IsBlank predicate. This means that while the formula Filter(SalesforceCustomers, Name = "Contoso") is delegable, the formula Filter(SalesforceCustomers, IsBlank(Name)) is not delegable.

Use the following table to understand the different options.


|                           | Common Data Service | SharePoint       | SQL Server | Dynamics 365 | Salesforce |
| :-------------------------| :------------| :----------------| :----------| :------------| :----------|
| Not                       | Yes          | No               | Yes        | Yes          | Yes        |
| IsBlank                   | No           | No               | Yes        | Yes          | No         |
| TrimEnds                  | No           | No               | Yes        | No           | No         |
| Len                       | No           | No               | Yes        | No           | No         |
| +, -                      | No           | No               | Yes        | No           | No         |
| \<, \<=, =, \<\>, \>, \>= | Yes          | Yes\*\*\*        | Yes        | Yes          | Yes        |
| And, Or, Not              | Yes\*\*\*\*  | Yes (except Not) | Yes        | Yes          | Yes        |
| In                        | No           | No               | Yes        | No           | Yes        |
| StartsWith                | No           | Yes              | No         | No           | No         |

*** For numeric columns, all operators can be delegated. For ID
columns, the only delegated option is the \'=\'. The data source cannot
delegate Date columns.

**** For operators only. And/Or/Not functions aren\'t delegated.

The Column type can also factor in
----------------------------------

One other thing to consider is that the column type can also affect whether delegation is possible. Complex columns, like a SharePoint lookup column, are not delegable. These columns have deeper logic and are only processable locally by PowerApps. The good news is that if you use a complex column PowerApps will provide the visual warning indicators so you can build your app as appropriate.
