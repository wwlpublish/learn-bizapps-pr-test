There are several activities that should be performed prior to go-live.

## Performance testing

Performance testing is to ensure that the application is performing as designed and can handle the rigors of daily use. Strong performance is vital for user adoption. Users will be reluctant to use an application that takes too long to load pages, or walk through business processes. Performance testing helps the customer identify if they need to revisit certain customizations and perform tuning activities.

Many customers don't include performance testing to save on cost and effort, and run into user adoption problems quickly after the application goes live. The solution architect needs to make the customer aware of the risks of not doing performance testing.

The results of this testing may require the solution architect to help plan the remediation steps and guide them through submitting support requests. Performance testing needs to be completed enough in advance of the application going live to remediate any issues surfaced in performance testing.

Key questions that the solution architect should address for performance testing:

- Is there a dedicated environment for performance testing?
- Have you identified the required master or reference data for performance testing?
- Have you identified the key business scenarios and the baseline for these?
- Have you identified the concurrent load for performance testing?
- Have you identified locations to perform latency tests for each location?
- Do you have a plan to populate the required data before performance testing?

The solution architect should:

- Identify potential hotspots in the app that should be performance tested.
- Know what the peak volume might be and always plan for a little higher.
- Ensure that any contractual performance SLAs are tested to ensure compliance.

The solution architect should monitor network traffic for the different office locations. In particular, latency and bandwidth need to be checked to ensure app performance is not adversely impacted by network issues. You can use Azure Monitor and Azure App Insights to monitor performance of your apps.

## Deployment planning

The deployment of a solution will go more smoothly with some preliminary planning. The deployment plan consists of many activities to ensure successful deployment of the solution: The deployment plan will vary on a case by case basis but a deployment plan can include:

- Environment setup
- Types of Testing
- End-User Training
- Data Migration
- Rollout strategy
- Support during deployment

Depending on size of the project the solution architect might either own the deployment plan or act as an advisor to a dedicated planning team. Typically the solution architect does not create the deployment plan but provides input and review.

The solution architect is often the first call when the customer is unhappy with the progress on deployment.

The solution architect should:

- Ensure the sequence of events for go live are in place
- Always looking for risks, and have a plan B.
- Ensure the team is in place to support the deployment.

## Risk assessment

The solution architect knows the system better than anyone and should perform their own risk assessment for go-live. The solution architect should take a look at the system from top to bottom and consider:

- What could break?
- What might not work as designed?
- What if the other system goes down.
- Do we have the proper deployment sequence?
- Plan for the worst, celebrate later when it doesn’t happen.
