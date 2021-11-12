One-to-many relationships are the most common Dataverse relationships that you will work with. Using our sample Hot-desking data model, we will explore how to work with them in a canvas app. We will use the relationship between the Location and the Desk. The following is a visualization of the relationship and the corresponding data.

> [!div class="mx-imgBorder"]
> [![Diagram of one-to-many relationship between location record on one side and multiple desk records on many side of the relationship.](../media/many-relationship.png)](../media/many-relationship.png#lightbox)

If you wanted to allow a user to select a location and have that location's desks show below in a gallery, you might create a screen similar to the following:

> [!div class="mx-imgBorder"]
> [![Screenshot of a sample user interface showing a dropdown with locations and Location 1 selected followed by a list of desks at the selected location.](../media/location-1.png)](../media/location-1.png#lightbox)

As with most data sources you could use the Filter() function to filter the desks to only show the desks for the selected location. Your formula would look something like the following:

> [!div class="mx-imgBorder"]
> [![Screenshot of a formula setting up a data source in the previous example.](../media/formula.png)](../media/formula.png#lightbox)

Since we are working with a Dataverse one-to-many relationship, you can instead use the dot notation to reference the location's desks by using Control.Selected.Desks like you can see in the following formula.

> [!div class="mx-imgBorder"]
> [![Screenshot of the alternative formula for Items property of the desk gallery.](../media/alternative-formula.png)](../media/alternative-formula.png#lightbox)

In this example, both formulas produce the same list of desks related to the selected location. Using the dot notation is simpler and more concise than using the filter function.

When you navigate a one-to-many relationship using the dot notation syntax by default, you get all the related records. You can use a filter to apply more criteria to the related rows. The following expression uses the one-to-many relationship and also filters the results on the active status.

`Filter(FilterLocation_1.Selected.Desks, Status= 'Status (Desks)'.Active)`

You can also use the relationship starting from the desk row. Take an example where in the gallery you want to show the location address for each desk. You might be familiar with using a lookup to retrieve the location record and then access the address column as a property.

> [!div class="mx-imgBorder"]
> [![Screenshot of a formula assigned to the text property of a control.](../media/text-formula.png)](../media/text-formula.png#lightbox)

Instead of using Lookup() you can use the dot notation and reference `ThisItem.Location.Address`.

> [!div class="mx-imgBorder"]
> [![Screenshot of the simplifed formula assigning the location address of the desk.](../media/location-formula.png)](../media/location-formula.png#lightbox)

You are not limited to one level of relationship navigation. Take the example of location that has a related primary contact, and you want to show the full name column. You could compose the following formula:

`ThisItem.Location.'Primary Contact'.'Full Name'`

Using the dot notation, you can quickly include related data regardless of which side of the relationship you are starting from.

## Add and update related rows

The easiest way to establish the one-to-many relationship is by using an edit form to create or update the related row. When you add the lookup column to the form, it uses the choices function to present possible values to the user. Take the follow example of adding a desk row where the location lookup column is added to the form.

> [!div class="mx-imgBorder"]
> [![Screenshot of an edit form for Desk record with Location lookup represented by a drop down control.](../media/edit-form.png)](../media/edit-form.png#lightbox)

When you look at advanced properties on the drop-down control, you see how the Items property is configured.

> [!div class="mx-imgBorder"]
> [![Screenshot of advanced properties of the drop down control used for Location lookup column.](../media/advanced-properties.png)](../media/advanced-properties.png#lightbox)

By using choices, you eliminate the need to add the lookup table as another data source. Choices function result is a table so you can add more filtering and sorting like the following:

`Filter(Choices([@Desks].contoso_Location), Status='Status (Locations)'.Active)`

If you already had the lookup value you wanted to set (for example when creating a desk record from location screen), you could set the DefaultSelectedItems property on the data card value and then set the form field's Visible property to off. This would allow the default value to be passed when the SubmitForm() function is invoked.

> [!div class="mx-imgBorder"]
> [![Screenshot of the expression setting the default value for the location in the drop down.](../media/default-value.png)](../media/default-value.png#lightbox)

If you are using the Patch function to set a lookup column you simply set the value of the column to a record from the primary table. In the following example, we are establishing a relationship between a desk row and a primary location row currently selected in the location drop-down:

`Patch(Desks, ThisItem, {Location:FilterLocation_1.Selected})`

You could also achieve the same result using the Relate() function. The first parameter is the list of the rows (desks) related to the primary row (location) and the second parameter is the row (desk) to be added to that list or *related*.

`Relate(FilterLocation_1.Selected.Desks,ThisItem)`

In the same way you could use the Unrelate() function to disassociate the rows, for example remove ThisItem (Desk) from the desks associated with the selected location FilterLocation_1.Selected.

`Unrelate(FilterLocation_1.Selected.Desks,ThisItem)`

When using unrelate, it is important to remember that it will set the value of the primary lookup on the related record to Nothing (or null). You would want to avoid having rows that are orphaned simply because the app may not have the ability to display the row without the primary association. In our example, if the list of desks is displayed only as related to the location, then any desk without a location will be orphaned and not accessible through the app. This can also occur as a side effect of deleting the primary row when the relationship behavior property is configured to remove the link to related rows.

