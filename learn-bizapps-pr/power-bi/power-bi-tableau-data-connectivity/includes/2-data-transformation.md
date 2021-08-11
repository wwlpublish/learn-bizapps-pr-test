## Dataflows

As a Tableau analyst who is transitioning to Power BI, your main learning opportunity will be in making sure that you can connect to your data (the same data that you can connect to in Tableau Desktop) and that the data is ready for analysis. However, you might realize that this scenario is not the case. A significant amount of effort is required for you to cleanse and transform the data.

This scenario is where a tool like Tableau Prep would be beneficial in helping you to create your dataflow. This unit will examine dataflows in depth.

There are three options, each with a button. Define new entities has an Add new entities button and the following description. Choose a data source to define the entities for your dataflow. You can map your data to standard Common Data Model entities, or define custom entities instead. Link entities from other dataflows has an Add linked entities button and the following description. Linking to entities from other dataflows reduces duplication and helps maintain consistency across your organization. Import Model has an Import model button and the following description. Choose a dataflow model to import into your workspace.

### Start screen when you attempt to create a dataflow in Power BI

A dataflow is the data transformation component for analysts in Power BI. It is a collection of entities (like tables) that are created and managed in workspaces in Power BI service. Dataflows are useful if you're applying organization logic to your data and want to share with other people in your organization. This component allows others to edit any step in the flow and use only the desired portions of the flow.

> [!div class="mx-imgBorder"]
> [![Screenshot of how you can edit any step in the flow and use only the desired portion(s) of the flow.](../media/applied-steps.png)](../media/applied-steps.png#lightbox)

### Example of editing any step (in the Applied steps section on the right) in the flow

> [!NOTE]
> The data transformation concepts that are highlighted in the previous screenshot are similar to the functionality that you would find with Tableau Prep (or even Alteryx, for the well-versed analysts). Tableau Prep allows analysts to perform data preparation tasks, such as combining, shaping, and cleaning, so that the data is ready for analysis. These tasks are then saved into a file called a flow. The flows can be shared with others in your organization through Tableau Server or Tableau Online, where people can edit any step in the flow and/or use desired portions of the flow.

For example, consider a scenario where you have sales details in a table and a customer membership table with complex membership logic. You have been asked to create two reports: one that requires all sales information on your customers and another that only needs customer information. With dataflows, you can choose to connect only to the customer information rather than all transformations together.

## Reference links

[Introduction to dataflows and self-service data prep](/power-bi/transform-model/dataflows/dataflows-introduction-self-service/?azure-portal=true)
