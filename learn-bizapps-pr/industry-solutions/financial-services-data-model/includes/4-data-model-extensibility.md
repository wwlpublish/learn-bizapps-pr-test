The Financial Services Industry Model is key to interoperability and data unification. It's core to how customers and Microsoft partners can speed up the roll out of Banking solutions. An often-addressed subject is the key extensibility capabilities and patterns of the Industry Data model.

The following are the extensibility factors:

- Cloud for FSI is a managed solution. The data model extensions are tightly controlled to allow for future compatibility and the data model continually expands based on customer feedback. Currently, the Tables are locked and don't allow for addition of fields, by design.

- However, the following patterns of extension are valid:

  - Option sets are extensible in multiple Tables, such as Life Events, Financial Holding Types, and Loan Types.

  - The model doesn't prevent addition of Tables and they're a workable option.

The known limitations are as below:

- The industry data model has several lookups as polymorphic relationships, example in Groups Table. There are no constraints to prevent customers from extending polymorphic relationships, however this might affect upgradability and isn't recommended.

- The Microsoft Financial Services Accelerator is getting deprecated. We recommend that customers migrate to Microsoft Cloud for Financial Services.

- The data model that was in Preview isn't upgradable to the Generally Available version.
