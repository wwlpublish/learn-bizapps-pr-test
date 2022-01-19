Before we build the final *AccidentTable*, it is beneficial to understand the different type of relationships. As mentioned earlier in the module we will need to build the following relationships between our custom tables:

- There will be a one-to-many relationship from the location table (LocationTable) to our main accident table (AccidentTable)

- There will be a one-to-many relationship from the location table (TypeofAccidentTable) to our main accident table (AccidentTable)

- There will be a many-to-many relationship from the employee table (EmployeeTable) to our main accident table (AccidentTable)

We won't go into all the details about relationship in this module, for more detailed information please refer to this link [Dataverse Relationships](/powerapps/maker/data-platform/relationships-overview).

The goal is to understand why the relationships above apply to our business case and are correctly associated.

In our business case, we know that each accident (being tracked in the *AccidentTable)* can occur in a particular location (being tracked in the *LocationTable)* so in this case an accident can occur many times in a single location. Sometimes it is easier to think of the *LocationTable* as the parent and the rows of the referencing table as the children, in this case the *AccidentTable.*

The same logic applies to the relationship between *TypeofAccidentTable* and the *AccidentTable.* Many accidents can occur with just one type of accident. The *TypeofAccident* is the parent and the rows in the *AccidentTable* is the children. It is important to note that a many-to-one relationship is the child perspective of a one-to-many relationship. To create these relationships, we will create **Lookup** data type columns in the next exercise.

The relationship between our *EmployeeTable* and *AccidentTable* is of the many-to-many relationship type. This is because one employee can be involved in many accidents and one accident record can involve more than one employee. The rows of many-to-many relationships are identical and reciprocal. **Dataverse** creates a third table not visible in the tables list to build the relationship. This table holds a one-to-many relationship with both related tables and just stores the values to define the relationship. In many-to-many relationships, there are no explicit columns being created, the relationship is created by selecting the two tables that you want to create the relationship for.

In the next exercise the answer to how to create the relationships will become clear.
