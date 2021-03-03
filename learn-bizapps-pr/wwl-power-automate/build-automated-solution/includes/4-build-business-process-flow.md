Business process flows are used to guide a user through the steps of your business process when working with Model-driven apps and Microsoft Dataverse. The example below will guide you through the process and decisions you need to make when building a business process flow. 

## Create a business process flow

1. Launch [Power Automate](https://flow.microsoft.com/) and sign in using your organizational account.

2. In the left pane, select **My flows**.

3. On the top bar, select **Business process flows**.

4. Select **+ New** at the top.

5. In the **Build a business process flow** pane, fill in the required fields:

    - **Flow Name**: The display name of the process doesn't have to be unique, but it should be meaningful for people who must choose a process. You can change this name later.

    - **Name**: A unique name that's based on the display name. You can change the name when you create the process, but you can't change it after the process has been created.

    - **Choose a table**: Select the table to base the process on. You can choose *Account* for this example. 

         The table that you select affects the columns that are available for steps in the business process flow. You can't change the table after creating the business process flow.

6. Select **Create**.

    The new process is created, and the business process flow designer is started. The designer page has three sections:

    - On the left, a single stage named Account New Stage has already been created for you.

    - Beneath this stage is the mini map, which lets you see the whole process or quickly go to a part of the process.

    - On the right are components that you can drag to the designer. You can also set properties to create a business process flow.

         ![Power Apps business process flow designer](../media/business-process-flow-designer.png)

7. Add stages, so that users can proceed from one business stage to another in the process:

    1. Drag the **Stage** component from the **Components** tab to the plus sign (+) in the designer.

       ![Stage tabs](../media/new-stage-component.png)

    2. Select the stage, and then, on the **Properties** tab on the right, set the properties:

       1. Enter a display name.

       2. Optional: Select a category for the stage (for example, **Identify** or **Research**). This category will display on the business process flow stage.

          ![Business Process Flow stages](../media/business-process-flow.png)

       3. When you've finished setting the properties, select **Apply**.

8. Add steps to each stage:

    1. Select **Details** on a stage to view the steps and processes in that stage. 
    
    2. Select **Data Step #1** to edit the Properties of that step. 

    3. Populate **Identify Primary Contact** for the **Step Name** and select **Primary Contact** for the **Data Field**.
    
    4. Select the **Component** tab and drag the **Data Step** component to the stage, under the previous step.

       ![Adding steps to each stage](../media/add-step-to-stage.png)

    5. Repeat the previous steps to populate the Data Steps as desired. 

9. Add a branch (condition) to the process:

    1. Drag the **Condition** component from the **Components** tab to the plus sign (+) between two stages.

       ![Condition branches](../media/add-condition-to-business-process-flow.png)

    2. Select the condition, and then, on the Properties tab, set the properties. When you've finished, select Apply.

10. Add a workflow to the process:

    1. Drag the **Workflow** component from the **Components** tab to either a specific stage or the **Global Workflow** item:

       - Drag the **Workflow** component to a specific stage if the workflow should be triggered when the process enters or exits that stage. The **Workflow** component must be based on the same primary entity as the stage.

       - Drag the **Workflow** component to the **Global Workflow** item if the workflow should be triggered when the process is activated or archived (that is, when the status changes to **Completed** or **Abandoned**). The **Workflow** component must be based on the same primary entity as the process.

    2. Select the condition, and then, on the **Properties** tab, set the properties:

       1. Enter a **display name**.

       2. Select when the **workflow** should be triggered.

       3. Search for an existing on-demand active workflow that matches the stage entity, or create a workflow by selecting **New**.

       4. When you've finished, select **Apply**.

11. To validate the business process flow, select **Validate** on the action bar.

12. To save the process as a draft while you continue to work on it, select **Save** on the action bar.

13. To activate the process and make it available to your team, select Activate on the action bar.

14. To define who has privileges to create, read, update, or delete the business process flow instance, select **Edit Security Roles** on the action bar. For example, for service-related processes, you might give customer service reps full access to change the business process flow instance. But you might give sales reps just read-only access to the instance, so that they can monitor post-sales activities for their customers.

    1. In the **Security Roles** pane, select the name of a role to open the details page for that role.

    2. On the **Business Process Flows** tab, select options to assign the role appropriate privileges for the business process flow.

       ![Business process flow tab for security roles](../media/business-process-flow-security-role.png)

    3. Select **Save**.

## Edit a business process flow

You can edit the business process flow after it has been created.

1. In the [Power Apps portal](https://make.powerapps.com/), select **Flows** in the left pane.

2. In the list of processes, select the business process flow that you created, and then select the **Edit** button.

Keep the following points in mind when you edit the stages of a business process flow:

  - Business process flows can have up to 30 stages.

  - You can add or change the following properties of a stage:

    - **Stage Name**: You can change the stage name after you create the stage.

    - **Table**: You can change the table for any stage except the first one.

    - **Stage Category**: A category lets you group stages by the type of action. It's useful for reports that will group rows by the stage that they're in. The options for the stage category come from the Stage Category global choice. You can add more options to this global choice and change the labels of existing options. You can also delete options, but we recommend that you keep the existing options. If you delete an option, you won't be able to add it back later. If you don't want an option to be used, change the label to Do not use.

    - **Relationship**: Enter a relationship when the preceding stage in the process is based on a different table than the current stage. For the current stage, select **Select relationships**, and then specify the relationship that should be used when the flow moves between the two stages. We recommend that you specify relationships, because they provide the following benefits:

      - Attribute maps are often defined for relationships. These attribute maps automatically carry over data between rows. Therefore, they help minimize the amount data entry that's required.

      - When you select **Next Stage** on the process bar for a row, any rows that use the relationship are listed in the process flow. Therefore, the reuse of rows in the process is promoted. In addition, you can use workflows to automate the creation of rows. Users then just have to select the workflow instead of creating a row. Therefore, the process is streamlined.

    - **Set Process Flow Order**: If you have more than one business process flow for a table, you must specify which process is automatically assigned to new rows. On the action bar, select Order Process Flow. For new rows or rows that don't already have a process flow associated with them, the first business process flow that a user has access to will be used.

    - **Enable Security Roles**: A user's access to a business process flow depends on the privileges that are defined for the business process flow in the security role that's assigned to the user. By default, only the System Administrator and System Customizer security roles can view a new business process flow.

Now you have seen firsthand the process and options for creating a business process flow. You can now apply these lessons to your own business process flow and continue to refine your flow by adding conditions, for example. Business process flows offer multiple levels of customizations to help facilitate working with your business data.