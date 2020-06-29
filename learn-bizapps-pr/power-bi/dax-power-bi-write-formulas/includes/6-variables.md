You can declare **DAX variables** in your formula expressions. When you declare at least one variable, a RETURN clause is used to define the expression, which then refers to the variables.

We recommend you use variables because they offer several benefits:

-   They improve the readability and maintenance of your formulas.

-   They can improve performance because variables are evaluated once and only ever when or if they're needed.

-   At design time, they allow easy testing of a complex formula by returning the variable of interest.

Let's see an example of a formula that declares a variables: The **Revenue YoY %** measure definition is rewritten to declare a variable that's assigned the value of the prior year's revenue.

```dax
Revenue YoY % =
VAR RevenuePriorYear =
	CALCULATE(
		[Revenue],
		SAMEPERIODLASTYEAR('Date'[Date])
	)
RETURN
	DIVIDE(
		[Revenue] - RevenuePriorYear,
		RevenuePriorYear
	)
```

Notice that the RETURN clause refers to the variable twice. This improved measure definition formula will execute in at least half the time because it doesn't need to evaluate the prior year's revenue twice.

In the **Adventure Works DW 2020 M02.pbix** Power BI Desktop file, refactor the **Revenue YoY %** measure to produce the same result as the above example.

For more guidance on using DAX variables, see [Use variables to improve your formulas](https://docs.microsoft.com/power-bi/guidance/dax-variables/?azure-portal=true).