The CALCULATE function is one of the most versatile functions in Power BI. Here is the syntax:

```CALCULATE( <expression>, <filter1>, <filter2>, ... )```

The expression in the first parameter must be evaluated to return the result (a value) and is usually an aggregation function like SUM, AVG, MIN, etc. This expression is then evaluated in a context based on the filters. These filters can both expand and limit the current evaluation context.

With the CALCULATE function, you have control over row and filter context. You can add, remove, and update filters. It is the magic key for many calculations in DAX.

## Add a filter with CALCULATE

For example, the following snippet of code shows how to evaluate total sales and add an airplane filter context:

```Airplane Sales = CALCULATE( [Total Sales], 'Product Details'[ItemGroup] = "Airplane" )```

> [!TIP]
> CORRELATING TO TABLEAU: The following snippet of code shows how you would make the same calculation in Tableau: ```Airplane Sales = IF [ItemGroup] = "Airplane" THEN SUM([Sales Amount] ELSE 0 END```

## Update a filter with CALCULATE

For example, the following snippet of code shows how to get "2018 Sales", even when 2019 is selected in a year slicer:

```2018 Sales = CALCULATE( [Total Sales], DATE[Year] = 2018 )```

> [!TIP]
> CORRELATING TO TABLEAU: This one is interesting because there does not seem to be a direct Tableau comparison. To do this in Tableau, you would need to duplicate fields, bring in supplementary data sources, or perform calculations on each column.

## Ignore a filter with CALCULATE

For example, the following snippet of code shows how to find the total sales of states that have the city of Alexandria as a city ("Alexandria" is a value selected in a city slicer):

```Total Sales All States = CALCULATE( [Total Sales], ALL( Geography[State] ) )```

> [!TIP]
> CORRELATING TO TABLEAU: This is how you would make the same calculation in Tableau, using the EXCLUDE LOD expression. You will notice that this LOD expression is different from the other one by its granularity. With this expression, you just want to exclude the state from the view, instead of the state and city: ```Total Sales All States = { EXCLUDE [State] : SUM([Total Sales]) }```
