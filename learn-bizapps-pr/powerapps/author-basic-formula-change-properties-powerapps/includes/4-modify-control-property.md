When working with controls, you can modify the way that other controls
function based on another control's properties. This allows users to
provide input that affects their experience. An example would be
providing a drop-down menu so a user could choose small, medium, or large.
Based on this setting, the app could dynamically change the font size
throughout the app. You could also apply the same logic for colors within the app,
locations of controls, or showing or hiding controls based on user
selections. For example, if a user selects a check box for "New Client",
the fields for entering a new client would appear on the screen.

Use the following example to understand control positioning on the
canvas and how to use the user's input to modify it. The control
location on the canvas is based on a combination of two properties: the
X and the Y property.

-   **X** -- The distance between the left edge of a control and the
    left edge of the screen.

-   **Y** -- The distance between the top edge of a control and the top
    edge of the screen.

The **X** and **Y** properties apply to all controls except screens.
Incorporating this functionality gives you more control over how
information is displayed and consumed by users.

1.  Add a **Dropdown** control to your canvas app.

	> Select **Dropdown** and change the **Items** property from **DropDownSample** to Table({Position:"Top"},{Position:"Bottom"},{Position:"Middle"})

2.  On the **Insert** tab, click **Icons** and select the **Check**
    icon.

3.  Set the **Y** property for the **Check** icon.

```
If(Dropdown1.Selected.Position ="Top",150,Dropdown1.Selected.Position = "Bottom",650,400)
```

4.  Test the formula. Select each position from the drop-down menu.
    Notice that the **Check** icon changes its Y position.
