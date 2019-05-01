<!---TODO: Remove 
## Learning objectives

At the end of lab, you will be able to perform the following tasks: 
- Install a power BI app
- Filter a Power BI dashboard
- Analyze the data that makes up a visual
- Sort data and apply cross-filtering to a report

Estimated time to finish this lab: 20 to 30 minutes
---->

## Scenario

Congratulations. You are the new sales manager at a clothing manufacturing company named *Van Arsdel*. Your first assignment is to analyze your sales and marketing data to find why there is an unexpected dip in June sales. 

## Procedure

### Add the Sales and Marketing Sample app

**Note:** If you already have the **Sales and Marketing sample** app installed, please skip to the next section.

1. Sign in to [http://app.powerbi.com](http://app.powerbi.com).
2. Select the **Apps** tab on the left.
3. Select the **Get apps** button.
4. Select “**Find more apps and consulting services at AppSource**” link at the bottom of the menu.
5. Search for “_Sales and Marketing sample_”  

![Image of the sample app for this lab.](../media/lab-2/power-bi-top-app-results.png)

6. From the **Install this Power BI app?** prompt, select the **Install** button.
7.  Select the “**Get it now**” link and wait for the app to install.
8. From the **Get started with your new app** screen, select the **Explore App** button. 
9.  Select the **Apps** tab on the left and then select the **Sales and Marketing sample** app tile.
10.  The first time you launch the app, you will see **Get started with your new app**
11.  Select the **Explore app** button to explore the dashboard.

 ### Apply a filter to a report page

In this section, you will explore two questions:

*   Why did our company, VanArsdel, underperform in June?
*   What are our best growth opportunities?

1.  In the **Sales and Marketing sample** app, start on the **YTD Category** report page by selecting the **YTD Category** tab at the bottom from any report (or by selecting the **Total Units YTD** visual from the dashboard).

![Image of the YTD Category report.](../media/lab-2/power-bi-ytd-category-report.png)


2. Notice the anomaly in the **Total Units by Month and Manufacturer** chart. 

![Image of a dip for Van Arsdel only in June.](../media/lab-2/power-bi-june-dip.png)

3.  If it is not already open, open the Filters pane by selecting **Filters** from the right side of your report.

4. Power BI displays all filters that the report designer applied to that visual.

![Image of available filters for the visual.](../media/lab-2/power-bi-lab-filters.png)

5. The report designer filtered for Van Arsdel and our top three competitors and for the year 2014. That is good but she also filtered for the *Central region* and you want to see all of the regions. Clear the **Region** filter by clicking the eraser icon on that filter.

![Image of the Region filter.](../media/lab-2/power-bi-region-filter.png)

6. Mouse over the **Total Units YTD by Manufacturer and Region** and note which segments in which Van Arsdel competes. Note that we compete in *Moderation* and *Convenience*.

![Image of hover mouse-over image of Total Units by segment.](../media/lab-2/power-bi-hover-1.png)

7. Hover over our competitors to see segments in which they compete. Do you see any patterns?

![Image of hover mouse-over image of Total Units by segment.](../media/lab-2/power-bi-hover-2.png)

8.  Explore the same question just for the month of June. To cross-filter this report page for June, in the **Total Units by Month and Manufacturer** visual, click on the label **June-14**. Notice that all of the visuals in this report page update for June. 

![Image of cross-filter for June.](../media/lab-2/power-bi-crossfilter-for-june.png)

9.  Notice the cross-highlighting of the **Total Units YTD by Manufacturer and Region** visual. 

![Image of cross-filter on Total Units YTD visual.](../media/lab-2/power-bi-visual-crossfilter-highlights.png)

10.  Hover over each company to see the pattern of segments during June.

11.  What can you conclude about the two most successful segments in June and why are our total sales dipping during that time?

12.  To explore the same question in a different way: go to the **Growth Opportunities** report by selecting the **Growth Opportunities** tab.

13. Hover over the **Total Units by Segment** bar chart visual and then select the "Drill Up" icon (the up arrow) to see "Total Units by Manufacturer". 

![Image of the "Filter Up" icon.](../media/lab-2/power-bi-filter-up-icon.png)

14. Clear the **isVanArsdel** and the **Segment** filters by clicking the eraser icons. This will allow us to see all of the companies and segments. Notice that Van Arsdel is the leading manufacturer overall. 

![Image of the unfiltered "Total Units by Segment" visual.](../media/lab-2/power-bi-total-units-manufacturer.png)

15.  Cross-filter for June on the **Total Units and Total Units by R12Ms by Month** visual by selecting **June-14**. Notice once again how Van Arsdel did in June.

![Image of the cross-filtered view of sales in June.](../media/lab-2/power-bi-crossfilter-june-total-units.png)

16. Drill down to view segments in June by clicking the "Click to turn on Drill Down" icon and then the "Go to the next level in the hierarchy" icon. 

![Image of the drilldown icons.](../media/lab-2/power-bi-drilldown.png)

17. Once again, what segments are the most successful in June.

![Image of the units-by-segment-june.](../media/lab-2/power-bi-segments-in-june.png)

18. Why are Van Arsdel sales failing in June? What could we do to better compete? 