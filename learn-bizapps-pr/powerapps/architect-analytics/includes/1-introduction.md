Analytics play a major role in solutions developed for the Power Platform. There are many ways for analytics and insights to be delivered with the Power Platform. The solution architect will need to evaluate the ways for implementing reporting and analytics in the solution.

Artificial intelligence (AI) is becoming more important to enhance the apps and data in business solutions. The solution architect will need to evaluate the options for using AI within Power Platform solutions.

## Reporting and Insights

The solution architect needs to consider reporting and analytics in all stages of the project.

![Diagram of project stages.](../media/1-stages.png)

For example:

- A solution architect will often be involved in sales and pre-sales and will use reporting to dazzle the customer.
- During the Analyze, the solution architect must clarify the actual goals for reporting and analytics.
- In Design, the solution architect must ensure that data modeling incorporates the required data and data relationships to support the reporting and analytic requirements.
- Training and setting up for self-service is required at the Deploy stage.

## The role of the Solution Architect in reporting

The Power Platform offers a multitude of options for reporting, which will be covered in this module. The solution architect must evaluate the needs from requirements and identify the best approach to take.

> [!NOTE]
> There may be different approaches required for different needs. The solution architect needs to select the most appropriate method for each requirement and scenario.

A key task that is often overlooked as reporting is left to the end of the project is to ensure that the data model supports the requirements for reporting and analytics. The data model must also support the relationships required for analytics. The solution architect should ensure that the data model support both the application processing and any reporting required.

The solution architect should look for opportunities to use proactive insights and AI instead of reactive reviewing of reports and analytics.

## Types of reporting and analytics

When looking at reporting, the solution architect needs to consider the different categories of reporting and analytics:

- Operational reporting: Data comes from Dataverse directly, viewed and interacted with in the context of a Power App.
- Self-service BI: Data is exported from Dataverse or could be refreshed on a schedule.
- Enterprise BI: Data is extracted for use in broader enterprise reporting tools, this could be done to allow integration of data from other sources.

![Diagram of types of reporting.](../media/1-types-of-reporting.png)

The solution architect needs to be aware of the prebuilt insights available with Dynamics 365 apps such as:

- Dynamics 365 Sales Insights
- Dynamics 365 Customer Service Insights
- Dynamics 365 Customer Insights
- Dynamics 365 Fraud Protection

There are extensive insights capabilities available within these apps that could be used in the solution instead of building reports. There are also Power BI template apps for Dynamics 365 apps that could be deployed to meet reporting requirements.

There are many consideration to take into account when evaluating requirements for reporting and visualizations:

- What data is required?
- Is there data required that is external to the solution?
- Does the requirement fit with one of the pre-built insights?
- Who consumes the report/visualization and are they users already?
- How fresh does the data have to be or does it need to be a point in time?
- Do we need to build something, or can an existing view or report satisfy the requirement?
- What is the expected action users will take from reviewing the report?
- Is the action something we can predict, or automate instead?
