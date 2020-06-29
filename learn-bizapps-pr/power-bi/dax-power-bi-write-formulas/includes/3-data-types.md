Data model columns have a set data type, which ensures all column values conform to that data type. Column data types are defined in Power Query, or in the case of calculated columns it's inferred from the formula. Measure data types, liked calculated column data types, are inferred from the formula.

Model data types aren't the same as DAX data types, although there's a direct relationship between them. Model data types and DAX data types are listed in the following table. Notice the supported range of values for each data type.

|     Model data type    |     DAX data type     |     Description                                                                                                                                  |
|------------------------|-----------------------|--------------------------------------------------------------------------------------------------------------------------------------------------|
|     Whole number       |     64-bit integer    |     -263 through 263-1                                                                                                                           |
|     Decimal number     |     64-bit   real     |     Negative: -1.79 x 10308 through -2.23 x 10-308     Zero     Positive: 2.23 x 10-308 through 1.79 x 10308     Limited to 17 decimal digits    |
|     Boolean            |     Boolean           |     TRUE or FALSE                                                                                                                                |
|     Text               |     String            |     Unicode character string                                                                                                                     |
|     Date               |     Date/time         |     Valid dates are all   dates after March 1, 1900                                                                                              |
|     Currency           |     Currency          |     -9.22 x   1014 through 9.22 x 1014    Limited to four decimal digits of fixed precision                                                      |
|     N/A                |     BLANK             |     In some cases, it’s the equivalent of a database (SQL) NULL                                                                                  |

## BLANK data type

The BLANK data type deserves a special mention: DAX uses BLANK for both database NULL and for blank cells in Excel. BLANK doesn't mean zero. Perhaps it's easier to think of it as the "absence of a value".

There are two DAX functions related to BLANK: The [BLANK](https://docs.microsoft.com/dax/blank-function-dax/?azure-portal=true) DAX function returns BLANK, while the [ISBLANK](https://docs.microsoft.com/dax/isblank-function-dax/?azure-portal=true) DAX function tests whether an expression evaluates to BLANK.
