A business process flow is a series of ordered work steps a user
completes within a business process. In Microsoft Power Automate, a
business process flow is composed of a series of discrete stages that
lead a user along a path towards process completion. Each stage contains
one or more fields (called data steps) that should be completed before
proceeding to the next stage in the business process flow.

A business process flow visually guides a user through stages within a
process and shows progress towards process completion. A user can also
easily see which stages they have completed and which stages still need 
to complete within an instance of a process. 

Business process flows can be configured to require users enter certain 
fields (data steps) before completing the stage and if needed, you can 
also allow users to jump stages. All of the data collected while completing 
a business process flow is stored in one or more entities in Common Data Service.

The illustration below shows a simple business process flow with two
stages for adding questions to a survey. Also note the business process
flow is shown as a component of a model driven solution in Power Apps.

![Model App with business process flow Stage One displayed](../media/1-embedded-business-process-flow-stage-displayed.png)

Business process flows are created and managed using Power Automate and they 
are available for out-of-the-box entities and even your own custom entities. 
Microsoft has many pre-built business process flows or you can create your own.
Additionally, an entity can have none, one, or many business process
flows associated with it. Business process flows are customizable
to easily fit many organizational needs.

> [!TIP]
> Business process flows are meant to guide users through steps required to 
complete a business process. You must have a valid Power Apps Dynamics 365 
license or a valid Power Apps license to create or use a business process flow.
