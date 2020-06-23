In addition to the out-of-the-box visualizations you see in Power BI Desktop, the Microsoft AppSource has a vast library of custom visuals that you can import into Power BI Desktop. These custom visuals give you a wider choice of options when it comes to using advanced analytics. There might be a custom visual that solves a business problem that the standard visuals cannot solve, or one that presents your data in a way that the standard visuals cannot.

> [!NOTE]
> Some organizations prefer not to use custom visuals at all, or only permit certain custom visuals, for security or other reasons. Before you import any custom visuals, check with your organization to see if they are allowed or not. If they are not allowed, you can still create reports in desktop with them, but they will not render in the Power BI Service.

You already imported a custom visual from the Microsoft AppSource in an earlier unit, for the purposes of time series analysis. In this unit, you'll focus on the range of Advanced Analytics custom visuals that are available. These custom visuals include box-and-whisker plots, variance charts, hierarchical trees, Gantt plots, clustering plots, and much more; the list goes on. Using advanced analytics visuals adds a layer of complexity to your reports, and allows you to further analyze the data and develop granularity within your visuals.

In this example, you've produced some charts and visuals for the Customer Service team but now they want you to create a variance chart, so they can study the variance in the Help tickets. You decide to browse the Microsoft AppSource to see if there is an advanced analytics visual you can use to satisfy this request.

In the **Visualizations** pane, select the **Get more visuals** icon, then select **Get more visuals**. On the **Power BI Visuals** window that displays, select the **Advanced Analytics** category. Browse the available options, then select the **Add** button for the visual you want to import. In this example, you add the **Variance Chart** custom visual.

> [!div class="mx-imgBorder"]
> [![Add advanced analytics custom visual](../media/8-add-advanced-analytics-custom-visual-ssm.png)](../media/8-add-advanced-analytics-custom-visual-ssm.png#lightbox)

When imported, an icon for the new custom visual displays under the other visual icons in the **Visualizations** pane.

> [!div class="mx-imgBorder"]
> [![Add variance chart custom visual to report](../media/8-add-variance-chart-custom-visual-report-ssm.png)](../media/8-add-variance-chart-custom-visual-report-ssm.png#lightbox)

You can then add fields to the new visual and customize the visual, in the same way you would for any other visual. In this example, you add **Country** to the **Category** field, add **Gross Sales** to the **Primary Value** field, and add **Net Sales** to the **Comparison Value** field.

You then see that you have a variance visual that contains multiple charts, which is something you couldn't do without importing the Advanced Analytics custom visual from the AppSource.

> [!div class="mx-imgBorder"]
> [![Set up advanced analytics custom visual](../media/8-set-up-advanced-analytics-custom-visual-ssm.png)](../media/8-set-up-advanced-analytics-custom-visual -ssm.png#lightbox)

