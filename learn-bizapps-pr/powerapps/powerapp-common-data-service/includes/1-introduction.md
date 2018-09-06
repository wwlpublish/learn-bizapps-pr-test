Common Data Service (CDS) for Apps lets you securely store and manage data used across you Dynamics 365 business applications. Data within Common Data Service for Apps is stored within a set of records call entities. For example, a customer account is an entity that contains information like Customer billing address, email, phone number, and so forth. 

Common Data Service for Apps includes a base set of standard entities that cover typical scenarios. You can also create custom entities specific to your organization and populate them with data you import from lists in SharePoint, from Excel, or from Power Query. App makers can then use PowerApps to build rich applications using this data.

![Screenshot showing overview of the Business Application Platform.](../media/platform.png)

## Why use Common Data Service for Apps?
Entities let you create a business-focused definition of your organization's data for use across your Dynamics 365 apps. 

Here are more benefits of using entitles:

* **Easy to manage**: Both the metadata and data are stored in the cloud. You don't need to worry about the details of how they're stored.
* **Easy to secure**: Data is securely stored so that users can view the data only if you grant them access. Role-based security allows you to control access to entities for different users and teams within your organization.
* **Access your Dynamics 365 Data**: Data from your Dynamics 365 applications is also stored within Common Data Service for apps, allowing you to quickly build apps which leverage your Dynamics 365 data. You can then extend your apps using PowerApps.
* **Contain rich metadata** Data types and relationships are leveraged directly within PowerApps.
* **Add logic and validation to your business**: You can define calculated fields, business rules, workflows, and business process flows to ensure data quality and to drive business processes.
* **Include Productivity tools**: Entities are available within the add-ins for Microsoft Excel to increase productivity and ensure data accessibility.

## Dynamics 365 and Common Data Service for Apps

Dynamics 365 applications, such as Dynamics 365 for Sales, Service or Talent, also use Common Data Service for Apps to store and secure data used by the applications. This means you can build apps using PowerApps and Common Data Service for Apps directly against your core business data already used within Dynamics 365 without the need for manual integration.

Here are more benefits of working with apps across Dynamics:

* **Build Apps against your Dynamics 365 Data**: Build apps quickly against your business data within PowerApps or by using the Pro Developer SDK.
* **Manage reusable Business logic and rules**: Business Rules and logic already defined in on your Dynamics 365 entities are applied to your PowerApps. This ensures data consistency regardless of how your users are accessing the data or through which app.
* **Reusable skills across Dynamics 365 and PowerApps**: Users with skills learned in PowerApps or Dynamics 365 can now leverage those skills across the new Common Data Service for Apps Platform. Creating entities, forms, charts, etc are now common across your applications.

    > [!NOTE]
    > Dynamics 365 for Finance and Operations currently requires the configuration of the Data Integrator to make your business data from Finance and Operations are available within Common Data Service for Apps.

## Integrating Data into Common Data Service for Apps

Building an app typically involves data from more than one source. Working with data from different sources can sometimes be done at the application level. However, integrating this data together into a common store allows for an easier app building experience. You also gain the advantages of a single set of logic to maintain and operate over the data. 

Common Data Service for Apps allows data to be integrated from multiple sources into a single store. This single store can then be used in PowerApps, Flow and Power BI along with data already available from the Dynamics 365 applications.

* **Scheduled integration with other systems**: Data which is kept within another application can be regularly synchronized with Common Data Service for Apps. This synchoronization allows you to leverage other applications data in PowerApps.
* **Transform and import data using PowerQuery**: 
You can import and transform data from many different data sources. You can do this using PowerQuery, which is a common tool used with Excel and Power BI.
* **One time import of data**: Simple import and export of Excel and CSV files can be used for a one time or infrequent import of data into Common Data Service for Apps.

## Interacting with entities
When you develop an app, you can use standard entities, custom entities, or both. Common Data Service for Apps provides standard entities by default. These entities are designed with best practices that capture the most common concepts and scenarios within an organization.

![Screenshot showing a list of entities.](../media/entitylist.png "Entity list")

See the [full list of entities](https://docs.microsoft.com/powerapps/developer/common-data-service/reference/about-entity-reference).

You can extend the functionality of standard entities by creating one or more custom entities to store information that's unique to your organization. 

Learn more about [how to create a custom entity](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/create-custom-entity).

## Logic and validation
Entities within Common Data Service for Apps can leverage rich server-side logic and validation to ensure data quality. You can also reduce repetitive code in each app that creates and uses data within an entity.

* **Business rules**: Business rules validate data across multiple fields and entities and provide warning and error messages, regardless of the app used to create the data. Learn more about how to [create a business rule](https://docs.microsoft.com/en-us/powerapps/maker/common-data-service/data-platform-create-business-rule).
* **Business process flows**: These flows guide users to ensure they enter data consistently and follow the same steps every time. Business process flows are currently only supported for model-driven apps. Learn mre about [Business process](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/business-process-flows-overview).
* **Workflows**: Workflows automate business processes without user interaction. Learn more about [Workflows](https://docs.microsoft.com/en-us/dynamics365/customer-engagement/customize/workflow-processes).
* **Business logic with code**: Business logic supports advanced developer scenarios that extend the application directly through code. Learn more how to [apply business logic with code](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/apply-business-logic-with-code).

## Developer capabilities
In addition to the features available through the [PowerApps](https://web.powerapps.com/), Common Data Service for Apps also includes features for developers to program with metadata and data to create custom entities and business logic. Learn more about the [Common Data Service for Apps Developer Overview](https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/overview).

## Privacy notice
With the Microsoft PowerApps common data model, Microsoft collects and stores custom entity and field names in our diagnostic systems. We use this knowledge to improve Common data model for our customers. The entity and field names that app Creators create help us understand scenarios that are common across the Microsoft PowerApps community and ascertain gaps in the service’s standard entity coverage, such as schemas related to organizations. The data in the database tables associated with these entities is not accessed or used by Microsoft or replicated outside of the region in which the database is provisioned. Note, however, that the custom entity and field names may be replicated across regions and are deleted in accordance with our data retention policies. Microsoft is committed to your privacy as described further in our [Trust Center](https://www.microsoft.com/trustcenter/Privacy/default.aspx).