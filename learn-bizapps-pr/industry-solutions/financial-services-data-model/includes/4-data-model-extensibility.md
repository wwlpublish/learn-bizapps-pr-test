The Financial Services industry model is key to interoperability and data unification. It's fundamental to how customers and Microsoft partners can accelerate the rollout of banking solutions. An often-addressed subject is the key extensibility capabilities and patterns of the industry data model.

The extensibility factors are:

- Cloud for Financial Services is a managed solution. The data model extensions are tightly controlled to allow for future compatibility. The data model continually expands based on customer feedback. By design, the tables are locked and don't allow for the addition of fields.

- The following patterns of extension are valid:

  - Option sets are extensible in multiple tables, such as life events, financial holding types, and loan types.

  - The model doesn't prevent the addition of tables and it's a workable option.

The known limitations are:

- The industry data model has several lookups as polymorphic relationships, such as in the Groups table. No constraints are in place to prevent customers from extending polymorphic relationships; however, this factor might affect upgradability and isn't recommended.

- Microsoft Financial Services accelerator is being deprecated. We recommend that customers migrate to Microsoft Cloud for Financial Services.

- The data model that was in preview isn't upgradable to the generally available version.
