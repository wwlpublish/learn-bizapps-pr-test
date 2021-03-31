When deploying Power Platform solutions, data is important. Your users cannot help your customers if there's no data in the system. Typically, when replacing another business application with a solution based on Microsoft Dataverse, some data is migrated into the new system during the deployment so the users can see relevant business data when they start using the application.

## Data migration approaches and tools

There are multiple types of tools and approaches that can be used when migrating data to Microsoft Dataverse. The following list of options is not an exhaustive list, but it includes some of the most common options:

- Get data from Excel: In the Maker Portal, you can click Get data when viewing a table and import data from an Excel or .csv file.
- Legacy data import utility: You can import data to tables from csv, xls, xml, and zip files.
- Power Platform Dataflows: In the Maker portal, you can select Dataflows from under the Data menu, and configure an import from various cloud data sources. Data from these sources can be transformed prior to import using Power Query.
- Extract, transform, and load (ETL) software such as Azure Data Factory. Azure Data Factory has a connector for Microsoft Dataverse.
- Third-party tools such as Kingswaysoft.
- Custom applications developed using the API.

## When to perform data migration

Data migration must be performed at many points in the project:

- Developers and functional consultants will require data when building apps.
- Users will require data for User Acceptance Testing.
- Testers will require data for Integration and Performance testing.
- Subject Matter experts require data for data validation testing

Data migrations will therefore need to be performed multiple times during a project.

## Sample data

Data migration will depend on getting the data from the source system. Often this can be delayed, so it maybe necessary to create sample data for use in early development and testing activities.

## Testing data migration

Data validation is a critical part of assessing the successful completion of data migration. There are two aspects of data validation testing; data quantity and data quality. Data quantity refers to the number of rows that were expected to be created in Dataverse, and quality is the correctness of data values as defined by data mapping.

Data quantity may not be a one to one match of records between the source environment and the test environment, especially for transaction data, as the data model design may be different in the target environment. As another example, some data quality issues are systemic with customer's data. If they have many different customer records for the same organization and you are integrating with their financial system, you're limited in how much you can improve their data. The testing team needs to be aware of issues like this to be effective at executing their testing plan.

Data like record ownership and the created on/by and modified on/by is likely to be different. This is also likely impacted by users who no longer exist and ownership won't be the same. This is one of the reasons you can't just do a straight table compare. Testing however should validate that this is being handled correctly and mapped as expected.

The expectations for data quantity and quality should be clearly identified both as part of the data migration strategy and testing strategy. Similarly, the data values may not show up as exactly the same value due to the difference in the new schema or due to transactional logic applied. Key business users must be engaged in this testing activity, especially for quality. Customers should also consider using a separate environment for testing data and not mix it with UAT testing as there will be a risk of UAT users modifying the migrated data. The number of runs must also be planned with initially a small subset, and then a significant 70% to 80% of full volume to ensure the correctness of migrated data.

Data validation testing is important to ensure the data migration is completed properly as this has a significant impact on correct functioning and adoption of the application. It is vital to raise awareness of the importance of data quality imported into the production system.

The solution architect needs to identify if the customer is missing any aspects of this critical activity and confirm that the customer is planning to validate imported data before going live to ensure data quality.

Key things to look for with data validation testing

- Have you identified the scope for data validation?
- Have you identified subject matter experts to perform data validation testing? Does this include users and managers?
- Have you considered integration/migration with a smaller record set and perform testing?
- Have you determined the strategy, outcome, and schedule for data validation testing?
- Have you identified the number of runs and data volume for each testing cycle?
- Have you defined the criteria for validating both data quality and quantity?
- Have you maintained separate environments for data validation?
- Are key test users aware of the transition logic being applied during data migration?

## Prioritize data migration

Do not under estimate the amount of effort required for data migration.

Data migration planning should take place as soon as possible after the project has started. Data migration may identify data elements and business processes that have not been captured in the requirements analysis. It is crucial that these omissions are raised with the customer so that decisions as to what to do with this newly identified data can be taken without jeopardizing the project.
