The DAX function library comprises hundreds of functions, each designed to accomplish a specific goal.

Because DAX originated with the PowerPivot add-in for Microsoft Excel 2010, there are over 80 functions that can also be found in Excel. It was a deliberate design strategy by Microsoft to ensure Excel users can quickly become productive with DAX.

Yet, there are many functions that you won't find in Excel, because they're specific to data modeling. They include:

-   Relationship navigation functions

-   Filter context modification functions

-   Iterator functions

-   Time intelligence functions

-   Path functions

> [!TIP]
> To search for documentation related to a DAX function, in a web search simply enter the keyword **DAX** followed by the function name.

For more information about DAX functions, see the [DAX function reference](https://docs.microsoft.com/dax/dax-function-reference/?azure-portal=true).

### Functions originating from Excel

Let's now consider several useful functions that you might already be familiar with---because they exist in Excel.

The [IF](https://docs.microsoft.com/dax/if-function-dax/?azure-portal=true) DAX function tests whether a condition provided as the first argument is met. It returns one value if the condition is TRUE, and returns the other value if the condition is FALSE. It's syntax is:

```dax
IF(<logical_test>,<value_if_true>[, <value_if_false>])
```

> [!TIP]
> A function argument is optional when documentation shows it enclosed within square brackets.

If **logical_test** evaluates to FALSE and **value_if_false** isn't provided, the function will return BLANK.

Many Excel summarization functions are available. They include: SUM, COUNT, AVERAGE, MIN, MAX, and many others. The only difference is that in DAX you pass in a column reference, whereas in Excel you pass in a range of cells.

Many Excel mathematic, text, date and time, information, and logical functions are available, too. For example, here's a small sample of Excel functions available in DAX: ABS, ROUND, SQRT, LEN, LEFT, RIGHT, UPPER, DATE, YEAR, MONTH, NOW, ISNUMBER, TRUE, FALSE, AND, OR, NOT, and IFERROR.

### Functions not originating from Excel

Let's now consider two useful functions that aren't specific to modeling, and that don't originate from Excel.

#### DISTINCTCOUNT function

You can use the [DISTINCTCOUNT](https://docs.microsoft.com/dax/distinctcount-function-dax/?azure-portal=true) DAX function to count the number of distinct values in a column. It's especially powerful in an analytics solution. Consider that the count of customers is very different from the count of *distinct* customers. The latter doesn't count repeat customers, so the difference is really "How many customers" compared with "How many *different* customers".

#### DIVIDE function

You can use the [DIVIDE](https://docs.microsoft.com/dax/divide-function-dax/?azure-portal=true) DAX function to achieve division. You must pass in numerator and denominator expressions. Optionally, you can pass in a value that represents an *alternate result*. It's syntax is:

```dax
DIVIDE(<numerator>, <denominator> [,<alternateresult>])
```

The DIVIDE function was designed to automatically handle division by zero cases. If an alternate result isn't passed in, and the denominator is zero or BLANK, the function returns BLANK. When an alternate result is passed in, it's returned instead of BLANK.

This function is convenient because it saves your expression from having to first test the denominator value. The function is also better optimized for testing the denominator value than the IF function. The performance gain is significant since checking for division by zero is expensive. What's more, using DIVIDE results in a more concise and elegant expression.

We recommend you use the DIVIDE function whenever the denominator is an expression that could return zero or BLANK. In the case that the denominator is a constant value, we recommend that you use the divide operator (/), which we'll introduce in the next unit. In this case, the division is guaranteed to succeed, and your expression will perform better because it'll avoid unnecessary testing.
