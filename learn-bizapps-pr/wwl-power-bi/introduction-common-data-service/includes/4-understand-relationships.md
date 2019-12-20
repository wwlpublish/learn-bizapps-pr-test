To make an efficient and scalable solution for most of the solutions that you build, you will need to split up data into different containers (entities). Trying to store everything into a single container would likely be inefficient and difficult to work with and understand.

The following example helps illustrate this concept.

Imagine that you need to create a system to manage sales orders. You will need a product list along with the inventory on hand, cost of the item, and the selling price. You also need a master list of customers with their addresses and credit ratings. Finally, you will need to manage invoices of sales that you make so you will want a way to store invoice data. The invoice should include information such as date, invoice number, and salesperson, customer information including address and credit rating, and a line item for each item on the invoice. Line items should include a reference to the product that you sold and be able to provide the proper cost and price for each product and decrease the quantity on hand based upon the quantity that you sold in that line item.

Trying to create a single entity to support the functionality that was previously described would be inefficient. A better way to approach this business scenario is to create the following four entities:

- Customers

- Products

- Invoices

- Line Items

Creating an entity for each of these items and relating them to one another will allow you to build an efficient solution that can scale while maintaining high performance. Splitting the data into multiple entities also means that you will not have to store repetitive data or support huge records with large amounts of blank data. Additionally, reporting will be much easier if you split the data into separate entities.

Entities that relate to one another have a relational connection. Relationships between entities exist in many forms, but the two most common are one-to-many and many-to-many, both of which are supported by Common Data Service.

One-to-many relationships are also known as parent-child relationships. In the previous invoice example, the invoice entity would be the parent and the line items would be a child entity. An invoice can have zero, one, or many line items (child records), but the line item will always be related to just one invoice (parent record). Typically, the child records will not exist without a parent record.

A field that only allows unique values, such as invoice number, is used to identify the parent record. This unique field is called a key. The same value (the parent key) is stored in the related child records. This field is called a foreign key when the child record is used to store the parent key value. Ingeniously, filtering is used to display child records with a value in the foreign key that matches the key value in the parent record. This allows applications to display the child records (line items in the previous example) that belong to a particular parent record (invoice in the previous example). This concept underlies many business software applications.

Splitting data into different entities makes for an efficient solution design that can scale, but knowing how to split up the data into entities can be difficult. Thankfully, Common Data Service already contains many of the entities that most organizations will need. Using standard entities and extending them will ensure that you are building solutions around a proven, scalable way of storing the data that is used by your solutions.
