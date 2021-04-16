Data modeling on the Power Platform looks at the whole data architecture picture and includes a logical look at data from Dataverse, Data Lakes, and external sources using connectors.

There are multiple types and standards for data modeling, including Unified Modeling Language (UML), IDEF1X, and others. Specific data model standards are beyond the scope of this unit, but data models for Dataverse data structures generally fall into two general categories:

- Logical Data Models
- Physical Data Models.

## Entity Relationship Diagrams (ERDs)

Logical data models are high-level diagrams that show how data flows through the system. Logical data models are frequently put together at the beginning of the project during discovery and before all of the columns have been defined. Generally, the logical data model diagram uses the business names of the entities, not the schema names.

Logical data model diagrams depict the flow of data in a solution without worrying about the physical implementation.

![Diagram of a logic data model for customers.](../media/3-logical-c.png)

Physical data models are lower level than logical data models. They generally include column-level detail and more precisely design relationships. The physical data model is created when the high-level logical design is translated to physical entities.

Physical data model diagrams should include showing Dataverse, Data Lake, Connector, or other data store boundaries.

![Diagarm of physical data model with tables and columns.](../media/3-physical-c.png)

You can also create object diagrams. Object diagrams really show you what you want to know and more importantly what you do not. Object diagrams need to be done in modeling sessions with domain experts.

![Depiction of an object diagram showing relationships.](../media/3-object-diagram.png)

## Data modeling strategies

The following are guidance to building a data model:

- **Start with core tables and relationships**: Too often teams get sidetracked with the whole problem it is a lot easier to solve small parts of the challenge and then look at it holistically later.
- **Over normalization**: Teams that have people with a strong data architect background tend to try to build a Dataverse data model like they would a traditional SQL Server database. This can lead to poor user experience and requirements for extra processing. The solution architect will need to work with such people to see the cause and effect of relationships in the user experience to help them understand the goal.
- **Needs today**: Dataverse is great at being incrementally built using an agile process, but having some insight into the short and long-term future helps lay the foundation. Just do not get stuck trying to identify every future requirement you can think of.
- **Proof of concepts**: Dataverse makes it easy to create an environment, try a model, throw it away and try again. Sometimes even challenging two teams with the same data modeling problem can produce useful results.

## Data model influencers

The data model can be influenced by a series of factors:

- **Security requirements**: The solution architect should always push for simplification, but these can drive requirements onto the data model.
- **User experience**: It is easy to forget that as we add normalization and relationships we create new constructs users need to navigate in the apps.
- **Data location and retention**: Not all data is allowed to be stored. Often data from services cannot be cached and companies have internal policies that govern use of data. Some data is protected by government laws or may have specific requirements for storage, for example, identifiable information, credit card numbers etc.
- **Self-service reporting**: If it takes a data architect to navigate the data model, the chances are many of the tools from Power BI and Export to Excel will be less valuable to the user. Most self-service features of Dataverse allow navigation of one level of relationship.
- **Existing systems**: Are these legacy systems? Is there an API? How can the data be accessed? Can it be copied?
- **Localization**: Is there multi-region, multi-lingual, or multi-currency requirements?
