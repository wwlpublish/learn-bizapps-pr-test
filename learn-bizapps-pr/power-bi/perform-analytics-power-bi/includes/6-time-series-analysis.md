In 2004, Hans Rosling presented a Ted Talk titled "*The best stats you've ever seen*." It went on to be the most watched talk of all time. In that talk, he showed a video that allowed him to analyze data over time by playing an animated chart. The chart would progress year by year, and you could watch how the longevity and family size moved over time for the entire world. This presentation kicked off a tremendous interest in the power of data visualization, particularly as it related to time series analysis.

Time series analysis involves analyzing a series of data in time order, to identify meaningful information and trends, and make predictions. The result of time series analysis is the best data you can use for forecasting activities.

Time series analysis often involves the use of visuals such as Gantt charts, project planning, and stock movement datasets. In Power BI, you can use visuals to view how your data is progressing over time, which in turn allows you to make observations, such as if there were any major events that disrupted your data.

To conduct a time series analysis in Power BI, you need to use a visualization type that is suitable for displaying trends and changes over time, such as a line chart, area chart or scatter chart. You can also import a time series custom visual into Power BI Desktop from the Microsoft AppSource. The following example uses a standard scatter chart.

In addition to the range of time series custom visuals, the Microsoft AppSource has an animation custom visual called **Play Axis** that works like a dynamic slicer, and is an interesting way to display time trends and patterns in your data, without any user interaction. This visual is very similar to the visual that Hans Rosling used in his original presentation, and is used alongside the scatter chart in the following example.

Note: Some organizations prefer not to use custom visuals, for security or other reasons. Before you import any custom visuals, check with your organization to see if they are allowed or not. If they are not allowed, you can instead use the Play Axis that is available for **Scatter chart** visualizations within Power BI Desktop, as it has similar functionality.

> [!div class="mx-imgBorder"]
> [![Play Axis option on Scatter chart](../media/6-play-axis-option-scatter-chart-ssm.png)](../media/6-play-axis-option-scatter-chart-ssm.png#lightbox)

In this example, you are developing a Sales report, and the Sales team is specifically interested in being able study the quarterly sales trends, to identify which models sell better, depending on the time of the season. You decide to use two visuals, a scatter chart and line chart, for the purpose of time series analysis, and then enhance those visuals with animation, so the Sales team can see how the sales data changes across time.

You start by adding your visuals to the report page, to show the sales data.

> [!div class="mx-imgBorder"]
> [![Scatter and Line charts](../media/6-scatter-line-charts-ss.png)](../media/6-scatter-line-charts-ss.png#lightbox)

Next, you need to import the animation custom visual to use with the visuals. In the **Visualizations** pane, select the **Get more visuals** icon, then select **Get more visuals**. On the **Power BI Visuals** window that displays, search for '*play axis*', then select the **Add** button for the **Play Axis (Dynamic Slicer)** visual.

> [!div class="mx-imgBorder"]
> [![Import custom Play Axis visual to Power BI desktop](../media/6-import-custom-play-axis-visual-ss.png)](../media/6-import-custom-play-axis-visual-ss.png#lightbox)

You'll see a message that tells you the visual was successfully imported. When you return to Power BI Desktop, you'll see the new **Play Axis** icon in the **Visualizations** pane. Select the page, then select the **Play Axis** icon to add that visual to the page.

Next, with the new visual selected, select the field (**Quarter**) that you want to use as the slicer in the **Play Axis** animation. Animation controls become available on the visual.

> [!div class="mx-imgBorder"]
> [![Play Axis visual animation](../media/6-play-axis-visual-animation-ss.png)](../media/6-play-axis-visual-animation-ss.png#lightbox)

You can now resize and reposition the new visual, and customize its formatting, so it is consistent with the other visuals on the page. Here are some specific formatting options you might want to use:

-   In the **Animation Settings** section, you can control the play functionality of the **Play Axis** visual, such as make the animation automatically start, continue looping and change the speed at which the animation occurs.

-   In the **Colors** section, you can change the appearance of the **Play Axis** visual by adjusting its overall color or selecting the **Show all** option, then changing the color of each control button.

-   The Enable Caption On section allows you to turn on/off the text displayed next to the visual or adjust the formatting of it.

> [!div class="mx-imgBorder"]
> [![Play Axis visual format options](../media/6-play-axis-visual-format-options-ss.png)](../media/6-play-axis-visual-format-options-ss.png#lightbox)

When you have set up the **Play Axis** visual to meet your requirements, you are ready to use it with your other visuals. Select the **Play** button, then sit back and watch how the data in each visual on the page evolves over the time. You can use the control buttons to pause the animation, restart it, and so on.

> [!div class="mx-imgBorder"]
> [![animated play axis visual](../media/6-animated-play-axis-visual.gif)](../media/6-animated-play-axis-visual.gif#lightbox)