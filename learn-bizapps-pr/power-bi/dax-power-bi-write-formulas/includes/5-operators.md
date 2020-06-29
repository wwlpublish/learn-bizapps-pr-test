Your DAX formulas can use **DAX operators** to create expressions that perform arithmetic calculations, compare values, work with strings, or test conditions.

> [!TIP]
> Many DAX operators and precedence order are the same as those found in Excel.

### Arithmetic operators

The following table lists the arithmetic operators.

|     Operator    |     Description       |
|-----------------|-----------------------|
|     +           |     Addition          |
|     -           |     Subtraction       |
|     *           |     Multiplication    |
|     /           |     Division          |
|     ^           |     Exponentiation    |

Remember, when dividing two expressions and when the denominator could return zero or BLANK, it's more efficient and safer to use the [DIVIDE](https://docs.microsoft.com/dax/divide-function-dax) DAX function.

### Comparison operators

The following table lists the comparison operators, which are used to compare two values. The result is either TRUE or FALSE.

|     Operator    |     Description                   |
|-----------------|-----------------------------------|
|     =           |     Equal to                      |
|     ==          |     Strict   equal to             |
|     >           |     Greater than                  |
|     <           |     Less than                     |
|     >=          |     Greater than or equal   to    |
|     <=          |     Less than   or equal to       |
|     <>          |     Not equal to                  |

All comparison operators, except ==, treat BLANK as equal to the number zero, an empty string (""), the date December 30, 1899, or FALSE. It means the expression `[Revenue] = 0` will be TRUE when the value of [Revenue] is either zero or BLANK. In contrast, `[Revenue] == 0` is TRUE only when the value of [Revenue] is zero.

### Text concatenation operator

Use the ampersand (&) character to connect---or concatenate---two text values to produce one continuous text value. For example, consider the following calculated column definition:

```dax
Model Color = Product[Model] & "-" & Product[Color]
```

### Logical operators

Use logical operators to combine expressions that produce a single result. The following table lists all logical operators.

|     Operator              |     Description                                                                                                                                                                                                                |
|---------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|     &&                    |     Creates an AND   condition between two expressions that each have a Boolean result. If both   expressions return TRUE, the combination of the expressions also returns   TRUE; otherwise the combination returns FALSE.    |
|     \|\| (double pipe)    |     Creates an   OR condition between two logical expressions. If either expression returns   TRUE, the result is TRUE; only when both expressions are FALSE is the result   FALSE.                                            |
|     IN                    |     Creates a logical OR condition   between each row being compared to a table. Note: the table constructor   syntax uses curly braces.                                                                                       |
|     NOT                   |     Inverts   the state of a Boolean expression (FALSE to TRUE, and vice versa).                                                                                                                                               |

Here's an example which uses the IN logical operator: The **ANZ Revenue** measure definition uses the [CALCULATE](https://docs.microsoft.com/dax/calculate-function-dax) DAX function to enforce a specific filter of two countries: Australia and New Zealand.

> [!NOTE]
> We'll introduce you to the powerful CALCULATE function when you learn how to modify the filter context.

```dax
ANZ Revenue =
CALCULATE(
	[Revenue],
	Customer[Country-Region]
		IN {
		"Australia",
		"New Zealand"
	}
)
```

### Operator precedence

When your DAX formula includes multiple operators, DAX uses rules to determine the evaluation order. It's known an *operator precedence*. Operations are ordered according to the following table.

|     Operator             |     Description                               |
|--------------------------|-----------------------------------------------|
|     ^                    |     Exponentiation                            |
|     -                    |     Sign (as   in -1)                         |
|     * and /              |     Multiplication and   division             |
|     NOT                  |     NOT                                       |
|     + and -              |     Addition and   subtraction                |
|     &                    |     Concatenation   of two strings of text    |
|     =,==,<,>,<=,>=,<>    |     Comparison                                |

When the operators have equal precedence value, they are ordered from left to right.

In general, operator precedence is the same as you'll find in Excel. If you need to override the evaluation order, then group operations within parentheses.

For example, consider the following calculated column definition:

```dax
Extended Amount = Sales[Order Quantity] * Sales[Unit Price] * 1 - [Unit Price Discount Pct]
```

This example calculated column definition produces an incorrect result because multiplication happens before the subtraction. The following correct calculated column definition uses parentheses to ensure the subtractions happens before the multiplications.

```dax
Extended Amount = Sales[Order Quantity] * Sales[Unit Price] * (1 - [Unit Price Discount Pct])
```

> [!TIP]
> Remembering operator precedence rules can be challenging, especially for DAX beginners. So, we recommend you take time to test your formulas thoroughly. When they don't produce the correct result due to an incorrect evaluation order, just experiment by adding parentheses to adjust the evaluation order. You can also add parentheses to improve the readability of your formulas.

For more information about DAX operators and precedence order, see [DAX operators](https://docs.microsoft.com/dax/dax-operator-reference).

### Implicit conversion

When writing a DAX formula that uses operators to combines different data types, you don't need to explicitly convert types. Usually, DAX automatically identifies the data types of referenced model objects and performs implicit conversions where necessary to complete the specified operation.

However, there are some limitations on the values that can be successfully converted. If a value or a column has a data type that's incompatible with the current operation, DAX returns an error. For example, the attempt to multiply a date value will create an error because it isn't logical.

Beware that BLANK is handled differently depending on the operator used. It's handled similar to how Excel treats blank, but very differently to how databases (SQL) treats NULL. BLANK is treated as zero when acted on by arithmetic operators and as an empty string when concatenated to a string.

> [!TIP]
> Remembering how BLANK is handled can be challenging, especially for DAX beginners. So, we recommend you take time to test your formulas thoroughly. When BLANKs create unexpected results, consider using the [IF](https://docs.microsoft.com/dax/if-function-dax) and [ISBLANK](https://docs.microsoft.com/dax/isblank-function-dax) DAX functions to test for BLANK, and then respond in an appropriate way.

