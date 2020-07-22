First, watch this video to learn about iterator functions.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4AkNG]

DAX includes a set of functions known as *iterator functions*. Iterator functions enumerate all rows of a given table and evaluate a given expression for each row. They provide you with flexibility and control over how your model calculations summarize data.

By now, you're familiar with single-column summarization functions, including SUM, COUNT, MIN, MAX and others. Each of these functions has an equivalent iterator function. They're easily identified by the "X" suffix; there's SUMX, COUNTX, MINX, MAXX, and others. There are also specialized iterator functions that perform filtering, ranking, semi-additive calculations over time, and more.

Characteristic of all iterator functions, you must pass in a table and an expression. The table can be a model table reference or an expression that returns a table object. The expression must evaluate to a scalar value.

By the way, we can now let you know that single-column summarization functions, like SUM, are just shorthand functions. Internally, Power BI converts the SUM function to SUMX. So, the following two measure definitions produce the exact same result and there's no difference in how Power BI evaluates them or performance.

```dax
Revenue = SUM(Sales[Sales Amount])
```

```dax
Revenue =
SUMX(
	Sales,
	Sales[Sales Amount]
)
```

It's important to understand how context works with iterator functions. Because iterator functions enumerate over table rows, the expression is evaluated for each row in row context just like calculated column formulas. The table itself is evaluated in filter context. So, using the above **Revenue** measure definition example, if a report visual were filtered by fiscal year **FY2020**, the **Sales** table would contain sales rows that were ordered *in that year*. Filter context is described in the filter context module.

> [!IMPORTANT]
> When using iterator functions, you must take care to avoid using large tables (of rows) with expressions that use expensive DAX functions. Some functions, like the [SEARCH](https://docs.microsoft.com/dax/search-function-dax/?azure-portal=true) DAX function, which scans a text value looking for specific characters or text, can result in slow execution. Also, the [LOOKUPVALUE](https://docs.microsoft.com/dax/lookupvalue-function-dax/?azure-portal=true) DAX function, may result in slow row-by-row retrieval of values. In this second case, use the [RELATED](https://docs.microsoft.com/dax/related-function-dax/?azure-portal=true) DAX function instead, whenever possible.
