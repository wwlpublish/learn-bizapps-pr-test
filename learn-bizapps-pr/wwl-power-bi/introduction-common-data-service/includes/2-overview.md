Microsoft Dataverse is a cloud-based solution that easily structures a variety of data and business logic to support interconnected applications and processes in a secure and compliant manner. Managed and maintained by Microsoft, Dataverse is available globally but deployed geographically to comply with your potential data residency. It is not designed for stand-alone use on your servers, so you will need an internet connection to access and use it. 

Dataverse is designed to be your central data repository for business data, and you might even be using it already. Behind the scenes, it powers many Microsoft Dynamics 365 solutions such as Field Service, Marketing, Customer Service, and Sales. It is also available as part of Power Apps and Power Automate with native connectivity built right in. The AI Builder and Portals features of Microsoft Power Platform also utilize Dataverse.

Below is a visualization that brings together the many offerings of Microsoft Dataverse.
 
![Dataverse API options](../media/common-data-service-diagram.png)

As you can see, Microsoft Dataverse offers a great deal of functionality. Below is a brief explanation of each category of features.

**Security**: Dataverse handles authentication with Azure Active Directory (Azure AD) to allow for conditional access and multi-factor authentication. It supports authorization down to the row and column level and provides rich auditing capabilities. 

**Logic**: Dataverse allows you to easily apply business logic at the data level. Regardless of how a user is interacting with the data, the same rules apply. These rules could be related to duplicate detection, business rules, workflows, or more.

**Data**: Dataverse offers you the control to shape your data, allowing you to discover, model, validate, and report on your data. This control ensures your data looks the way you want regardless of how it is used.

**Storage**: Dataverse stores your physical data in the Azure cloud. This cloud-based storage removes the burden of worrying about where your data lives or how it scales. These concerns are all handled for you.

**Integration**: Dataverse connects in different ways to support your business needs. APIs, webhooks, eventing, and data exports give you flexibility to get data in and out.

As you can see, Microsoft Dataverse is a very powerful cloud-based solution for storing and working with your business data. In the following sections, you will look at Microsoft Dataverse from the lens of data storage for Microsoft Power Platform, where you will start your journey. Keep in mind the additional rich capabilities discussed above which you can explore further as your usage increases. 

To get started, Microsoft Dataverse lets you create one or many cloud-based instances of a standardized database. The database includes predefined tables and columns which store data commonly found across nearly all organizations and businesses. You can customize and extend what is stored by adding new columns or tables. The ease of setting up a Microsoft Dataverse database and standardized data model under it simplifies your ability to concentrate your efforts on building solutions without worrying about infrastructure, storage, and data integration.
With your data stored in Microsoft Dataverse, there are many different ways to access it. You can work with the data natively with tools such as Power Apps or Power Automate. Or through connectors and APIs you can connect to Microsoft Dataverse from any business solution. With the power of features such as role-based security and business rules you can trust your data is safe no matter how it is accessed. 

## Microsoft Dataverse defined

A Dataverse database is a single instance of Microsoft Dataverse which stores data in a set of standard and custom data structures called tables. A table is a logical set of rows that is used to store data. Rows within a table contain many columns to manage individual pieces of information about a single row.

You can create one or many database instances in Microsoft Dataverse to host data behind your business solutions. Each instance of a Microsoft Dataverse will start with the same set of tables to store data, but you can always extend and customize a Microsoft Dataverse database to meet specific business needs. This means that you can share business solutions that reference standard tables in Microsoft Dataverse across your organization or with any other organization by using it anywhere in the world.

## Scalability

A Dataverse database supports large data sets and complex data models. Tables can hold millions of items, and you can extend the storage in each instance of a Microsoft Dataverse database to four (4) terabytes per instance. The amount of data that is available in your instance of Microsoft Dataverse is based upon the number and type of licenses that are associated with it. Data storage is pooled between all licensed users, so you can allocate storage as needed for each solution that you build. Additional storage can be purchased if you need more storage than what is offered within standard licensing. 

> [!TIP]
> Dataverse supports transactional multi-user applications, where quick response to user demand is the priority. It is not intended to be a platform for long running or batch processing.

## Common Data Model vs. Microsoft Dataverse

The standard table design in a Microsoft Dataverse database is based upon an open data model standard called Common Data Model. Common Data Model is a logical design that includes a set of open-sourced, standardized, extensible data tables and relationships that Microsoft and its partners have published in an industry-wide initiative called the Open Data Initiative. This collection of predefined tables, columns, semantic metadata, and relationships form the basis of the Common Data Model.

## Microsoft Dataverse structure and benefits

The structure of a Microsoft Dataverse database is based upon the definitions and schema in the Common Data Model. The key benefit of using Common Data Model as the basis of a Microsoft Dataverse database is simplified integration of any solutions that use a Common Data Model schema, because the standard tables of the solution are the same. You will also be able to take advantage of a rich ecosystem of solutions that vendors have built from using Common Data Model. Best of all, there is practically no limit to how far you can extend a Microsoft Dataverse database.