Each model calculation type, calculated table, calculated column, or measure is defined by its name, followed by the equals symbol (=), followed by a **DAX formula**. So, use the following template to create a model calculation:

```dax
<Calculation name> = <DAX formula>
```

> [!NOTE]
> A calculation name cannot include leading or trailing spaces, control characters, or the following special characters: .,;':/\*|?&%$!+=()[]{}<>

For example, the definition of the **Ship Date** calculated table that duplicates the **Date** table data is:

```dax
Ship Date = 'Date'
```

A DAX formula consists of expressions that return a result. The result is either a table object or a scalar value. Calculated table formulas must return a table object; calculated column and measure formulas must return a scalar or single value.

Formulas are assembled by using:

-   DAX functions

-   DAX operators

-   References to model objects

-   Constant values, like the number 24 or the literal text "FY" (for fiscal year)

-   DAX variables

-   Whitespace

> [!TIP]
> When you enter DAX formulas in Power BI Desktop you have the benefit of IntelliSense. IntelliSense is a code-completion aid lists functions and model resources. When you select a DAX function, it also provides you with a definition and description. We recommend you leverage IntelliSense to help you quickly build accurate formulas.

## DAX functions

Like Excel, DAX is a functional language: Formulas rely upon **DAX functions** to accomplish specific goals. Typically, functions have arguments that allow passing in variables. Formulas can use many function calls, often nesting functions within other functions.

In a formula, function names must be followed by parentheses. Within the parentheses, variables are passed in.

> [!NOTE]
> Some functions don't take arguments, or arguments might be optional.

We'll describe working with DAX functions in more detail in a later unit.

## DAX operators

Formulas also rely upon **DAX operators**, which can perform arithmetic calculations, compare values, work with strings, or test conditions.

We'll describe DAX operators in more detail in a later unit.

## References to model objects

Formulas can only refer to three types of model objects: tables, columns, or measures. A formula can't refer to a hierarchy or a hierarchy level. (Recall that a hierarchy level is based on a column, so your formula can refer to a hierarchy level's column.)

### Table references

When referencing a table in a formula, officially the table name is enclosed within single quotes. In the following calculated table definition, notice that the **Date** table is enclosed within single quotes.

```dax
Ship Date = 'Date'
```

However, single quotes can be omitted when both of the following conditions are true:

1.  The table name does not include embedded spaces.

2.  The table name is not a reserved word used by DAX. All DAX function names and operators are reserved words. Note that *Date* is a DAX function name, so that explains why when referencing a table named **Date**, it must be enclosed within single quotes.

In the following calculated table definition, it's possible to omit the square brackets when referencing the **Airport** table:

```dax
Arrival Airport = Airport
```

### Column references

When referencing a column in a formula, the column name must be enclosed within square brackets. Optionally, it can be preceded by its table name. For example, the following measure definition refers to the **Sales Amount** column.

```dax
Revenue = SUM([Sales Amount])
```

Because column names are unique within a table but not necessarily unique within the model you can disambiguate the column reference by preceding it with its table name. It's known as a *fully qualified column*. Note that some DAX functions require passing in fully qualified columns.

> [!TIP]
> To improve the readability of your formulas, we recommend you always precede a column reference with its table name.

The previous example measure definition can be rewritten as:

```dax
Revenue = SUM(Sales[Sales Amount])
```

### Measure references

When referencing a measure in a formula, like column name references, the measure name must be enclosed within square brackets. For example, the following measure definition refers to the **Revenue** and **Cost** measures.

```dax
Profit = [Revenue] - [Cost]
```

For DAX beginners, the fact that column and measure references are always enclosed within square brackets can be cause for confusion when reading a formula. However, once you're proficient with DAX fundamentals, you'll easily determine which type of object it is. It's because in DAX formulas, columns and measures are used in very different ways.

> [!TIP]
> It's possible to precede a measure reference with its table name. However, measures are a model-level object. While they're assigned to a home table, it's just a cosmetic relationship to logically organize measures in the **Fields** pane.

So, while we recommend you always precede a column reference with its table name, the inverse is true for measures: We recommend you never precede a measure reference with its table name.

For further guidance, see [Column and measure references](https://docs.microsoft.com/power-bi/guidance/dax-column-measure-references/?azure-portal=true).

## DAX variables

Formulas can declare DAX variables to store results.

We'll describe how and when to use DAX variables in a later unit.

## Whitespace

Whitespace refers to characters you can use to format your formulas in a way that's quick and easy to understand. Whitespace characters include:

-   Spaces

-   Tabs

-   Carriage returns

Whitespace is optional and it doesn't modify your formula logic or negatively impact on performance. We strongly recommend you adopt a format style and apply it consistently. Here are some recommendations:

-   Use spaces between operators.

-   Use tabs to indent nested function calls.

-   Use carriage returns to separate function arguments, especially when it's too long to fit on a single line. Formatting in this way makes it easy to troubleshoot, especially when there's are missing parenthesis.

-   Err on the side of too much whitespace than too little.

> [!TIP]
> In the formula bar, to enter a carriage return, press **Shift+Enter**. Pressing **Enter** alone will commit your formula.

Consider the following measure definition that's written a single line, and that includes five DAX function calls:

```dax
Revenue YoY % = DIVIDE([Revenue] - CALCULATE([Revenue], SAMEPERIODLASTYEAR('Date'[Date])), CALCULATE([Revenue], SAMEPERIODLASTYEAR('Date'[Date])))
```

Here's the same measure definition but now formatted. It's now easier to read and understand:

```dax
Revenue YoY % =
DIVIDE(
	[Revenue]
		- CALCULATE(
			[Revenue],
			SAMEPERIODLASTYEAR('Date'[Date])
	),
	CALCULATE(
		[Revenue],
		SAMEPERIODLASTYEAR('Date'[Date])
	)
)
```

Try formatting the measure for yourself. Open the **Adventure Works DW 2020 M02.pbix** Power BI Desktop file, then in the **Fields** pane, expand the **Sales** table, and then select the **Revenue YoY %** measure. Use tab and carriage return characters to produce the same result as the above example. When you add a carriage return, remember to press **Shift+Enter**.

This measure definition can still be improved for readability and performance. You'll see how in a later unit when we introduce variables.

> [!TIP]
> There's a great third-party formatting tool to help you format your calculations: [DAX Formatter](http://www.daxformatter.com/?azure-portal=true). The tool allows you to paste in your calculation and format it. It's then easy to copy the formatted calculation to your clipboard and paste it back into Power BI Desktop.