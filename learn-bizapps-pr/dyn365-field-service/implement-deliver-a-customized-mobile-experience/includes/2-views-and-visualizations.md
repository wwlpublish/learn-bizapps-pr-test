Views are used throughout the mobile application. They are used when you want to specific to see items like a list of the available bookings available for a specific technician. They can also be used to provide additional details about an item such as displaying related data associated with a work order.

There are several view types that can be used:

-   **Dashboard View:** Shows views and charts that were designed and defined for the entities.

-   **Public View:** Displays the selected entity's list of records.

-   **Associated View:** Shows the list of items from the associated entity that are relevant for the selected item and entity.

-   **Lookup View:** Shows the list of items from the entity that should be inserted to the form.

For more about views, see [Views](https://www.resco.net/woodford-user-guide/#__RefHeading__5821_1627906509).

### Binding

When organizations are creating views for the mobile application, they
can define several aspects. These might include items like the
following:

-   **Row Properties:** Rows have multiple properties that can be defined such as modifying the height, width, and color.

-   **Binding Information:** Lets you control what field's data will be used for a view element.

    For example, you could change the binding of an option set field to
    display the numeric value instead of the value. This would let you 
    potentially be able to add images or map pins that could be
    displayed.

 For more about bindings, see [Binding](https://www.resco.net/woodford-user-guide/#__RefHeading__5825_1627906509).

### View configurations

-   **Defining the kind:** Let's you define what kind of data will be displayed in a specific field for a view. This could include text, image, or a map pin that might be used in a map view.

-   **Add action buttons:** Buttons can be configured, so when a record on view is selected, the button could be used to do something like create a child record or set the status of a record.

-   **Edit Filter:** Edit Filter can restrict the displayed data in the view to only those that meet the specified conditions.

-   **Edit Sort:** Edit Sort defines the direction of sorting (Ascending or Descending) and which field will be used for it.

-   **Edit Search:** In Edit Search, you can define where (which field) will the application search for the character entered in the application's search field.

-   **Date Fields:** In Date Fields, you can specify which fields will be used as Start and End date fields in case you need to add the view to Calendar. Since it is possible to add any entity to calendar, this is a good way for you to set the appropriate field to be used as Start and End date on Calendar.

For additional view actions, see [View Configurations](https://www.resco.net/woodford-user-guide/#__RefHeading__5829_16279065090).

### Multiple views

Sometimes technicians may need to access data for a specific entity in multiple ways. For example, a technician might have work orders in multiple cities throughout the day such as Seattle, Redmond, or Bellevue. With multiple views, the default public view could display all account records in Washington, while additional views could be created
to show only a subset of the data each city with different potentially different fields for each.

For more about working with multiple views, see [Multiple Views](https://www.resco.net/woodford-user-guide/#__RefHeading__5831_1627906509).

### Row scripts

One challenge that can arise, is not being able to easily identify statuses of items. For example, let's say that a technician is on site to install 4 items. Each item is listed on the work order as a product. It can be challenging to quickly identify which specific product has or has not been installed. One way this can be done is with row scripts.
Row scripts allow us to add logic to views that can be used to change the visual appearance of rows.

Since each row that is displayed in a view can have its own properties
defined, it would be possible to create three rows for one view:

-   **Default:** Displays a product with no formatting at all

-   **Estimate:** Highlights the row in red when a product is in an estimate status

-   **Used:** Highlights the row in green when a product has a status of used.

Using the Row script button on the view, we could define when to display the estimate, used, or default rows. Now when a technician is looking at the products associated with a view, they can easily see at a glance the
status of the product.

For more about row scripts, see [Row Scripts](https://www.resco.net/woodford-user-guide/#_Toc483815916).
