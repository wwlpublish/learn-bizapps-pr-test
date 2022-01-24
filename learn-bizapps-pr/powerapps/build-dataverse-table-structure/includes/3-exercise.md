In this exercise, you will create two more custom tables to store more data for your employee accident tracking application.

>[!NOTE]
> If you haven't completed the previous modules within this learning path, download the [packaging files](https://github.com/MicrosoftDocs/mslearn-developer-tools-power-platform/tree/master/power-apps/create-dataverse-table). These files contain the completed work on the Accident Tracking app thus far.

### Create a custom LocationTable

Follow these steps to create a custom **LocationTable**:

1. On the main menu, expand **Dataverse** and then select **Tables**.

1. Select **+ New table**.

1. Enter the following information:

    - **Display name** - LocationTable

    - **Plural display name** - This field will automatically populate. You can choose to modify it, but for this exercise, you will use the default.

    - **Primary Name Column > Display name** - LocationId (The primary name is the column that displays for users when they select records from this table. Also, this column is shown on the **many** side when a lookup column is used.)

1. Select **Create**.

1. Under the **Columns** tab, find and select the **LocationId** field.

1. On the **Columns** tab, change the **Data type** dropdown menu from **Text** to **Autonumber**.

1. On the **Autonumber type** dropdown menu, select **String prefixed number**.

1. In the **Minimum number of digits** field, enter **4**.

1. In the **Seed value** field, enter **1000**.

1. Now that your **LocationTable** has been created, select **+ Add column** and then create the following columns:

    - **Display name** - LocationName

    - **Data type** - Text

    - **Required** - Required (you want to prevent users from entering a location record without a name)

    - **Searchable** - Yes

    - **Display name** - LocationCountry

    - **Data type** - Choice

    - In the **Choice** field, select the **+ New choice** button to create a new set of choices to store the different countries that Contoso has locations in.

        > [!div class="mx-imgBorder"]
        > [![Screenshot of the Choice field and New choice menu option highlighted.](../media/13-new-choice.png)](../media/13-new-choice.png#lightbox)

As a good practice, name your custom choice with a prefix to help identify it as a choice object later.

1. In the **Display name** field, enter **ChLocationCountry**.

1. Select **View more** and then make sure that the **Global choice** option is selected. (With the **Global choice** option, you can use the custom choice in different table contexts within the same Dataverse environment. With the **Local choice** option, you can only use the custom choice in this table context only.)

    > [!div class="mx-imgBorder"]
    > [![Screenshot of ChLocationCountry entered in the Display name field and the Global choice option selected.](../media/14-location-country.png)](../media/14-location-country.png#lightbox)

1. In the **Items** section, select **Add new item** and then enter **USA**.

1. Select **Add new item** and then enter **SPAIN**.

    > [!NOTE]
    > You can add more choices for countries, but for this example, you will use USA and SPAIN.

    > [!div class="mx-imgBorder"]
    > [![Screenshot of USA and Spain options listed as new items.](../media/15-items.png)](../media/15-items.png#lightbox)

    > [!NOTE]
    > Choice fields are beneficial when the number of options is limited and when items change infrequently or not at all.

1. Select **Save**.

    - **Default value** - \[No default value\]

        (This setting is useful if you want to always display a location as the default, such as the most common country where locations exist.)

    - **Required** - Required (you want to prevent users from entering a location record without a location)

    - **Searchable** - Yes

1. Select **Save Table** to ensure that your changes are saved.

### Create a custom TypeofAccident table

To create a custom **TypeofAccident** table, follow these steps:

1. On the main menu, expand **Dataverse** and then select **Tables**.

1. Select **+ New table**.

1. Enter the following information:

    - **Display name** - TypeofAccidentTable (You don't need to enter the *Table* suffix; you're only doing so as a preference for this exercise.)

    - **Plural display name** - This field will automatically populate. You can choose to modify it, but for this exercise, you will use the default.

    - **Primary Name Column > Display name** - TypeofAccidentId (The primary name is the column that is shown to users when they select records from this table. Also, the column is shown on the **many** side when a lookup column is used.)

1. Select **Create**.

1. Under the **Columns** tab, find and select the **TypeofAccidentId** field.

1. On the **Columns** tab, change the **Data type** dropdown menu from **Text** to **Autonumber**.

1. On the **Autonumber type** dropdown menu, select **String prefixed number**.

1. In the **Minimum number of digits** field, enter **4**.

1. In the **Seed value** field, enter **1000**.

1. After the **TypeofAccidentTable** has been created, you can select **+ Add column** and then create the following columns:

    - **Display name** - AccidentName

    - **Data type** - Text

    - **Required** - Required

    - **Searchable** - Yes

    - **Display name** - AccidentSeverity

    - **Data type** - Choice

    - **Choice** - Create a new choice option called **ChAccidentSeverity** and then add five new items. Items are numbered from one to five.

    - **Default value** - \[No default value\]

    - **Required** - Required

    - **Searchable** - Yes

1. Select **Save Table** to ensure that your changes are saved.
