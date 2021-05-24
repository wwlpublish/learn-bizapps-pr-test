Previously, we connected to our Dataverse for Teams table data and then transformed it. We can build a report with interactive visualizations using the Power BI **Report** view. The report view consists of:

- The **Report** canvas where visualizations are created and arranged (1 in the image).

- The **Filters** pane allows you to filter and only work with subsets of data (2 in the image).

- The **Visualizations** pane where you can select and edit the visualizations (3 in the image).

- The **Fields** pane where you choose the data to include in the visualizations or include as a filter (4 in the image).

- The **Pages** tab where you can create more report canvases (5 in the image).

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power B I Desktop with the report view items numbered.](../media/image-16.png)](../media/image-16.png#lightbox)

The basic steps to add visualizations to the report are:

1. Select a visualization from the **Visualizations** pane.

1. Select and drag the required fields from the **Fields** pane into the Visualizations pane or Filters pane.

1. Move and resize the visualization in the **Report** canvas.

1. Make more edits to the visualization in the visualization pane.

## Add a stacked column chart

1. Select the **Stacked Column Chart** from the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane.](../media/image-17.png)](../media/image-17.png#lightbox)

1. Select and drag from the Fields pane:

    - **Date** field to **Axis**
    - **Total Cost** field to **Values**

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations and Fields panes with Date dragged to Axis and Total Cost dragged to Values.](../media/image-18.png)](../media/image-18.png#lightbox)

1. Notice that the chart is showing the data by years. You can drill in to see the data by quarter and month by selecting the **Go to next level of the hierarchy** icon underneath the chart. In the next step, we edit the chart to show the data by month.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the "Go to next level in the hierarchy" icon highlighted.](../media/image-19.png)](../media/image-19.png#lightbox)

1. With the chart selected in the report canvas, remove the **Year** and **Quarter** under **Axis** so the graph shows the data by month.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the Axis with the date showing only month and day.](../media/image-20.png)](../media/image-20.png#lightbox)

1. Resize the chart in the **Report** canvas by selecting and dragging the indicated border controls. Have the chart fill up the upper left portion of the canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the chart with the bottom-right corner border control selected.](../media/image-21.png)](../media/image-21.png#lightbox)

## Add a line chart

1. Select the **Line Chart** icon in the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the Line chart icon highlighted.](../media/image-22.png)](../media/image-22.png#lightbox)

    > [!NOTE]
    > If you already have a visualization selected in the report canvas, then selecting another visualization will replace it. Make sure not to have a visualization selected by selecting a blank area of the report canvas before creating a new one.

1. Select and drag from the Fields pane:

    For **Axis**
    - Date (remove Year and Quarter)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the axis section with year and quarter removed, leaving month and day.](../media/image-23.png)](../media/image-23.png#lightbox)

    For **Values**
    - Materials
    - Printing
    - Assembly
    - Shipping

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Values section with the values added.](../media/image-24.png)](../media/image-24.png#lightbox)

1. Select and drag to resize the line chart to cover the bottom half of the Report canvas.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the charts with the line chart covering the bottom half of the canvas.](../media/image-25.png)](../media/image-25.png#lightbox)

1. Change the data colors by going to the Visualizations pane, selecting the Format tab, and then expanding **Data colors**. Use the pull-down next to each one and select the following theme colors.

    - **Materials** - Theme color 4
    - **Printing** - Theme color 5
    - **Assembly** - Theme color 6
    - **Shipping** - Theme color 3

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the format tab icon selected and Data colors highlighted.](../media/image-26.png)](../media/image-26.png#lightbox)

## Add a stacked area chart

1. Select the **Stacked Area Chart** icon in the **Visualizations** pane.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Visualizations pane with the stacked area chart icon highlighted.](../media/image-27.png)](../media/image-27.png#lightbox)

1. Select and drag from the **Fields** pane to the **Values** area.

    For **Axis**:
    - Date (Remove Year and Quarter)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the axis area showing the date with year and quarter removed.](../media/image-28.png)](../media/image-28.png#lightbox)

    For **Values:**
    - Total Production Cost
    - Shipping

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the values area with the two fields added.](../media/image-29.png)](../media/image-29.png#lightbox)

1. Change the colors of the are chart to make it consistent with the rest of the report. In the Visualizations pane, select the **Format** tab, then expand **Data colors**. Use the pull-down next to each one and select the following theme colors.

    - **Total Production Cost** - Theme color 2
    - **Shipping** - Theme color 3

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the format tab with data colors selected.](../media/image-30.png)](../media/image-30.png#lightbox)

1. Select and resize the chart in the report canvas to use up the existing space.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the report canvas with the stacked area chart filling the upper right section of the report.](../media/image-31.png)](../media/image-31.png#lightbox)

## Change data to use currency format

Notice the report shows data in the legends and pop-outs as simple numbers without any formatting. It would be more useful to have the data appear as currency.

> [!div class="mx-imgBorder"]
> [![Screenshot of the report with unformatted numbers.](../media/image-32.png)](../media/image-32.png#lightbox)

To change to currency format:

1. Under the **Fields** pane, select the **Assembly** field.

1. In the **Column tools** ribbon, select the **Currency** format icon.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of the Power B I Desktop Column tools tab with the Currency icon highlighted.](../media/image-33.png)](../media/image-33.png#lightbox)

1. Repeat these steps for **Materials**, **Printing**, **Shipping**, **Total Cost**, and **Total Production Cost**.

Once completed, our data shows up as currency.

> [!div class="mx-imgBorder"]
> [![Screenshot of the report with numbers formatted as currency.](../media/image-34.png)](../media/image-34.png#lightbox)

## Save the report

Save the report by selecting **File** > **Save as** in the menu. Type in **Contoso Cost Trends** as a name and then select **Save.** Power BI Desktop uses a **pbix** file extension for its save files.

The final report should look similar to this.

> [!div class="mx-imgBorder"]
> [![Screenshot of the final Contoso Cost Trends report.](../media/image-35.png)](../media/image-35.png#lightbox)
