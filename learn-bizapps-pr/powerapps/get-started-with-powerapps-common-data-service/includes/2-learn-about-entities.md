Common Data Service is designed to let you quickly and easily create a data model for your application, based on the entities and the entity metadata that you include in your app. 

Entities describe the kinds of data that is stored in the Common Data Service database. Each entity corresponds to a database table and each field (also known as an attribute) within an entity represents a column in that table. 

In Common Data Service, metadata (data about data), is a collection of entities. Entity metadata is what controls the kinds of records you can create and what kind of actions can be performed on them. When you use customization tools to create or edit entities, fields, and entity relationships, you are editing this metadata.

The apps that your customers use to interact with the data in your environment depend on the entity metadata, and they adapt as you customize the metadata. 

## When to use standard entities, and when to create new entities
Common Data Service comes with a number of standard entities that support core business application capabilities. Each entity also contains a number of metadata fields that represent common data that the system needs to store for that entity. We recommend that you become very familiar with the catalog of standard entities, and use them where possible, because any applications written with standard entities will work as you expect in your environment without additional effort.

For minor changes, you might not have to create a custom entity: 

- To change the display name of a field, you can edit the entity. You don't have to create a new entity.
- You can't delete standard entities, but you can hide them. To hide a standard entity, change the security role privileges for your organization to remove the Read privilege for that entity. This will remove the entity from most parts of the application.

If standard entities don't work for your business needs, and if they can't be edited to meet those needs, consider creating a new entity, field, or entity relationship. If a standard entity almost meets your business needs, you can use it as the basis for a new entity.

## Entity relationships
Entity relationships define the different ways entity records can be associated with records from other entities or the same entity. Entity relationships are metadata. They let queries retrieve related data very efficiently. Use entity relationships to define the formal relationships that define the entity or that most records can use. 

When you look at the solution explorer you might think that there are three types of entity relationships but actually there are only two, see below:

- **One-to-many relationships**: In a one-to-many (1:N) entity relationship, many related entity records are associated with a single primary entity record in a parent/child relationship. 
- **Many-to-many relationships**: In a many-to-many (N:N) entity relationship, many entity records are associated with many other entity records. Records that are related through N:N entity relationships are considered peers.

The N:1 (many-to-one) relationship type exists in the user interface because the designer shows you a view grouped by entities. 1:N relationships actually exist between entities and refer to each entity as either a Primary/Current Entity or Related Entity. The related entity, sometimes called the child entity, has a lookup field that allows storing a reference to a record from the primary entity, sometimes called the parent entity. A N:1 relationship is just a 1:N relationship viewed from the related entity.

Besides defining how records can be related to other records, 1:N entity relationships also provide data to address the following questions:

- When I delete a record, should any records that are related to that record also be deleted?
- When I assign a record to a new owner, do I also have to assign all related records to the new owner?
- How can I streamline the data entry process when I create a new related record in the context of an existing record?
- How should people who view a record be able to view the related records?

## Entity types
Before creating or editing entities in Common Data Service, you should understand the different types of entities that you can create. After a custom entity is created, the entity type can't be changed. 

### Types of entity owners
 When you create a custom entity, the options for ownership are *User or team owned*, or *Organization-owned*. After an entity is created, you can’t change the ownership. 

- **User or team owned**: Actions that can be performed on these records can be controlled at the user level.
- **Organization-owned**: Access to the data is controlled at the organization level.

### Activity entities
An *activity* is an action that a calendar entry can be made for. Activities have these characteristics:

- They have time dimensions (start time, stop time, due date, and duration) that help define when the action occurred or will occur.
- They have data (like a subject and description) that helps define the action that the activity represents. 
- They can be opened, canceled, or completed. Several sub-status values will be associated with the *Completed* status of an activity to clarify how the activity was completed. 
 
Activity entities can be owned only by a user or team. They can't be owned by an organization.

The following default activity entities are available:

- **Appointment**: A commitment representing a time interval that has start/end times and duration.
- **Email**: An activity that's delivered by using email protocols.
- **Fax**: An activity that tracks the call outcome and number of pages for a fax. The activity can optionally store an electronic copy of the document.
- **Letter**: An activity that tracks the delivery of a letter. The activity can store an electronic copy of the letter.
- **Phone Call**: An activity that tracks a telephone call.
- **Recurring Appointment**: The master appointment of a recurring appointment series.
- **Task**: A generic activity representing work that must be done.

### Custom activity entities
You can create new custom activity entities. The metadata values of activity entities differ from the metadata values of other entities. For example, the **Primary** field is set to **Subject**. 

## Business Rules

Business rules provide a simple interface to implement and maintain fast-changing and commonly used rules. The business rules defined for an entity apply to both canvas apps and model-driven apps if the entity is used in the app.
 
By combining conditions and actions, you can do any of the following with business rules:
- Set field values
- Clear field values
- Set field requirement levels
- Show or hide fields
- Enable or disable fields
- Validate data and show error messages
- Create business recommendations based on business intelligence.

## Differences between canvas and model-driven apps

Model-driven apps can use all actions available on business rules, however not all business rule actions are available for canvas apps at this time. The following actions are not available on Canvas apps:
- Show or hide fields
- Enable or disable fields
- Create business recommendations based on business intelligence.
