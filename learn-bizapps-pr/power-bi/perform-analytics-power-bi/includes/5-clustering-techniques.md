Clustering allows you to identify a segment (cluster) of data that is similar to each other but very dissimilar to the rest of the data. The process of clustering is different to that of grouping, which you did earlier.

The Power BI clustering feature allows you to quickly find groups of similar data points in a subset of your data. It analyzes your dataset to identify similarities and dissimilarities in the attribute values, then it separates the data that has similarities into a subset of the data. These subsets of data are referred to as clusters.

For example, you might want to look for patterns in your sales data, such as the behavior of customers overall. You can segment the customers into clusters, according to their similarities, such as age or location.

Start by adding the **Scatter chart** visualization to your report, then add the required fields to the visual. In this example, you add the **Order Qty** field to the X-axis, the **Sales** field to the Y-axis, and the **Product Name** field to the **Legend** section. As you can see in the following image, there is a lot of data now in the scatter chart, so it is difficult to see any natural groups.

> [!div class="mx-imgBorder"]
> [![Scatter chart with Product names](../media/5-scatter-chart-product-names-ss.png)](../media/5-scatter-chart-product-names-ss.png#lightbox)

To apply clustering to your scatter chart, select **More options** (...) in the top right corner of the visual, and then select **Automatically find clusters**.

On the **Clusters** window that displays, you can edit the default name, field and description, if required. But in this example, you want to change the number of clusters. As you can see in the following image, the **Number of clusters** box is blank by default, which means Power BI automatically finds the number of clusters it thinks makes the most sense with your data.

> [!div class="mx-imgBorder"]
> [![Default settings in Clusters window](../media/5-default-settings-cluster-window-ss.png)](../media/5-default-settings-cluster-window-ss.png#lightbox)

Enter the number of clusters you want (3) into the box, then select **OK**. Power BI will run the clustering algorithm and create a new categorical field with the different cluster groups in it. Now when you look at the visual, you can more easily see the clusters that are in your data, and proceed to perform analysis on them.

> [!div class="mx-imgBorder"]
> [![Clustering applied to scatter chart](../media/5-clustering-applied-scatter-chart-ss.png)](../media/5-clustering-applied-scatter-chart-ss.png#lightbox)

The new cluster field is added to your scatter chart's legend field well bucket, which you can now use as a source of cross highlighting like any other legend field. You can also find it in your field list and use it in new visuals, just like any other field.

If you want to edit the cluster, right-click the cluster field and select **Edit clusters**.

> [!div class="mx-imgBorder"]
> [![Edit clusters](../media/5-edit-clusters-ss.png)](../media/5-edit-clusters-ss.png#lightbox)

In the above example, when you applied clustering to the scatter chart, you could only use two measures. If you want to find clusters using more than two measures, you can use a table visual instead, add all the fields you want to use, then run the clustering algorithm using the same process.
