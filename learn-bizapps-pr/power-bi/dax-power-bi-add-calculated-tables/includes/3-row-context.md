Now that you've created calculated columns, let's understand how their formulas are evaluated.

The formula for a calculated column is evaluated for each table row. What's more, it's evaluated within row context, which literally means "the current row". Consider the **Due Fiscal Year** calculated column definition.

```dax
Due Fiscal Year =
"FY"
	& YEAR('Due Date'[Due Date])
		+ IF(
			MONTH('Due Date'[Due Date]) <= 6,
			1
		)
```

When the formula is evaluated for each row, the `'Due Date'[Due Date]` column reference returns the column value for *that row*. For many, it's an easy concept to understand. You'll find that Excel has the same concept when working with formulas in [Excel tables](https://support.office.com/article/overview-of-excel-tables-7ab0bb7d-3a9e-4b56-a3c9-6c94334e492c/?azure-portal=true).

However, it's important to understand that row context does not extend beyond the table. If your formula needs to reference columns in other tables, you have two options:

1.  If the tables are related either directly or indirectly you can use either the [RELATED](https://docs.microsoft.com/dax/related-function-dax/?azure-portal=true) or [RELATEDTABLE](https://docs.microsoft.com/dax/relatedtable-function-dax/?azure-portal=true) DAX functions. The RELATED function retrieves the value at the one-side of the relationship, while the RELATEDTABLE retrieves values on the many-side. Note that the RELATEDTABLE function returns a table object.

1.  When the tables aren't related, you can use the [LOOKUPVALUE](https://docs.microsoft.com/dax/lookupvalue-function-dax/?azure-portal=true) DAX function.

Generally, try to use the RELATED function whenever possible. It'll usually perform better than the LOOKUPVALUE function due to the ways relationship and column data is stored and indexed.

Let's now add the following calculated column definition to the **Sales** table.

```dax
Discount Amount =
(
	Sales[Order Quantity]
		* RELATED('Product'[List Price])
) - Sales[Sales Amount]
```

The calculated column definition adds the **Discount Amount** column to the **Sales** table. Power BI evaluates the calculated column formula for each row of the **Sales** table. The values for the **Order Quantity** and **Sales Amount** columns are retrieved within row context. However, because the **List Price** column belongs to the **Product** table, the RELATED function is required to retrieve the list price value *for the sale product*.

Row context is used when calculated column formulas are evaluated. It's also used when a class of functions known as the *iterator functions* are used. Iterator functions provide you will flexibility to create sophisticated summarizations. We'll introduce iterator functions in a later module.