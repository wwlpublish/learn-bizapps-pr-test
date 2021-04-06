# Business process flows

Business process flows are a capability of the Power Platform that helps users observe a defined business process, find out where they are in the process, and know what data is required to complete the next stage. Business process flows are used within model-driven apps to help guide the user through multiple steps and stages.

 A Business process flow is consists of stages and steps. A stage is linked to a Dataverse table, and steps and typically linked to columns in the table for the stage. The business process flow is shown at the top of a form in a model-driven app.

![Screenshot showing a Business process flow.](../media/6-bpf.png)

## Capabilities

Business process flows are interactive guide for users to get work done and to track major milestones in long running business processes. Business process flows have several capabilities that can be used in your solution to aid business processes:

- Stage gating: The steps in a stage can be mandatory, preventing the user from moving to the next stage in the process until the step has been completed.
- Conditional branching: The business process flow stages can alter which is the next stage in the process based on values entered.
- Multiple tables. A business process flow can include up to five tables in the process.
- Switch: A user can switch from one business process flow to another at any time.
- Security: Business process flows can be linked to security allows different users to use different business process flows.

When a Business process flow is created, a table called the process table, is created. This table is used to track the instances of the business process flow and their current stage. You can add this table to a model-driven app navigation and can create reports, charts, and dashboards to show usage of business process flows. There is a Power BI template app that provides visualizations for running of business process flows.
Automation and Developer APIs

Process management can be automated using the API or by Power Automate to start/stop the process as well advance stages automatically.

## Use cases

Good candidates for using Business process flows:

- Encourage outcomes, not wizard data capture.
- Link between related table; the form changes automatically from one table to another. This hides the data model from the user.
- Triggers automation based on progression between stages.

## Branching vs Multiple processes

A decision that may need to be made with Business process flows is to have one process with multiple branches or to have multiple processes. You can answer this by examining these issues:

- Do the processes need to run concurrently?
- Does the process need to return to same place after the branch?
- How will you decide which business process flow is used for new records?

## Immersive business process flows

Business process flows be used standalone outside the context of a model-driven app using a per process license. These are known as immersive Business Process flows.

You create an immersive business process flow by selecting None for the table to associate the flow with. The process table created then becomes the table where columns can be added, a form created, and data is stored.
