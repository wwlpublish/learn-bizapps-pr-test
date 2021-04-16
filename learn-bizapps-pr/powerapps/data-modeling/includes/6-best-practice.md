Data modeling is a science, and there are data modeling professionals and established standards for data modeling. To be effective with Dataverse data modeling, you do not have to be a professional data modeler or use any special tools. Popular tools like Microsoft Visio can be used to quickly create a basic Entity Relationship Diagram (ERD) that visualizes the relationships and flow of data between tables. In this unit, we will discuss some general best practices for data modeling for Dataverse deployments. Best practices to follow are:

- Data models should be updated continuously during a deployment. it is common for a data model to be designed at the beginning of a project, but it is important that it does not stop there. As you go through the deployment, new columns and tables will be added. it is important to capture these new columns and tables in the data model and make it a living data model. Recommend to customers that they continue to update it as they enhance the system.

- Do not start from scratch. Community tools available with the [XrmToolBox](https://www.xrmtoolbox.com) make it easy to quickly generate ERD diagrams of your Dataverse configuration. These tools include the UML Generator and Entity Relationship Diagram (ERD) Generator. After you complete configuration updates, generate an up-to-date ERD diagram.

- Do not include every table. Some core tables, such as activities, notes, and users (record owners) are related to nearly every table in Dataverse. If you include every relationship with these tables in your data model, the result will be unreadable. Best practice is to only include the primary tables used in your configuration in your data model diagram, and only include custom relationships with the user and activity tables to maximize readability.

- Data models should include tables outside of Dataverse. If you are integrating with other systems using Dataverse data connectors or virtual tables, or if data flows outside of Dataverse using an integration, this data should also be represented in your data model diagram.

- Start simple, with the standard tables, then add custom table relationships to your data model.

- Experience should influence your data model. Sometimes it is easy to over-normalize your data, but in the process you can make the application more cumbersome to use.

Start with what you need now, but design the data model in a way that will support what you are going to be doing in the future. For example, if you know that in the future you will need to store more details about sales territories, using a text column for territory now will make it more difficult to implement than if you use the territory table relationship. Plan ahead for what is coming.

## Out-of-the box vs. custom tables

In this topic, we identify standard, "out-of-the-box" (OOB) tables that are used in the configuration, along with custom tables and the purpose for which they are being used. This information matters because the Microsoft Dataverse has many common tables, and as a general rule, a custom table should not be created if a standard table already exists that addresses that purpose. The reason is that if you overload your configuration with many redundant tables, you will negatively impact the performance of the system, and you will make the system more difficult to use (many redundant sounding tables confuses users in advanced find). Each custom table should serve a specific purpose. This topic will also help identify what tables are the most used and identify if you are at risk of over-loading tables.

### Should you replace standard tables with custom tables?

Sometimes makers think they should replace standard functionality with custom tables. Makers reason that, for example, if they need a sales opportunity, but they need a simpler form than the standard opportunity form, that it might be easier. However, you should consider what you may be giving up by using a custom table, instead of a standard table. Using an out-of-the-box table ensures greater alignment with core platform features. Since more features are added regularly, using standard tables makes it easy to benefit from new features when they are released. For example, if you decided to replace the standard opportunity table with a custom opportunity table, you will not be able to use Sales Insights and other AI features.

### Accounts and contacts should never be recreated

When deploying Power Platform solutions, there are frequently multiple types of companies, organizations, and contacts that you will be tracking in the system. Some represent customer/client organizations, some may be support and advisory organizations, like accountants and legal firms, and some may be miscellaneous types of organizations, such as trade associations.

How should you manage multiple categories of company relationships? The most common approach is to use the account table for all organization types and use a column like relationship type or a custom option set to flag companies by their type or category. Views can be filtered based on the type of company, and business rules can conditionally show or hide column and form components based on type.

In order to benefit from a standard integration with Dynamics 365 Finance and Operations apps using Dual-Write, it is best to use the default tables and columns that are added by the Dual Write Core solution to your Dataverse environment.

Another approach is to create custom tables for each type of company. One reason commonly cited is "I might need to use accounts for another reason in the future, so I do not want to customize the account table."

Before recreating the account table as a custom company table, consider strongly what you are giving up by creating a custom table. Consider the following:

- Multiple addresses: Account has a unique address capability that supports multiple addresses. The first two addresses are displayed on the company form, but these address records live in the related customer address table. While you can create a custom address table tied to a custom company table, recreating the unique logic where the addresses are stored in the related table and displayed on the form and table views would require development. If you need multiple addresses, use the account table.
- Contact hierarchy: Accounts are the parent of contacts. Activities related to contacts roll up to the parent account record. This hierarchy cannot be replaced by a custom company record. You can create more relationships with custom company tables, but the standard account/contact relationship cannot be replaced. If the company has contacts with their primary company relationships to this type of company, or if you want to roll up activities from contacts to companies, use the account table.
- The standard map control in model-driven apps does not support custom company tables.
- Hierarchical relationships between parent/child accounts and the standard hierarchy visualization and roll-up of child account activities to parent account, only work with standard account tables.
- Dataverse includes a special type of polymorphic lookup column called a customer column. This column allows a row to be linked to a company/account or a contact. Dataverse does not allow for custom tables to be selected from polymorphic lookup columns.
- Marketing will not work. Marketing lists can only work with contacts, accounts, and leads, not custom tables. Dynamics 365 Marketing can send to accounts and contacts, but not custom company tables.

So, in almost every situation, the account table should be used for company records of all types. What are the exceptions?

- Minor types of companies that are not relational and have minimal attributes. Think of a type of organization with no contacts, address, and that only exists for lookup purposes.
- Unqualified or unverified companies imported from business cards or web forms that we do not want to pollute the account table. For these situations, you could use the lead table.

### Should you repurpose system tables for other purposes

Consider the scenario where you have a business requirement that is similar to opportunities, but not really a sales opportunity. Should you repurpose system tables or create new tables?

The following items should be considered before repurposing system tables:

#### Consider the future

The future of the Power Platform is moving much faster than ever before, so using tables in non-standard ways can cause problems if Microsoft makes changes to the table that you are using. Also, if you choose to repurpose a little used system table like contracts, there is a chance that Microsoft will elect to deprecate that table in the future. Custom tables do not get deprecated. Also, if you repurpose a system table, what will you do, if later, you need that entity for its intended purposes? There are customers who repurposed case, and later needed case management and had to address it with custom tables because the standard case table was already used for dramatically different purposes.

#### Consider the overhead

There are many system tables that have certain columns that cannot be removed from the forms. For example, some columns on tables like opportunity, case, and campaign cannot be removed from the form. While you can hide these columns, having a bunch of locked columns on the form can add overhead to your environment configuration.

#### Consider the user experience

If your use case is less than 50% inline with the standard table functionality, a custom table will typically give users a simpler user experience than scaling down a more complex system table. it is also possible to add business process flows to any table, including custom tables, which can easily make a custom table user experience as good as, or better than repurposing a system table.

## Avoiding common pitfalls

Below are common data modeling issues:

- Too many tables: Probably over normalized
- Too many columns on a table: Probably should have been a separate table.
- Use the tools: Quick view forms instead of repeating columns.
- Avoid Yes/No data type, if there might be more values, or you need to store as Unknown.
- You are stuck with data type formatting forever.
- Do not build out parts of the data model you don’t plan to use.

## Proof of Concept

 Dataverse makes it easy to create a trial environment and it is quick to create tables and relationships. You can build Proof of Concepts to try out your data model and see what the user experience might be like.
