The growth of Microsoft Power Apps has led many traditional developers to take a look at Power Apps. When they do, they into an app development model that is _like_ other development environments, but not quite the same. While Power Apps has been built in order to allow more people to achieve more by building apps, it can also be a valuable tool for traditional developers looking to create apps quickly, iterate through testing, and get those apps in front of users on tablets, phones, and on the web faster than ever before.

This module will help bridge the gap between your existing traditional development knowledge and how Power Apps works including app logic, user interface creation, and data flow.

## Setting the scene

The management at VanArsdel, Ltd have decided to allow the business users in the office to start using Power Apps in order to scale how quickly applications can be built for the business to get their needs met while continuing to overload their IT organization.

:::row:::
  :::column span="4":::
    Kiana Anderson is a full-stack developer and software architect specializing in C# and .NET. She has written and designed many of VanArsdel's applications but is getting stretched thin by all the new requests. Kiana has heard of Power Apps, and would like to learn what it can do on its own before using her full-stack skills to add more capabilities to the platform.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Crystal](../../../shared/media/crystal.png)
  :::column-end:::
:::row-end:::

Kiana has been supporting a long-running forms-over-data app written in ASP.NET years ago, which people in the office use to check inventory and order parts if necessary. She has been asked to create a mobile version of the inventory app for use by field workers, and thinks that it would be a good use case to try out Power Apps.

:::row:::
  :::column span="4":::
    Maria Zelaya works in inventory management and makes sure Munson's runs like a well-oiled machine. She verifies the warehouse has enough materials on hand and if not orders more using a legacy system that Crystal wrote. But more than that—she performs audits on the inventory, checks with vendors for the best prices, and other inventory supply management tasks.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Maria](../../shared/media/maria.png)
  :::column-end:::
:::row-end:::

Maria has been studying up on Power Apps in her spare time. She believes that Power Apps excels at enabling business professionals develop applications that are easy to create and deploy. She will provide Crystal with requirements for the new app, and do some work on the Power Apps mobile app with her as well.

## What Is "Low Code", and how is it used in Canvas-based Power Apps?

The term "low code" can mean different things to different people when they first hear it. What we mean when we talk about low code is that with tools like Power Apps, you only need to write a small amount of code to get results that would normally take several more lines of code in a traditional programming language.

In canvas-based Power Apps, the low code scripting language used is called [Power Fx](https://docs.microsoft.com/en-us/power-platform/power-fx/overview); that is the language we will be learning and using throughout this module to build our app.

Take this as an example: to look up the first name of the employee for an order, one would write the Power Fx formula or equivalent JavaScript as seen in the animation below. This animation shows the mapping between the parts of the Power Fx formula and the concepts that need to be explicitly coded in the equivalent JavaScript.

![Power Fx and JavaScript comparison](../media/powerfx-vs-js-example.gif)

Let’s look more in depth at all the things that Power Fx is doing for us and the freedom it has to optimize because the formula was declarative:

### Asynchronous.

All data operations in Power Fx are asynchronous. The developer doesn’t need to specify this, nor does the developer need to synchronize after the call is over. Most importantly, the developer doesn’t need to be aware of this concept at all, they don’t need to know what a promise or lambda function is.

### Local and remote.

Power Fx uses the same syntax and functions for data that is local in-memory and remote in a database or service. The user need not think about this distinction. Power Fx automatically delegates what it can to the server to process filters and sorts there more efficiently.

### Relational data.

Orders and Customers are two different tables, related through a many-to-one relationship. The OData query requires an “$expand” with knowledge of the foreign key, similar to a Join in SQL. The formula has none of this, in fact database keys are another concept the maker doesn’t need to know about. The maker can use simple dot notation to access the entire graph of relationships from a record.

### Projection.

When writing a query, many developers will naively write “select * from …” that brings back all the columns of data. Power Fx does analysis of all the columns that are used through the entire app, even across formula dependencies. Projection is automatically optimized and again the maker need not even know what that word means.

### Retrieve only what is needed.

In this example, the LookUp function implies that only one record should be retrieved and that is all that is brought back. If more records are requested by using the Filter function, for which thousands of records may qualify, only a single page of data is brought back at a time, on the order of a hundred records. The user must gesture through a gallery or data table to see the additional data, and it is automatically brought in for them. The maker can reason about large sets of data without needing to think about limiting data requests to reasonable chunks.

### Runs only when is needed.

We defined a formula for the Text property of the label control. As the variable Selected changes, the LookUp is automatically recalculated and the label updated. The maker did not need to write an OnChange handler for Selection, needing to remember that this label is dependent upon it. This is declarative programming as discussed earlier; the maker specified what they wanted to have in the label, not how or when it should be fetched. In fact, if this label is not visible because it is on a screen that is not visible or its Visible property is false, we can defer this calculation until the label is visible and effectively eliminate it if that rarely happens.

### Excel syntax translation.

Excel is used by hundreds of millions of users, most of which know that “&” is used for string concatenation. JavaScript uses “+” and other languages use “.”. We are meeting makers where they are, leveraging the knowledge they already have.

### Display names and localization.

'First Name' is used in the Power Fx formula while nwind_firstname is used in the JavaScript equivalent. In Dataverse and SharePoint, there is a display name for fields and tables as well as a unique logical name. The display names are often much more user friendly, as in this case, but they have another important quality: they can be localized. If you have a multi-lingual team, each team member can see table and field names in their own language. In all cases, Power Fx makes sure that the correct logical name is sent to the database automatically.

### Always live

There is another Excel trait that is critical for citizen developers: immediate feedback. If you stop to think about it, Excel has no edit mode, compile step, or run state. What’s great is that you’ve probably never thought about that before: you load your spreadsheet, you edit formulas and values freely, and you get your answers. The spreadsheet is always live while in Excel and there is no distinction made between editing and running. Changes in any value or formula are immediate propagated throughout the spreadsheet and the maker can quickly check for the right answer. Any errors that Excel detects are surfaced immediately and don’t interfere with the rest of the spreadsheet.

## Learning Objectives

After completing this module, you will be able to:

* Understand what "low code" is
* How Power Apps low code works in terms that map to other traditional software development stacks 
* How data flows into and out of the apps you can create in Power Apps