Before you can start creating datasets in Power BI, the solution architect should understand the data and requirements in relation to Power BI's capabilities.

## Where is the data

Reporting depends so much on the data structure and volumes and also expectations of users. The solution architect should be asking these questions about the data required for reporting?

- Is all data coming from Dataverse?
- Is there any reference data that would be useful?
- What is the volume of data?
- How frequently will data need to be refreshed?
- How is the data related?
- What are the key fields needed to relate data?
- What are the key fields that contain KPIs?
- How sparse is key data fields?
- What data can we leave behind?

> [!IMPORTANT]
> The size of data and refresh frequency can impact licensing.

## Who is consuming the output

The solution architect needs to understand the requirements about who will be looking at Power BI reports and dashboards and ask these questions:

- Who will be consuming the Power BI visualizations?
- Are there any data security considerations on use of data?
- Will users use Q&A feature?
- Any plans for using alerts?
- Any plans for using mobile?
- Any external stakeholders?
- Are there any licensing considerations?

## What security is required

The solution architect needs to understand what sets of data each user is permitted to see in Power BI. A key question is should the data shown in Power BI be the same as can be seen through the apps provided or can they see more summarized data?

Other security considerations:

- Power BI content in shared model-driven app dashboards must also be shared in Power BI.
- Shared dashboards are refreshed in context of the report owner not the user viewing the dashboard.
- Does Row Level Security (RLS) need to be configured?
- Exclude or obfuscate secure fields and PII data.
- Consider aggregating data in the query.
- Limit the export data options in Power BI.

> [!IMPORTANT]
> Power BI and Dataverse have no synchronization on privileges. You can inadvertently grant other people access to confidential data in Power BI.

Consider the frequent scenario where:

- End user should only have access to their own data
- Managers should only have access to their own team's data
- Executives should have access to all data
- Data has been imported into a dataset and combined with data from other systems.

To meet these requirements, you will need to limit access to rows based on assigned roles in the dataset using RLS.
