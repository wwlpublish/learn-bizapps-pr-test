Power Apps provides users with an easy and efficient way to work with their business data and processes. Data is accessed by apps using connectors. Commonly, when an app starts up or a new screen is displayed, some information is retrieved for initial display. Controls on the screens are often bound directly to connectors, and data is retrieved when the screen is rendered for the user. Navigating from screen to screen can also cause the data to be retrieved again. If not optimized, in some cases this can result in a substandard user experience or additional processing. By evaluating your users' needs and how data is loaded, you can develop a strategy to improve performance.

As you evaluate your app, the following are some key considerations:

- **Is the initial data being shown to the user useful?** Often apps makers feel they need to show some data when users arrive at a screen. This behavior can make the app look nice and demos well but is inefficient when much of the time the initial list isn't used. This can result in unintentional slowness of the app when preloading a large quantity of unfiltered records.

- **Does the app offer the right data filters?** Adding controls to allow users to input criteria that reduce the number of rows displayed can be helpful not only for user productivity but also for performance.

- **Are you incurring overhead from showing related data?** If you're using a data source that provides access to relational data and use related values in a gallery, the app might be performing lookup queries for each row shown. You can identify this by running the app with Power Apps Monitor and reviewing the results. Preloading the related data into a collection and then looking up from the collection instead can be more performant.

- **Do you know what data is static and what data is updated frequently?** Before considering preloading data, make sure you know if it's frequently updated. Caching of infrequently changing or static data can help improve the performance of the application by having the data ready when the screen is displayed. Caching data that frequently change, on the other hand, can either have a detrimental impact on the application performance or present stale data to the user.

- **Do you wish to show a loading indicator to the user?** If you're binding data from the connector directly to the control, you don't have the option of showing and hiding a loading indicator like you would if you cached the data in a collection.

- **How much data is going to be loaded from the data source?** If you're considering caching, you need to make sure that the data source you're going to cache doesn't have more rows than configured for the data row limit in the app settings.

- **Do you need to calculate columns or manipulate the data you loaded?** If the data source supports required calculations and the column is useful across multiple apps, you should try to implement these in the data source. For example, Microsoft Dataverse has calculated and rollup column capabilities.

- **How frequently do you need to see data added/modified by another app or automation?** If you are pre-loading data into a collection, you will only see the updated information if you reload the collection.

## Direct data source binding

