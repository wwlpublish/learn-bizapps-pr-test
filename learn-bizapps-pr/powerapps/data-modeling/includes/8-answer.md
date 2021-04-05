There may be other ways to approach these requirements. Here are some ideas and tips.

## Scenario: VIP customer management

You should use the following tables:

- Account and Contact table for the Customer
- Level table for the levels of VIP
- Benefit table for the benefits
- Requirement table for the requirements
- Level Benefit table, or use a N:N relationship between Level and Benefit, for the benefits for each level
- Level Requirement table, or use a N:N relationship between Level and Requirement, for the requirements to achieve the level
- VIP Benefit table for the benefits available to each VIP

How the requirements are measure may affect the tables required.

## Scenario: File and Image storage

You should use the following storage:

- Image of Customer: Use Dataverse as can store small and full images.
- Contract Collaboration: Use SharePoint.
- PDF of competitor status: Could use either a column in Dataverse or SharePoint.
- Benefit Guide: Use Azure Storage. This could from Marketing assets or another CMS if you have one.

## Exercise: Design a data model

A solution is not provided. There are many possible models that could be built and we do not want to define "the answer". You could use some of the Sales CDM tables, but also could equally argue not to use them. This is meant to be a difficult exercise and your own experience will guide you.

To answer some of the tasks:

- Visitor photos can be stored in Dataverse as the image data type.
- Signed wavier can be stored in Dataverse as the file data type.
- Viewing of tracking data should not be brought into Dataverse but could be accessed via custom connector.
