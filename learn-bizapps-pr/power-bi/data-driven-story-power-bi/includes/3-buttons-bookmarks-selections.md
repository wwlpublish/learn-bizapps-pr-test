You can use the **Bookmarks**, **Buttons** and **Selections** features in Power BI Desktop to make your report more interesting and interactive, and easier for users to navigate.

-   **Bookmarks** capture the currently configured view of a report page, so you can quickly return to that view later. You can use bookmarks for different reasons. For example, you can use them to keep track of your own progress when you are creating reports. You can also use them to build a PowerPoint-like presentation that goes through the bookmarks in order, thereby telling a story with your report.

-   **Buttons** create a more interactive experience for the report users. With the addition of buttons that have assigned actions, your report behaves similar to an app, where users can hover, click, and interact more with the content.

-   **Selections** allow you to determine what items in the report are visible and what items are hidden. Selections are used alongside bookmarks and buttons.

Suppose you have designed a report page and you want to have a second page that looks almost the same, except that one of the visuals is different. Rather than creating a second page and manually making changes, you can use a combination of selections, bookmarks and buttons to switch between the two visuals on the one page.

## Add bookmarks

When you add a bookmark, the following elements are saved with the bookmark:

-   Current page

-   Filters

-   Slicers, including slicer type (for example, dropdown or list) and slicer state

-   Visual selection state (such as cross-highlight filters)

-   Sort order

-   Drill location

-   Visibility of an object (by using the Selection pane)

-   Focus or Spotlight modes of any visible object

In this example, you want to add bookmarks to allow users to switch between two visuals on one page. You first need to set up the page how you want it to display initially.

When you have added and formatted all of the visuals and other items on the page, you can add a bookmark to capture a snapshot of the page in its current state.

Before adding a bookmark, go to the **View** tab in the ribbon and select **Selection**. In the **Selection** pane that displays, you'll see a list of all of the items on your page, along with an eye icon that indicates the items that are currently visible. You can rename the items in the list by double-clicking on them, so you clearly know which one is which.

Now you are ready to add the bookmark. Again on the **View** tab, select **Bookmarks**. On the **Bookmarks** panel that displays, select **Add**. It's good practice to rename the new bookmark, so its purpose is clear, this is especially true if you plan on adding multiple bookmarks. To rename a bookmark, simply double-click the bookmark and enter the new name. In this example, you want to change the bookmark name from *Bookmark 1* to *Variance Chart* because the **Variance** chart is the main focus of the page, as you can see in the following image. In the **Selection** pane the **Variance** chart is displaying and the other visuals are hidden.

> [!div class="mx-imgBorder"]
> [![Add bookmark](../media/3-add-bookmark-ssm.png)](../media/3-add-bookmark-ssm.png#lightbox)

Now it's time to make the second bookmark. You start by making changes to how the page currently looks. In this example, you add another bookmark for the main dashboard charts. As you only want to see charts from the main dashboard, you hide the **Visual** chart by selecting its eye icon on the **Selections** pane. You then add a bookmark for this new view of the page, and rename it as **Main Dashboard**.

> [!div class="mx-imgBorder"]
> [![Select items to see with Main Dashboard bookmark](../media/3-select-items-dashboard-bookmark-ssm.png)](../media/3-select-items-dashboard-bookmark-ssm.png#lightbox)

Now you can switch between the two bookmarks to see the difference in the page.

> [!div class="mx-imgBorder"]
> [![Main Dashboard with buttons added](../media/3-main-dashboard-buttons-added-ssm.png)](../media/3-main-dashboard-buttons-added-ssm.png#lightbox)

You can repeat these steps to add more bookmarks. In summary, you select items you want to show/hide on the report page, then add a bookmark and give it a descriptive name.

You can now assign those bookmarks to buttons to allow users to switch between the bookmarks. You'll learn how to add buttons in the next section.

## Add buttons

You can use buttons for many reasons, such as to switch between two visuals in a report (as required in the previous example), to drill-down into the data in a visual or to move from one page in your report to another. Power BI Desktop provides a range of types of buttons you can add to your report, as illustrated in the following image.

> [!div class="mx-imgBorder"]
> [![Button options](../media/3-button-options-ssm.png)](../media/3-button-options-ssm.png#lightbox)

In this example, you want to add customized buttons that are used to switch between two bookmarks. To add a button, go to **Insert** tab on the ribbon and select **Buttons**, then select the type of button you want to add from the list, in this case you select the **Blank** option.

When the button is added to the page, reposition the button to above the visual, on the right side. Next, select the button, and then in the **Visualizations** pane, move the **Button Text** slider to the **On** position. Expand the **Button Text** section, and then type the text you want to display on the button, for example *Main Dashboard*. You can then format the button text by changing its font, color, alignment and text size. Expand the **Background** section and select a suitable color for the button.

> [!div class="mx-imgBorder"]
> [![Enable and customize button text](../media/3-enable-customize-button-ssm.png)](../media/3-enable-customize-button-ssm.png#lightbox)

Now you add an action to the button. Go to the **Action** slider near the bottom of the **Visualizations** pane and move the slider to the **On** position, then expand the **Actions** section to view the options. The options for the button action types are listed below, and some of these options are explained in more detail in the subsequent sections.

-   **Back** - Returns the user to the previous page of the report. This option is useful for drill-through pages or pages that are all accessed from one main page.

-   **Bookmark** - Presents the report page that's associated with a bookmark that is defined for the current report.

-   **Drill through** - Brings the user to a drill-through page that is filtered to their selection, without using bookmarks.

-   **Page navigation** - Brings the user to a different page within the report, also without using bookmarks, which is an effective way to create a navigation experience for your report users. You will take a closer look at this type of button in the next unit.

-   **Q&A** - Opens a **Q&A Explorer** window, which allows users to type questions to quickly find the information they are looking for, and specify the type of visual they want to see that information displayed in. This option can be useful if you want to save space in the report but still offer **Q&A** functionality to the user.

-   **Web URL** - Opens a website in a new browser window. For example, you might want to give users quick access to your organization's website or Intranet from within a report.

In this example, you select **Bookmark** as the action type. In the **Bookmark** list that displays, select the bookmark that you want to assign to the action - the **Main Dashboard** bookmark you created earlier. For enhanced accessibility, you should add a tooltip that users will see when they hover over the button but in this case, it's not required, as you have a descriptive button label.

> [!div class="mx-imgBorder"]
> [![Assign bookmark as action for button](../media/3-assign-bookmark-action-ssm.png)](../media/3-assign-bookmark-action-ssm.png#lightbox)

Now that your button is all set up, you can copy and paste the button, so you have two buttons with consistent formatting on the page. In this example, you rename the second button to *Variance Chart* and change the assigned action to the **Variance Chart** bookmark.

You can then reposition the buttons anywhere on your canvas but in this example, you position the new buttons on the left side of the canvas, for easy navigation.

> [!div class="mx-imgBorder"]
> [![Two buttons on the left side](../media/3-two-buttons-ssm.png)](../media/3-two-buttons-ssm.png#lightbox)

Your buttons are now ready for use. You can use them to switch between two bookmarks with a different layout on the same page. When you select the **Main Dashboard** button, the main dashboard charts display, and when you select the **Variance Chart** button, the **Variance** chart displays.