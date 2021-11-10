The input variables already had associated steps, but it's difficult to define an output variable when you're recording actions because the goal is to get information rather than do an action such as clicking. A new action within the process is required to set an output variable. Ensure that the desktop application that is relevant to your flow is running during this process. On the Actions Pane, expand **UI automation** and **Data extraction**. Select and drag **Get details of a UI element in window** to the appropriate step in your flow (for the Contoso Invoicing flow, this placement will be between steps 8 and 9).

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate for desktop showing how to drag an action to a step.](../media/17-drag-step.png)](../media/17-drag-step.png#lightbox)

In the next dialog box, select the down arrow to expand options and then select **Add a new UI element**.

> [!div class="mx-imgBorder"]
> [![Screenshot of Get details of a UI element in window dialog box with the UI element expanded and the Add a new UI element button highlighted.](../media/18-expand-options.png)](../media/18-expand-options.png#lightbox)

The Power Automate designer will minimize, revealing your desktop application and a small window that contains your tracking session. Unlike when you record actions, the tracking session is looking for you to select an element to capture. You can take actions without affecting the tracking session. To choose the element, hover over it until you see a red border, hold down the **Ctrl** key, and then select the element (in this case **Invoice ID**) to record it in the tracking session.

> [!div class="mx-imgBorder"]
> [![Screenshot of Contoso Invoicing with Invoices selected and Invoice ID highlighted.](../media/19-invoice-id.png)](../media/19-invoice-id.png#lightbox)

When the selected element displays in the **Tracking session** window, select **Done**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Tracking session window with the Done button highlighted.](../media/20-done-ui-element.png)](../media/20-done-ui-element.png#lightbox)

The **Tracking session** window will disappear, leaving the Power Automate designer and the edit dialog box for the **Get details of a UI element in window** dialog box. Select **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Get details of a UI element in window dialog box with the Save button highlighted.](../media/21-save-ui-element.png)](../media/21-save-ui-element.png#lightbox)

This action will automatically create a variable called AttributeValue as an output that you can refer to in later actions within Power Automate for desktop.

When you retrieved the element (**Invoice ID**) from the application, a specific value was returned based on a new invoice that was being created. To ensure that your value can be dynamic, you need to perform a few more steps.

Select the stacked paper icon on the right side of your screen. Find the element that you selected. The element should start with **Text** and the text that you added should be encased in single quotation marks, as shown in the following screenshot. Select the ellipsis (**...**) and, in the menu, select **Edit selectors**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the UI elements dialog box with the stacked paper icon highlighted.](../media/22-stacked-paper.png)](../media/22-stacked-paper.png#lightbox)

In the next dialog box, hovering over the text will reveal the ellipsis (**...**). Select the ellipsis and then select **Edit selector**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Selectors of UI element "Text '1030" dialog box with the Edit selector option highlighted.](../media/23-edit-selector.png)](../media/23-edit-selector.png#lightbox)

Select the element that you want to edit and ensure that the **Name Equal to 1030** (or your text) isn't selected. This factor allows the value to be dynamic instead of static. Select **Update** and then close the **Edit selector** dialog box.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Selector builder dialog box.](../media/24-selector-builder.png)](../media/24-selector-builder.png#lightbox)

Now that you're gathering a dynamic UI element, you can set the output variable. On the Actions Pane, expand **Variables** and then select and drag **Set variable** after the **Get details of a UI element in window** step.

> [!div class="mx-imgBorder"]
> [![Screenshot of Power Automate for desktop showing the Set variable action being dragged to the steps.](../media/25-set-variable-output.png)](../media/25-set-variable-output.png#lightbox)

You can now set the output variable that you defined in the previous unit. Setting the output variable will allow you to use it in downstream processes such as a cloud flow. To set the variable, put the variable name between two percentage symbols: **%InvoiceID%**. You can fill in the **To:** field in a similar manner or by using the **{x}** button. Select **Save**.

> [!div class="mx-imgBorder"]
> [![Screenshot of the filled-in Set variable dialog box.](../media/26-set-variable-output-2.png)](../media/26-set-variable-output-2.png#lightbox)

If you forget the names of your variables, you can always see them by selecting {x} in the upper-right corner of Power Automate designer.

You now know how to define and set both input and output variables. These variables will allow you to make your desktop flows more powerful and dynamic.

**Save** and **Run** your flow to see your work in action.
