# Add forumulas to PowerApps
One of the major benefits of PowerApps is not having to write complicated application code as a developer does. But you still need a way to express logic in an app and to control an app's navigation, filtering, sorting, and other functionality. This is where formulas come in.

If you have used Excel worksheet formulas, the approach that PowerApps takes should look familiar. In this topic, we'll show a couple of basic formulas for text formatting and then walk through three of the formulas that PowerApps includes in the generated app. You will get a taste of what formulas can do, and start to write your own.

## Understanding formulas and properties
In the previous topic, we worked with the Browse screen gallery. Now we're going to work with the Details screen, which is the screen the user selects in order to look more closely at a carpet item. 

The Price field showed up as a plain number without a currency symbol. Suppose we want to add a dollar sign, and also change the text color depending on how much the item costs (for example red if it's more than $5, otherwise green). The following image shows the idea.

![Text formatting for color and currency](media/powerapps-formulas2.png)

Let's start with the currency formatting. By default PowerApps just pulls in a Price value for each item, which is set as the **Text** *property* of the label that displays the price.

1. On the Screens pane on the left, select the Details screen since that is the main screen we want to change (**DetailsScreen1** ).
1. Select the Price control in the app.

   ![Price formatting](media/powerapps-formulas3.png)

 

3. In the Functions bar at the top, select the properties for this control, and then select the **Text** property in the list. The list of properties are the ones that are relevant to the control that is currently selected in your app. You'll see that the Price control is currently set to the number value only and has not been formatted yet to be more helpful. 

   ![Price formatting](media/powerapps-formulas1.png)

4. To add the US currency symbol, replace "Price" with this formula: 

   `Text(Price, "[$-en-US]$ ##.00")`

The formula `Text(Price, "[$-en-US]$ ##.00"` uses the **Text** *function* to specify how the number should be formatted. The formula is like an Excel function, but PowerApps formulas refer to controls and other app elements rather than cells in a spreadsheet.

If you select a control and then select the property drop down list, you see a list of properties that are relevant to the control. For example, here is a partial list of the properties for a label. Some properties are relevant across a broad range of controls and others only for a specific control.


   ![Setting properties](media/powerapps-formulas4.png)

To format the color conditionally based on the price, use a formula like the following for the **Color** property of the label:

 `If(Price > 5, Color.Red, Color.Green)`

## Formulas included in the generated app
Now that you understand how to use formulas in conjunction with properties, we'll look at three examples of formulas that PowerApps uses in the generated app. The examples are all from the browse screen and work with the OnSelect property, which defines what happens when a user clicks or taps an app control.

* The first formula is associated with the **IconNewItem1** control: ![New item icon](media/powerapps-icon-add-item.png). You click or tap this control to go from the browse screen to the edit/create screen and create an item. 
  
  * The formula is `NewForm(EditForm1);Navigate(EditScreen1, ScreenTransition.None)`
  * The formula *instantiates* a new edit form and then navigates to the edit/create screen so that you can create a new item. A value of `ScreenTransition.None` means there is no transition between screens (such as a fade).
* The second formula is associated with the **IconSortUpDown1** control: ![Sort gallery icon](media/powerapps-icon-sort.png). You click or tap this control to sort the list of items in the browse screen gallery.
  
  * The formula is `UpdateContext({SortDescending1: !SortDescending1})`
  * The formula uses `UpdateContext` to update a *variable* called `SortDescending1`. The value of the variable switches back and forth as you click the control. This tells the gallery on this screen how to sort the items (watch the video for more details). 
* The third formula is associated with the **NextArrow1** control: ![Go to details arrow icon](media/powerapps-icon-arrow.png). You click or tap this control to go from the browse screen to the details screen.
  
  * The formula is `Navigate(DetailScreen1, ScreenTransition.None)`
  * The formula navigates to the details screen, again with no transition.

There are many other formulas in the app, so take some time to click on controls and see what formulas are set for various properties.

For more information about these and other functions, see the [formula reference](https://docs.microsoft.com/en-us/powerapps/maker/canvas-apps/formula-reference)

## Wrapping it all up
This brings us to the end of exploring the generated app, and taking a look behind the scenes at the screens, controls, properties, and formulas that give the app its capabilities and even personality. If you've followed along, you should have a better understanding of how a generated app works. Now you can take this understanding into creating your own app.

In the next series of topics, we'll look at how to create versions of your apps.