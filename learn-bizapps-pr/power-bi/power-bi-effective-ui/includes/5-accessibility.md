More than a billion people in the world live with a disability. Accessibility is about making sure all people, regardless of ability, have equal access to physical and electronic environments and resources.

Some people with disabilities use assistive technology such as screen readers, screen magnifiers, and speech recognition tools. Microsoft ensures that their products, apps, and services offer great experiences to people when they are using assistive technology.

To this end, Power BI supports certain accessibility features you can factor into your report designs. The product allows you to create reports that are usable by the widest possible audience, without the need to adapt them for special accessibility requirement. So, always design with accessibility in mind. And avoid creating a new report version that addresses a particular accessibility requirement. Be sure to consider report consumers who have visual impairments or who rely on keyboard or voice-activated interaction.

Accessible report designs can be met by using suitable format options or by applying built-in accessibility features.

## Styling

To help report consumers with visual impairments, use non-serif fonts and lean toward larger font sizes. To support report consumers with color vision deficiencies, preference the use high contrast colors. Consider using a built-in theme, like "Color blind safe" or "High contrast".

> [!NOTE]
> When the Windows high contrast option is enabled, Power BI automatically applies those settings to reports. However, in some cases Power BI can't automatically detect this setting, in which case the report consumer can manually apply contrast colors using the **View** menu.

By default, data series are distinguished by different colors. You can further distinguish the data series by using line styles or markers.

In the following line chart visual, shapes help distinguish the two data series.

> [!div class="mx-imgBorder"]
> [![Diagram of a line chart visual with two data series. One series uses a circle marker. The second series uses a square marker.](../media/accessibility-styling-markers.png)](../media/accessibility-styling-markers.png#lightbox)

In the following line chart visual, line styles help distinguish the two data series.

> [!div class="mx-imgBorder"]
> [![Diagram of a line chart visual with two data series. One series uses a solid line. The second series uses a dotted line.](../media/accessibility-styling-line-style.png)](../media/accessibility-styling-line-style.png#lightbox)

## Alt text

Alternative text descriptions or *alt text* can describe the appearance and function of report objects to screen reader users. Every report object has an alt text property, which is set in the **General** section of the **Format** options.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Alt Text property in the Format options.](../media/accessibility-alt-text.png)](../media/accessibility-alt-text.png#lightbox)

For data visuals, don't describe specific data points in alt text because data values are likely to change. However, it's possible to assign a measure, which uses Data Analytic Expressions (DAX), to the alt text property. That way, the measure could evaluate the filter context and return a text description of the data.

> [!TIP]
> To learn more about DAX, see the Learn Path [Use DAX in Power BI Desktop](/learn/paths/dax-power-bi/?azure-portal=true).

## Tab order

Ensure the tab order (set in the **Selection** pane) for each page follows a logical sequence, and remove report objects from the tab order if they're purely decorative, like a background shape or image. A well-configured tab order allows screen readers to read aloud relevant objects in a logical order. For data visuals, screen readers always read out the title, visual type, and any alt text.

> [!TIP]
> To help the screen reader experience, keep titles concise yet friendly, and avoid using acronyms and abbreviations.

## Conditional formatting

There are several conditional formatting options you can use to highlight values in grid data visuals, like the table and matrix. The *icon* option helps to convey status with both color and icon.

In the following matrix visual, notice that the **Days sales of inventory** column communicates zero on hand stock by using an icon (exclamation mark) and color (red).

> [!div class="mx-imgBorder"]
> [![Screenshot of a matrix visual with conditional formatting as described in the previous paragraph.](../media/accessibility-conditional-formatting-icon.png)](../media/accessibility-conditional-formatting-icon.png#lightbox)

## Report consumption experience

It's important that report consumers can fully use and interact with your reports. Be sure to educate them on how to:

-   Apply high contrast color themes (use **View** menu).

-   Tab to navigate between report objects on the page.

-   Use many different keyboard shortcuts to shift focus into visuals, navigate between data points, select one or more data points, or clear selections (use **Shift+?** to see a complete list).

-   Use focus mode to zoom into a visual.

-   Show data table to view the underlying data of a visual in tabular format (use **Alt+Shift+F11**).

For more information about accessible report designs, including many helpful tips, see [Design Power BI reports for accessibility](/power-bi/create-reports/desktop-accessibility-creating-reports/?azure-portal=true).