When you set the items property of a gallery to the table of a tabular connector or use an expression like Filter() that is based on the table, you are doing direct data source binding. The following expression binds directly to the Desks table.

    SortByColumns(Filter(\[\@Desks\], StartsWith(Title, TextSearchBox1.Text)), \"Title\", If(SortDescending1, Descending, Ascending))

This is the most basic approach to data loading. Data is retrieved directly from the connector as the criteria on the filter changes. This is a declarative way of loading data where the Power Apps runtime can decide to load and refresh the data. As a result, you don't have the option of having a loading indicator shown to the user.

Once data is loaded, it can be used by controls without retrieving from the data source each time. You can manually refresh the data from the data source using Refresh(tableName). The data displayed in controls is automatically refreshed when data is modified elsewhere in the app.

Another significant advantage of direct binding is you are not limited by the data row limit app setting if your connector supports delegation. For example, if you had 100,000 contact rows in Microsoft Dataverse and you bound a gallery directly to the table, the gallery would load an initial set of items and then get more as the user scrolled. The following screenshot shows Power Apps Monitor events that include getRows call to load the initial data followed by several getMoreRows calls as the user scrolls the gallery. These are done automatically by Power Apps and the app doesn't need to handle paging of the data.

> [!div class="mx-imgBorder"]
> [![Screenshot that shows Power Apps Monitor events with three columns.](../media/1-network-rows.png)](../media/1-network-rows.png#lightbox)

As we suggested in our initial considerations you really don\'t want to present the user with 100,000 rows. Instead, with data sources that support delegation, add a filter then let the connector process the filter criteria and only return rows that match.

## Preload data into collection

This allows you to control the load of the data in either App.OnStart or OnVisible screen property. Preloading data in App.OnStart is a good choice if you need the same data on multiple screens. Doing it from OnVisible allows deferring the load until that screen is used. Either option allows you to show a loading indicator while the data is loaded.

The following expression clears the colDesks collection and loads all the Desks table rows up to the Data row limit app setting.

    ClearCollect(colDesks,Desks)

To use the preloaded data, you would change your relevant formulas to use the collection.

> [!div class="mx-imgBorder"]
> [![Screenshot of the Tree View menu with updated formula highlighted.](../media/2-screen-formula.png)](../media/2-screen-formula.png#lightbox)

When you use data preloaded into a collection the data does not get refreshed unless you ClearCollect() again to bring in the latest data. This is different from the direct data source binding where refresh is automatically managed by the Power Apps.

Another advantage of this approach is you can allow your user to modify and review multiple rows as they go, without saving each one using the data source. Once changes are completed, they can be committed back to the data source using a single Patch() function call. If you want to undo all changes before the commit, you can refresh the collection. The following is an example of using Patch function to commit changes in colDesks collection back to Desks table in Dataverse.

Patch(Desks,colDesks)

## Loading from persisted storage

A variation of the simple preload approach is to load data from your device local storage first and then continue to load directly from the data source. This strategy is helpful when the data source is slow or available intermittently. To implement this pattern, you would need to do the following:

- Load the data, if it exists, from the device local storage using LoadData(). At this point, any control bound to the collection would show the data.

- Proceed to load data directly from the data source connector into the same collection. At this point, any control bound to the collection would show the updated data loaded from the connector.

- Use SaveData() to persist the most recent data to the device local storage.

Your formulas would look like the following:

    LoadData(colDesks,\"LocalDesks\",true);

    ClearCollect(colDesks,Desks);

    SaveData(colDesks,\"LocalDesks\");

If your users are occasionally not connected, you can add in a conditional check if they are connected prior to attempting to load new data. The revised formula would look like the following:

    LoadData(colDesks,\"LocalDesks\", true);

    If (Connection.Connected,

    ClearCollect(colDesks,Desks);

    SaveData(colDesks,\"LocalDesks\")

    )

## Preload into a variable

When working with non-tabular connectors like the Office 365 Users, you can improve performance by saving the results from a function call into a variable. In the following example, the formula is calling the function three times to get information from the profile.

    Set(profileDisplayName,Office365Users.MyProfileV2().displayName);

    Set(profileHireDate,Office365Users.MyProfileV2().hireDate);

    Set(profileCity,Office365Users.MyProfileV2().city);

The following expression is more efficient because it only calls the connector once but still populates the three variables:

    Set(profile,Office365Users.MyProfileV2());

    Set(profileDisplayName,profile.displayName);

    Set(profileHireDate,profile.hireDate);

    Set(profileCity,profile.city);

You could also simplify it further to one variable named profile and use the dot notation to access the properties whenever required for example, use profile.hireDate property instead of the profileHireDate variable. To do that you would only have the following expression in App.OnStart:

    Set(profile,Office365Users.MyProfileV2());

    And then instead of the following expression that uses individual variables to set a controls color:

    If(IsBlank(profileHireDate),Red,Green)

    You would use the following expression using the dot notation profile.hireDate

    If(IsBlank(profile.hireDate),Red,Green)

## Loading data concurrently

If you are preloading data from connectors and have multiple items that you're caching, by default they will run one at a time sequentially. Take the follow example loading two tables and the user profile into collections and a global variable.

    ClearCollect(colDesks,Desks);

    ClearCollect(colDeskFeatures,\'Desk Features\');

    Set(userProfile, Office365Users.MyProfileV2())

If each of them is independently preloading data, then you can run them in parallel by using the Concurrent() function.

    Concurrent(

    ClearCollect( colDesks,Desks ),

    ClearCollect( colDeskFeatures, \'Desk Features\' ),

    Set( userProfile, Office365Users.MyProfileV2() )

    )

## Loading data once

If you preload data in App.OnStart, it will only run once when your app starts up. If you use OnVisible property instead to defer,  preload to the first time the screen is used, OnVisible will run each time the screen is navigated to. This will potentially refresh your collection too frequently. To avoid this, instead of simply doing a ClearCollect you would need to check first if you have already loaded the data.

Replace the following function call:

    ClearCollect(colDesks,Desks)

    with the following expression that includes the check if the collection is empty:

    If(IsEmpty(colDesks),ClearCollect(colDesks,Desks))

## App Settings and data loading

In the opening topic of this module, we covered how app settings can affect your app's performance and behaviors. If you are using collections to preload data, the data row limit applies and can make larger data sets unsuitable for preloading.

Another setting to be aware of is delay load. This setting delays running screen expression calls until needed and then runs them on demand. This setting is on now by default for all new apps and can be turned on manually for older apps.

Optimizing your app's data loading is unique to each app. In this topic, we looked at how to evaluate the needs of your users and the app to tailor your data loading strategy for best performance and user experience. Optimizing is not a one-time exercise, but something you do over the lifetime of the app. You also want to make sure to take advantage of any of the new platform capabilities that optimize data loading as they become available.
