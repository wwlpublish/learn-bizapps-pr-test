In this exercise, you'll ingest the Dataverse sample data from your Azure Data Factory into Dynamics 365 Customer Insights and run the Retail Banking Churn Model.

## Task 1: Configure a data source in Dynamics 365 Customer Insights

In this task, you'll configure the operationaldata data source for ingesting data into Customer Insights.

1. In Customer Insights, navigate to **Data Sources** and edit **operationaldata**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Customer Insights on the Data sources page showing the edit button next to the operationaldata data source.](../media/operational.png)](../media/operational.png#lightbox)

1. Select **Azure subscription** and then select the appropriate **Subscription**, **Resource group**, and **Storage account** from the dropdown menus. For the **Container** field, type the name of your Container. Select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of .](../media/storage-details.png)](../media/storage-details.png#lightbox)

1. Scroll down and select the **msfsi.manifest.cdm.json** file. Select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Select a common data model file showing the JSON file selected.](../media/select-file.png)](../media/select-file.png#lightbox)

1. Select all entities and select **Next**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Common Data Model folder showing all entities selected.](../media/entities.png)](../media/entities.png#lightbox)

1. Select all entities for data profiling and select **Save**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Common Data Model folder showing the message "Indicate which data entities you want to enable data profiling" and all entities selected.](../media/profiling.png)](../media/profiling.png#lightbox)

1. Go back to **Data Sources** to view the status. The process should complete with some errors for Analysis preparation. This error is normal and won't affect any future steps.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Data sources showing operationaldata Status as Completed with errors.](../media/errors.png)](../media/errors.png#lightbox)

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Progress details showing that the Analysis preparation had zero of one refreshed.](../media/progress-details.png)

1. Now that the entities have been mapped, go to **Unify** on the site map to run the Match by selecting **Run**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Audience insight with Unify selected in the navigation pane to the left. In the Match tab of Unify, the Run button appears at the top.](../media/run.png)](../media/run.png#lightbox)

1. Once the match is complete, you should see the following numbers for your matches.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Unify on the Match tab showing 74 unique source records, 37 matched and non-matched, and 37 matched records only.](../media/unify.png)](../media/unify.png#lightbox)

1. As a final step before running the prediction model, we must now merge the records. On the **Merge** tab, select **Run** and then select **Run Merge and downstream processes**.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Run menu expanded to show options for Run Merge and downstream processes or Run only Merge.](../media/run-merge.png)](../media/run-merge.png#lightbox)

1. Once the merge is complete, you should see the following success message.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Unify on the Merge tab showing current matched records 37 and the successful message.](../media/unify-merge.png)](../media/unify-merge.png#lightbox)

1. Expand **Intelligence** on the site map and go to **Predictions**. You'll now see the Retail banking churn model begin to refresh. This step may take several minutes to complete. If it doesn't complete after 10 to 15 minutes, try running the merge in step 9 again.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Audience insight on the Intelligence Predictions page My predictions tab showing the Retail banking churn prediction status as Refreshing.](../media/refreshing.png)](../media/refreshing.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Audience insight on the Intelligence Predictions page My predictions tab showing the Retail banking churn prediction status as Successful.](../media/successful.png)](../media/successful.png#lightbox)

1. Open the Prediction to view the contents of the training model. Here you'll find three main areas:

    - **Training model performance** will display a letter grade of how well the model has performed.

    - **Likelihood to churn (number of customers)** that can be read as X customers are Y% likely to churn.

    - **Most influential factors** considered by the AI in predicting the model. These factors will vary depending on the data set.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Audience insight on the Retail banking churn prediction page showing Training model performance of A, a churn risk chart, and Most influential factors.](../media/churn.png)](../media/churn.png#lightbox)

1. To view a customer's full profile in Dynamics 365 Customer Insights, navigate to Customers and open any of the sample records.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of Customer Insights on the Customers page showing 37 customers.](../media/customers.png)](../media/customers.png#lightbox)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the full profile for the customer Rowan Gray (Sample).](../media/customer-profile.png)](../media/customer-profile.png#lightbox)

1. To view the calculated churn scores, navigate to **Data** and then under **Intelligence**, open the **msfsiRetailBankingChurn** entity that was created when you ran the churn model.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the list of Entities showing the churn model under Intelligence.](../media/entity.png)](../media/entity.png#lightbox)

1. Select the **Data** tab to see the calculated churn score for each of the CustomerIDs in the dataset.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Customer Insights churn Data tab showing the list of Customer I Ds with a churn score next to each.](../media/score.png)](../media/score.png#lightbox)

1. To view the churn score in **Dataverse**, open a new tab in your internet browser and navigate to your Dataverse environment in [Power Apps](https://make.powerapps.com/?azure-portal=true).

1. Go to **Apps** and then open **Unified Customer Profile**.

    > [!div class="mx-imgBorder"]
    > ![Screenshot of Apps with Unified Customer Profile selected.](../media/apps.png)

1. Open any of the 37 sample contact records.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Unified Customer Profile sandbox on the All contacts page.](../media/sandbox.png)](../media/sandbox.png#lightbox)

1. Scroll down to the bottom of the **Customer Snapshot** section and select the **i** icon to see the full details of the churn score.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of a contact's customer profile with the Churn risk score dialog open showing a score of 12 of 100, low churn risk.](../media/churn-risk.png)](../media/churn-risk.png#lightbox)

**Congratulations!** You've successfully run the Retail Banking Churn Model in Dynamics 365 Customer Insights.
