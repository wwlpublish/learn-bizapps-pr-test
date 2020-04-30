The **Edit Form** control has three different display modes: **View**,
**Edit**, and **New**. Each mode has some difference in the options
available and affects the form's behavior.

-   **View mode** -- In this mode, the form will present the information
    for the record, but the fields will not be editable. The controls on
    the cards will present themselves with their view behavior. For
    example, the **Input** control will present without a border around
    the text.

-   **Edit mode** -- In this mode, the form will present the information
    for the record, and all the editable fields will be editable.
    Remember, a form can have a mixture of editable and non-editable
    fields. The controls on the cards will present themselves with their
    edit behavior. For example, the **Input** control will present with a
    border around the text. This gives the user a visual clue they can
    edit the data. The **Default** property of the **Input** control
    determines the data shown in the control.

-   **New mode** -- In this mode, the form will present all of the
    fields for a record, but the fields will be blank. The user will
    enter new data and create a new record. The controls on the cards
    will present themselves with their edit behavior. For example, the
    **Input** control will present with a border around the text, giving
    the user a visual clue that they can input data.

Controlling form modes
----------------------

A **Form** control has a default mode. You set the default mode using the
**Edit** panel. The form mode can also be changed dynamically using a
series of Power Apps functions. Each function is responsible for setting
the mode to a specific value.

-   ViewForm(YourFormName) -- Puts the form in **view** mode.

-   EditForm(YourFormName) -- Puts the form in **edit** mode.

-   NewForm(YourFormName) -- Puts the form in **new** mode.

Use these functions to have a single form used for displaying, editing,
and creating records. The way the user would toggle the modes is through
a group of button controls placed on the screen.

![New Form](../media/new-form.png)

Now you have allowed the user to stay on the same screen but interact
with the data differently based on their needs. The SharePoint
customized list forms work exactly this way, providing one form for all
user activities. To take the scenario one step further, you could
incorporate conditional logic. One button could toggle through the
different modes, but that is beyond the scope of this lesson.