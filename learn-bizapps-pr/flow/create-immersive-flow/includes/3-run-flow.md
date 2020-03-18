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

	![Run check in business process flow](../media/21-run-check-business-process-flow.png)
	
	This selection will launch a new instance of the flow that you created.
	
1. Enter a name in the **Name** field on the **General** form (main form) and then select **Save**, as shown in the following figure.
	
	![Check in Stage 1](../media/22-check-stage-1.png)
	
1. After you select the **Save** button, select the red circle for the first stage, fill out the information, and then select the **Next Stage** button.
	
	![Filling Out Stage 1](../media/23-filling-out-stage-1.png)
	
1. Select the second stage, fill out the vehicle information, and then select the **Finish** button.
	
	![Filling Out Stage 2](../media/24-filling-out-stage-2.png)
	
	After you select the **Finish** button, the button in Stage 2 should turn green and the data that you entered is automatically saved.
	
	![Business process flow	complete](../media/25-business-process-flow-complete.png)
	
1. You can create additional records by launching Power Automate, selecting **My Flows** and **Business process
flows**, and then selecting the arrow next to the **Customer Check In** business process flow, as shown in the following screenshot.
	
   ![Running the business process flow again](../media/26-run-business-process-flow-again.png)

### View the created data

You can view the data that you created for running the flow by following these steps:

1. Go to [Power Apps](https://make.powerapps.com/?azure-portal=true) and sign in.

1. Select the environment that you used to create the **Customer Check In** business process flow, as shown in the following screenshot.

	![Launch Power Apps](../media/27-launch-power-apps.png)
		
	![check environment](../media/28-check-environment.png)

1. Select the **Solutions** menu on the left side of the screen.

	![Select Solutions on menu on left](../media/29-select-solutions-menu.png)

1. Double-click the **Common Data Services Default Solution** to open it, as shown in the following figure.

	![Select Common Data Service Default Solution](../media/30-select-cds-default-solution.png)

1. Select the **Customer Check In** entity.

	![Select Customer Check In entity](../media/31-select-check-entity.png)

1. Select the **Data** tab then click **Select view** on the right side of the screen, and then select the **All Data** view option.

	![Select data tab and all data view](../media/32-select-data-tab-all-data-view.png)
		
	![close up of all data view](../media/33-close-up-all-data-view.png)

Now, you can view the all the data that you created with your new immersive business process flow.

In the next and final module of this learning path, you will improve your new immersive flow by
customizing the form that is associated with your flow, adding logical branching, and adding instant 
workflow notification to make your new immersive business process flow even more powerful.
