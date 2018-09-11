Common Data Service (CDS) for Apps lets you securely store and manage data that's used by business applications. 

## Entities
In CDS for Apps, data is stored in a set of records called entities. An *entity* is a set of records that's used to store data, similar to how a table stores data in a database.

CDS for Apps includes a base set of standard entities that support common business scenarios that connect to Microsoft Dynamics 365 application data. You can also create custom entities that are specific to your organization, and populate them with data that you import from lists in Microsoft SharePoint, from Microsoft Excel, or from Microsoft Power Query for Excel. App makers can then use Microsoft PowerApps to build rich applications that use this data.

![Illustration showing an overview of the Business Application Platform](../media/platform.png)

Dynamics 365 applications, including Dynamics 365 for Sales, Dynamics 365 for Service, and Dynamics 365 for Talent, use CDS for Apps to store and help secure the data they use. This means you can use PowerApps and CDS for Apps to build apps directly against core business data that's already used in Dynamics 365, without having to do manual integration.

> [!NOTE]
> Dynamics 365 for Finance and Operations and Dynamics 365 for Retail currently require you to set up the Data Integrator to make your business data available in CDS for Apps.

![Screenshot showing a list of entities](../media/entitylist.png "Entity list")

For most organizations, it's a good idea to use the standard entities and attributes as they were intended. But to meet your business needs, you can extend the functionality of standard entities by creating one or more custom entities to store information that's unique to your organization. 

## Logic and validation
Entities in CDS for Apps can take advantage of rich server-side logic and validation to ensure data quality. You can also reduce repetitive code in each app that creates and uses data in an entity.

* **Business rules**: Business rules validate data across multiple fields and entities, and provide warning and error messages, regardless of the app that's used to create the data. 
* **Business process flows**: Business process flows guide users to ensure they enter data consistently and follow the same steps every time. Business process flows are currently supported only for model-driven apps.
* **Workflows**: Workflows automate business processes without requiring user interaction. 
* **Business logic with code**: Business logic supports advanced developer scenarios that extend the application directly through code. 

## Security
Data in CDS for Apps is securely stored so that users can see it only if you grant them access. Role-based security, based on the Dynamics 365 system, lets you control access to entities for different users in your organization.