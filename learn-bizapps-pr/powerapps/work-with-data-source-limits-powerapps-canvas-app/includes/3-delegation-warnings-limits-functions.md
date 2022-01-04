Power Apps uses visuals to help you, the app maker, understand when
delegation is occurring. The maker portal also has one setting you can
adjust to increase the amount of data returned when delegation isn't
possible.

## Delegation warnings

Anytime you use a non-delegable function, Power Apps underlines it with a
blue line and displays a yellow warning triangle as shown below.

![Screenshot of non-delegable function with blue line and yellow warning triangle.](../media/delegate-warning.png)

This gives you a clear visual indicator that delegation isn't
happening, which means you may not see all of your data. It's
important to understand a couple of things about this visual indicator.

- Power Apps will provide this warning whatever the size of your
    data source. Even if your data source only has a few items
    and delegation isn't technically causing you a problem, the
    warning will still show. Remember the first 500 items are returned by
    default and processed locally. The warning appears anytime that your
    formula isn't delegated.

- The warning indicator only processes through the first thing that causes delegation. Notice in the above screenshot that only the underlined field "FirstName" is in blue. That is because it was the first item that caused delegation. "LastName" would also cause delegation in this scenario. This can be confusing because people try to troubleshoot what is the difference between FirstName and LastName instead of the real issue, which is the Search function. If you come across this confusion, rearrange your formula. This will validate and whichever field is first will show the issue.

    ![Screenshot of the Warning Indicator for the first item that caused delegation.](../media/warning-indicator.png)

- This visual indicator is only present when you are in the maker
    portal, building the app. When a user is running the app, they won't
    receive any notification that delegation isn't occurring and
    that they may only be seeing partial results. Keep this in mind when
    designing your app and build accordingly.

## Change the number of records returned when delegation isn't available

When a formula can't delegate to the data source for any
reason, then by default Power Apps retrieves the first 500 records from
that data source and the processes the formula locally. Power Apps does
support adjusting this limit from 1 to 2000. You can adjust this limit in
the Advanced settings.

1. From the Maker portal, select **File** in the upper-left corner.

1. In the left-most menu, select **Settings**.

1. Under **App settings**, select **Advanced settings**

1. Set the Data row limit for non-delegable queries for any value
    between 1 to 2000.

1. After you have set the limit, select the **arrow** in the upper left to
    save your change and return to the Maker portal.

![Screenshot of the Power Apps Settings Advanced Settings with data row limit set.](../media/app-settings.png)

There are two primary reasons that you might want to adjust this limit.

- To increase the limit if you're working with data where 500
    records aren't enough, but less than 2000 is. For example, if you
    have a customer list and you know you'll never have more than 1000
    customers, then you could design your app to ignore delegation and
    always return all 1000 records.

- To lower the limit to 1 or 10 to help with testing. If you're
    running into scenarios where you aren't sure if a non-delegable
    function is causing problems with your app, you can lower the limit
    and then test. If you set the limit to 1 and your gallery is
    only presenting one record, you know that you had a non-delegable
    function. This setting speeds up your troubleshooting process.

## Non-delegable functions

In the previous unit, you learned about the functions that are delegable and how they relate to the various data sources. These other functions, not covered in that unit, aren't delegable. The following are notable functions that don't support delegation.

- First, FirstN, Last, LastN

- Choices

- Concat

- Collect, ClearCollect (Neither of these functions return a delegation warning, but they aren't delegable)

- CountIf, RemoveIf, UpdateIf

- GroupBy, Ungroup

All of these functions aren't delegable. So by adding them to a formula you might take a previously delegable function and make it not delegable, as seen in the previous example.

## Partially supported delegable functions

The Table shaping functions below are considered to be partially delegable. This means, formulas in their arguments can be delegated. However, the output of these functions is subject to the non-delegation record limit.

- AddColumns

- DropColumns

- ShowColumns

- RenameColumns

A common pattern is to use AddColumns and LookUp to merge information
from one table into another, commonly referred to as a Join in database
parlance. For example:

```powerappsfl
AddColumns( Products, "Supplier Name", LookUp( Suppliers,
Suppliers.ID = Product.SupplierID ).Name )
```

Even though Products and Suppliers may be delegable data sources and
LookUp is a delegable function, the AddColumns function is partially
delegable. The result of the entire formula is limited to the first
portion of the Products data source.

Because the LookUp function and its data source are delegable, a match
for Suppliers can be found anywhere in the data source, even if it's
large. A potential downside is that LookUp will make separate calls to
the data source for each of those first records in Products, causing much
chatter on the network. If Suppliers is small enough and doesn't
change often, you could cache the data source in your app with a Collect
call when the app starts (using OnVisible on the opening screen) and do
the LookUp to it instead.
