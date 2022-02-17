Customer data platforms share common elements such as data collection, profile unification, segmentation, and activation. With unified customer profiles in Dynamics 365 Customer Insights, you get that and more. Customer Insights includes out of the box profiles that can be enriched using included services to better know your customer and get a single view of them with the unified customer profile. Dynamics 365 Customer Insights are managed and maintained by the business users in your organization, avoiding the added expense of more costly IT resources. As part of the unified customer profile in Customer Insights, you can include a custom retail churn score using the retail channel churn predictive model in Microsoft Cloud for Retail.

## Customer Insights

Dynamics 365 Customer Insights works well with your data that is ready to process. If your data needs major transforming, consider using Azure Synapse in addition to, or instead of, Customer Insights. For more information, see [Transform data in Azure Data Factory and Azure Synapse Analytics](/azure/data-factory/transform-data/?azure-portal=true).

When you first start with Customer Insights, you'll choose one of two paths to focus on, audience insights or engagement insights (currently in preview). Choose audience insights to unify disparate data across multiple sources for a 360-degree view of your customers. Choose engagement insights to understand customer behavior across websites, mobile apps, and connected products. You can switch your path at any time. For a self-guided tour of Customer Insights, see  [Microsoft Guided Tours](https://guidedtour.microsoft.com/en-us/guidedtour/dynamics/customer-insights/5/1/?azure-portal=true).

### Unified customer profile in Customer Insights

The unified customer profile in Customer Insights is a valuable asset. You can quickly see a single view of an individual customer. The unified customer profile you have in the audience insights path shows information and intelligence from several different data sources.

> [!div class="mx-imgBorder"]
> [![Screen image of a unified customer profile in Dynamics 365 Customer Insights.](../media/profile.png)](../media/profile.png#lightbox)

With the information in unified customer profiles, you can build segments and micro-segments to better target your customer. Additionally, AI offers insight into the influence of your customer segments.

> [!div class="mx-imgBorder"]
> [![Screen view of a table of segments and their status values.](../media/segments.png)](../media/segments.png#lightbox)

While Customer Insights offers you much greater information about your customers, connecting it to external systems, such as Dynamics 365 Marketing, allows you to expand that knowledge into action and engagement. To learn more about Customer Insights, see [Unlock customer intent with Dynamics 365 Customer Insights](/learn/paths/build-customer-insights/?azure-portal=true).

Let's take a look at Customer Insights and the unified customer profile.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWVHaF]

## Retail channel churn

Expand insight into your customer with the retail channel churn predictive model. Microsoft Cloud for Retail Unified customer profile (currently available in the U.S.) includes an AI-based churn predictive model, designed for omnichannel retail and built atop Customer Insights.

Create a retail channel churn predictive model to fit your business needs, and gain cross-channel insights into the chance of retail customer churn. Run your company data through this model, training it to improve its predictions and identify the factors that contribute to churn, at the customer level.

### Configure and train your retail churn model

In order to complete setup and training of your retail churn model, you need to meet the following prerequisites:

- Retail components, available within Microsoft Cloud for Retail in Microsoft Cloud Solution Center.

- At least Contributor permissions in Dynamics 365 Customer Insights.

- An understanding of what churn means for your organization. A customer is considered to have churned if their purchase value or volume drop below thresholds that you define.

Three data entities require mapping to the retail churn model: customer data, session data and transaction data. With each of these entities, you'll have columns of data that are required for the configuration and training of the model and some columns that are optional. With all AI-models, the more data you configure for training, the more accurate predictions can be. And with more accurate predictions the value of the churn model is greater for your organization.

> [!NOTE]
> You may see entities also referred to as *tables*. For our purposes here, consider these terms interchangeable.

To create and train your model, you need to follow a few general steps that will be explained here. For detailed step by step instructions, see [Introduction to Azure Synapse Analytics](/learn/modules/introduction-azure-synapse-analytics/?azure-portal=true).

You'll first name your model, then select some preferences for your model. These preferences include prediction period number of days and transaction threshold definitions. Next you'll map the data columns from the entities mentioned above. And finally, you'll set a frequency for retraining your model. Retraining your model improves the accuracy of your predictions. Select **Save and run** to begin the prediction process. Review the progress of your model on the **My predictions** tab in the Intelligence area of navigation in Customer Insights.

> [!div class="mx-imgBorder"]
> [![Screen image of the My Predictions tab of Intelligence area in Customer Insights.](../media/my-predictions.png)](../media/my-predictions.png#lightbox)

### Prediction results

Once initial training has completed, you should review the results of the prediction model. Select the model for review and choose **View** from the options.

:::image type="content" source="../media/view.png" alt-text="Screen image of right-click menu with View highlighted.":::

You'll find three primary sections of data on the results page: training model performance, churn risk by percentile and most influential attributes.

**Training model performance**: A, B, or C are possible scores. This score indicates the performance of the prediction and can help you make the decision to use the results stored in the output table.

![Screen image showing the model score of a successful model.](../media/performance.png)

Scores are determined based on the following rules:

- **A** when the model accurately predicted at least 50% of the total predictions, and when the percentage of inaccurate predictions for customers who became dormant is lower than 10%.

- **B** when the model accurately predicted at least 50% of the total predictions, and when the percentage of inaccurate predictions for customers who became dormant is greater than 10%.

- **C** when the model accurately predicted less than 50% of the total predictions.

**Churn risk by percentile**: Groups of customers based on their predicted risk of churn. This data can help you later if you want to create a segment of customers with high churn risk. Such segments help you to understand, for example, where your cutoff should be for customer retention segments.

![Screen image of a chart displaying churn risks.](../media/churn-risk.png)

**Most influential factors**: There are many factors that are considered when creating your prediction. Each of the factors has its importance calculated for the aggregated predictions that a model creates. You can use these factors to help validate your prediction results. You can also use this information to create segments that could help influence churn risk for customers.
