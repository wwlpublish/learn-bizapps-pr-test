There are numerous design aids to help you lay out your reports. Knowing about these aids and how to use them will help you to reduce report authoring time and produce more visually appealing results. They include:

-   Format commands.

-   The **Selection** pane.

-   Report layout options.

-   Page view.

-   Undo/redo.

## Format commands

On the **Format** contextual ribbon tab (available when you select one or more report objects), there are several commands to help arrange objects on the page.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Power BI Desktop Format contextual ribbon tab.](../media/format-contextual-ribbon.png)](../media/format-contextual-ribbon.png#lightbox)

Use this ribbon tab to manage the layer order for one or more objects, with options to move objects forwards or backwards, or directly to the top or bottom layer. You might overlap visuals when toggling visibility state with bookmarks, or when superimposing objects, like text boxes or visuals, on background shapes.

There are also various options to align objects horizontally or vertically. Well-aligned objects result in a balanced and visually appealing page layout. When a single object is selected, you can align it with the report page; when multiple objects are selected you can align them among themselves. You can also distribute a multi-selection of objects horizontally or vertically, ensuring equal spacing separates the objects. The distribution options require that at least three objects are selected.

Grouping options lets you treat the group like a single object, making moving, resizing, and working with layers in your report easier, faster, and more intuitive. It's possible to group, ungroup, or merge other objects into an existing group.

For more information about grouping visuals, see [Group visuals in Power BI Desktop reports](/power-bi/create-reports/desktop-grouping-visuals/?azure-portal=true).

## The Selection pane

The **Selection** pane has two tabs: **Layer order** and **Tab order**.

### Layer order

In the **Layer order** tab, you can see a list of all objects and groups of objects found on the page, together with the visibility state. The name of each item in the list is either a generic label, like "button" or "slicer", or the object title property, when it's set. Renaming an object in this pane updates the title property.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Selection pane and the Layer order tab. Several objects and groups are listed.](../media/selection-pane-layer-order.png)](../media/selection-pane-layer-order.png#lightbox)

The **Layer order** tab allows you to do many things. As the name of the pane suggests, you can use it to select, or multi-select, objects or groups. Often, it can be easier and quicker to select objects using in the pane instead of selecting the objects on the page, especially for complex, multi-layered layouts.

You can set the visibility state to hide or unhide individual objects or groups. Hiding objects can help unclutter a report page at design time. Bookmarks can capture visibility state, allowing report consumers to control visibility with buttons.

You can also modify the layer order, often referred to as *z-order*. Because it's possible to overlap objects (or groups) on the page, the higher an object is in the list, the closer it is to the front. So, when you have overlapping objects, the one listed first is on top. To change order, drag and drop an object or group to a new position.

Lastly, it's possible to summarize an object, which adds a text box that contains a text description of the visual to the report page. It's similar to what the smart narrative visual does.

### Tab order

The **Tab order** tab allows you to manage tab order.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Selection pane and the Tab order tab. Several objects and groups are listed.](../media/selection-pane-tab-order.png)](../media/selection-pane-tab-order.png#lightbox)

Configure the tab order to keyboard navigation follows (using the **Tab** key) a logical sequence. It also allows screen readers to read aloud the objects in a logical order. It's also possible to remove an object from the tab order. To remove an object from the tab order, click the numeric value at the left of the object.

> [!NOTE]
> Accessibility is described in Unit 5.

## Report layout options

On the **View** ribbon tab, you can enable gridlines, snap to grid, and lock objects. These three options apply to all report pages. Also, these options aren't persisted, so you must re-enable them each time you edit the report.

> [!div class="mx-imgBorder"]
> [![Screenshot of the View ribbon tab, with the page options Gridlines, Snap to grid, and Lock objects.](../media/view-ribbon-tab-page-options.png)](../media/view-ribbon-tab-page-options.png#lightbox)

When **Gridlines** is enabled, visible guides appear that can help you align your visuals. The gridlines can make it easier to determine whether two (or more) visual borders are aligned horizontally or vertically.

When **Snap to grid** is enabled, it helps you align visuals on the page, resulting in a more visually pleasing layout. When you move or resize visuals, the report designer will align them to the nearest gridline.

When **Lock objects** is enabled, it's not possible to resize or move visuals. You might find this option helpful when you want a report reading experience and you want to avoid accidentally modifying the visual layout. When objects are locked, it's still possible to modify the position and size of visuals by using the **Format** options (in the **General** section).

> [!TIP]
> Sometimes *snap to grid* tries to align to visuals in an unintended way. While moving or resizing a visual, you can temporarily override the snap to grid behavior by pressing the **Windows** key.

## Page view

It's possible to scale the report canvas to fit to page, fit to width, or show actual size. Full screen mode isn't an option during report design; it's only supported for report consumers when the report is viewed in the Power BI service or a Power BI mobile app. There's no zoom control to enlarge or reduce the report canvas.

> [!div class="mx-imgBorder"]
> [![Screenshot of the View ribbon tab, and highlights the Page view command.](../media/view-ribbon-tab-page-view.png)](../media/view-ribbon-tab-page-view.png#lightbox)

> [!TIP]
> Whenever possible, use the largest possible monitor size and maximize the Power BI Desktop window. To maximize the report canvas, consider closing or minimizing panes, like the **Fields** pane. You can also collapse the ribbon to the condensed view.

## Undo/redo

Like many Microsoft products, it's possible to undo or redo actions by pressing **Ctrl+Z** or **Ctrl+Y**, respectively. In Power BI Desktop, these options are also available in the quick access area, located at the top-left corner. Don't be afraid to experiment because it's easy to undo the last action(s) you made.

> [!div class="mx-imgBorder"]
> [![Screenshot of the undo quick access command, located at the top-left of the Power BI Desktop window.](../media/undo.png)](../media/undo.png#lightbox)

> [!TIP]
> Many other shortcuts are available in Power BI Desktop. You can press **Shift+?** to see a list of keyboard shortcuts.
