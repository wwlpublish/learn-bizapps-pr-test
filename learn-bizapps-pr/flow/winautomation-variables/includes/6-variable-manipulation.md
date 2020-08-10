When you create a variable, the name must be enclosed by percentage signs (**%**). The percentage sign is used as a special character to denote variables. Any expression that you have added between percentage signs should be evaluated.

In some cases, the percentage sign should be used as a simple character, instead of denoting a calculation. In those cases, it should be escaped using the backslash (**\\**).

WinAutomation enables you to create complex expressions containing hardcoded values, variable names, arithmetic operations, comparisons, logical operations, and parentheses.

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-expression.png)

**Hardcoded values**

To include a hardcoded text value inside a variable, you can use quotes. Every value between the quote characters will be treated as a text value and not as a variable Name.

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-hardcoded-values.png)

**Variable names**

Variables can be used by adding their name to the expression without any further notation.

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-variable-names.png)

**Basic arithmetic**

To perform mathematical operations, you can use all the essential, arithmetic operators, such as addition (**+**), subtraction (**-**), multiplication (**\***), and division (**/**).

Arithmetic operations are designed to be used with numerical values and variables. However, the addition operator can also be used between text strings to concatenate them. Adding numbers and text strings in the same expression will convert the numbers into text, and concatenate them with the other text strings.

| Expression                  | Result                                              |
|-----------------------------|-----------------------------------------------------|
| %5 * 3%                     | 15 (number)                                         |
| %4 / Var%                   | 4 divided by the value of the Variable named “Var”  |
| %"this is " + "text"%       | this is text (text)                                 |
| %"This is the number " + 5% | This is the number 5 (text)                         |

**Comparisons**

Besides arithmetic operators, WinAutomation allows you to perform comparisons using the following operators

| Operator | Description                        |
|--------- |------------------------------------|
| ==, !=   | Equal/not equal                    |
| <, <=    | Less than/less than or equal       |
| >, >=    | Greater than/greater than or equal |

Keep in mind that comparisons, when evaluated, produce either **True** or **False** as a value. Naturally, comparisons can only be performed between values of the same type.

**Logical operators**

Logical operators can also be used to check multiple conditions simultaneously, allowing you to implement more complex logic in a single expression. The supported operators are: AND (**&&**), the OR (**||**) and the NOT (**!**). 

| Expression                     | Result                                                                                      |
|--------------------------------|---------------------------------------------------------------------------------------------|
| %Index == 1 || Index == 2%     | True if the value of the **Index** variable is 1 OR 2, otherwise False                          |
| %Index == 4 && Text == "Four"% | True if the value of the **Index** variable is 4 AND the value of the **Text** variable is Four, otherwise False |
| %!ConditionIsTrue%             | True if the value of the **ConditionIsTrue** variable is False, otherwise False                 |

**Parentheses**

If you want to change the operators' priority, you can use parentheses. parentheses are handled the same way as in algebra and programming languages.

![The populated Set Value field in the Set Variable action's properties dialog.](..\media\set-variable-action-properties-parenthesses.png)