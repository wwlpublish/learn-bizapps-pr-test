In Microsoft Dataverse you can define business rules. Business rules allow you
to apply and maintain business logic at the data layer instead of the app layer.
Put more simply, if you create business rules in Microsoft Dataverse, they are
in effect regardless of where you interact with the data.

For example, business rules can be used in canvas and model-driven apps to set
or clear values in one or many columns in a table. They can also be used to
validate stored data or show error messages. Model-driven apps can use business
rules to show or hide columns, enable or disable columns, and create
recommendations based on business intelligence.

> [!TIP] 
> Business rules are usually defined for a table and apply to all
forms, but you can define a business rule for a specific model-driven form.
Canvas apps cannot have a business rule applied to a specific form, but they
are still enforced when interacting with the data.

Business rules give you a powerful way to enforce rules, set values, or validate
data regardless of the form that is used to input data. Additionally, business
rules are effective in helping to increase the accuracy of data, simplify
application development, and streamline the forms presented to end users.

The following business rule actions can be used by canvas and model-driven apps:

-   Set column values

-   Clear column values

-   Validate data and show error messages

Model-driven apps can also use business rules to:

-   Show or hide columns (model-driven apps only)

-   Enable or disable columns (model-driven apps only)

-   Create business recommendations based on business intelligence (model-driven
    apps only)

Below is an example of a simple, yet powerful use of business rules. The
business rule is configured to change the field Credit Limit VP Approver to be a
required field if the Credit Limit is set to greater than $1,000,000. If the
credit limit is less than $1,000,000 then the field is optional.

![Example of business-rule](../media/business-rule.png)

By applying this business rule at the data level instead of the app level, you
have better control of your data. This can ensure your business logic is
followed whether it is being accessed directly from Power Apps, Power Automate,
or even via an API. The rule is tied to the data, not the app.
