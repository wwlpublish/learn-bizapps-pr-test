Common Data Service for Apps is designed so that you can quickly and easily create a data model for your application based on the entities, and the entity metadata that you include in your app. 

Entities describe the kinds of data that is stored in the Common Data Service for Apps database. Each entity corresponds to a database table and each field (also known as an attribute) within an entity represents a column in that table. 

In Common Data Service for Apps, metadata (data about data), is a collection of entities. Entity metadata is what controls the kinds of records you can create and what kind of actions can be performed on them. When you use customization tools to create or edit entities, fields, and entity relationships, you are editing this metadata.

The apps that your customers use to interact with the data in your environment depend on the entity metadata and adapt as you customize the metadata. 

## When to use standard entities, and when to create new entities
Common Data Service for Apps comes with a number of standard entities that support core business application capabilities. Each entity also contains a number of metadata fields that represent common data that the system needs to store for that entity. We recommend that you become very familiar with the catalog of standard entities, and use them where possible, because any applications written with standard entities will work as you expect in your environment without additional effort.

You may not need to create a custom entity for minor changes: 

- You can edit an entity to change the display name of a field without creating a new entity
- You can’t delete standard entities, but you can hide them. If you want to hide a standard entity, change the security role privileges for your organization to remove the read privilege for that entity. This will remove the entity from most parts of the application.

If standard entities don't work for your business need, and can’t be edited to match your need, you should evaluate creating a new entity, field, or entity relationship. If a standard entity almost meets your business needs, you can use it as a basis for a new entity.

## Entity relationships
Entity relationships define the ways that entity records can be associated with records from other entities or the same entity. Entity relationships are metadata. They allow for queries to retrieve related data very efficiently. Use entity relationships to define formal relationships that define the entity or that most records can use. 

There are two types of entity relationships.

- One-to-many relationships. In a one-to-many entity relationship, many related entity records are associated with a single primary entity record in a parent/child relationship. 
- Many-to-many relationships. In a many-to-many entity relationship many entity records are associated with many other entity records. Records related using a many-to-many relationship are considered peers.

Beyond defining how records can be related to other records, 1:N entity relationships also provide data to address the following questions:
- When I delete a record should any records related to that record also be deleted?
- When I assign a record, do I also need to assign all records related to that record to the new owner?
- How can I streamline the data entry process when I create a new related record in the context of an existing record?
- How should people viewing a record be able to view the associated records?

## Entity types
Before creating or editing entities in Common Data Service for Apps, you should understand the different types of entities that you can create. After a custom entity is created, the entity type can't be changed. 

### Types of entity owners
 When you create a custom entity, the options for ownership are *User or team owned*, or *Organization-owned*. After an entity is created, you can’t change the ownership. 

- **User or team owned** Actions that can be performed on these records can be controlled on a user level.
- **Organization-owned** Access to the data is controlled at the organization level.

### Activity entities
An activity is an action for which an entry can be made on a calendar. An activity has:
- Time dimensions (start time, stop time, due date, and duration) that help determine when the action occurred or will occur.
- Data that helps determine what action the activity represents, for example, subject and description. 
- Can be opened, canceled, or completed. The completed status of an activity will have several sub-status values associated with it to clarify the way that the activity was completed. 
 
Activity entities can only be owned by a user or team, they can’t be owned by an organization.

The following default activity entities are available:

- **Appointment** Commitment representing a time interval with start/end times and duration.
- **Email** Activity that is delivered using email protocols.
- **Fax** Activity that tracks call outcome and number of pages for a fax and optionally stores an electronic copy of the document.
- **Letter** Activity that tracks the delivery of a letter. The activity can contain the electronic copy of the letter.
- **Phone Call** Activity to track a telephone call.
- **Recurring Appointment** The master appointment of a recurring appointment series.
- **Task** Generic activity representing work needed to be done.

### Custom activity entities
You can create new custom activity entities. Activity entities have metadata values that differ from other entities, such as Primary field set to Subject. 

You can't create a custom activity using the PowerApps portal. You must open the Solution explorer by using the Advanced button. 
