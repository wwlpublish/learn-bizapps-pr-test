Now that you have a new business process flow, you can try it out and discover how the data is stored after it has been run.

1. Select the **Update** button in the top ribbon.

1. Close the business process flow designer after you see the message that the process
flow has updated successfully.

1. Go back to **My Flows**. Select **Business process flows**, where you should see the new flow listed.

   > [!NOTE]
   > You can see all immersive business process flows that are in
   process or that have been run by going to the main Power Automate
   page, selecting the **My flows** icon on the left menu, and then
   selecting the **Business process flows** tab.

1. Select the **Run** arrow, as shown in the following screenshot.

   ![Screenshot of Power Automate on the Flows page Business process flows tab. Customer Check In and the Run button next to it are highlighted.](../media/21-run-check-business-process-flow.png)

   This selection will launch a new instance of the flow that you created.

1. Enter a name in the **Name** field on the **General** form (main form) and then select **Save**, as shown in the following figure.

   ![Screenshot of New Customer Check In Stage 1 with Name, New Stage, and the Save button highlighted.](../media/22-check-stage-1.png)

1. After you select the **Save** button, select the red circle for the first stage, fill out the information, and then select the **Next Stage** button.

   ![Screenshot of New Stage dropdown with customer contact info filled in.](../media/23-filling-out-stage-1.png)

1. Select the second stage, fill out the vehicle information, and then select the **Finish** button.

   ![Screenshot of second New Stage dropdown with automobile info filled in.](../media/24-filling-out-stage-2.png)

   After you select the **Finish** button, the button in Stage 2 should turn green and the data that you entered is automatically saved.

   ![Screenshot of second New Stage dropdown with the green Finished button highlighted.](../media/25-business-process-flow-complete.png)

1. You can create additional records by launching Power Automate, selecting **My Flows** and **Business process
flows**, and then selecting the arrow next to the **Customer Check In** business process flow, as shown in the following screenshot.

   ![Running the business process flow again](../media/26-run-business-process-flow-again.png)

### View the created data

You can view the data that you created for running the flow by following these steps:

1. Go to [Power Apps](https://make.powerapps.com/?azure-portal=true) and sign in.

1. Select the environment that you used to create the **Customer Check In** business process flow, as shown in the following screenshot.

   ![Screenshot of Power Apps Home page with Environment SmogChecksRUS highlighted in the top right corner.](../media/27-launch-power-apps.png)

   ![Screenshot zoomed in on the highlighted Environment SmogChecksRUS.](../media/28-check-environment.png)

1. Select the **Solutions** menu on the left side of the screen.

   ![Screenshot of Power Apps navigation menu with Solutions highlighted.](../media/29-select-solutions-menu.png)

1. Double-click the **Microsoft Dataverse Default Solution** to open it, as shown in the following figure.

   ![Screenshot of Power Apps Solutions page with Microsoft Dataverse Default Solution highlighted.](../media/30-select-cds-default-solution.png)

1. Select the **Customer Check In** entity.

   ![Screenshot of Power Apps Solutions > Microsoft Dataverse Default Solution page with Customer Check In highlighted.](../media/31-select-check-entity.png)

1. Select the **Data** tab then click **Select view** on the right side of the screen, and then select the **All Data** view option.

   ![Screenshot of Power Apps Solutions > Dataverse Default Solution > Customer Check In page with the Data tab and Select View button highlighted.](../media/32-select-data-tab-all-data-view.png)

   ![Screenshot zoomed in to show the date in the all data view.](../media/33-close-up-all-data-view.png)

Now, you can view the all the data that you created with your new immersive business process flow.

In the next and final module of this learning path, you will improve your new immersive flow by
customizing the form that is associated with your flow, adding logical branching, and adding instant
workflow notification to make your new immersive business process flow even more powerful.
