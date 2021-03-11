The growth of Microsoft Power Apps has led a number of traditional developers to take a look at Power Apps and run into an app development model that is _like_ other development environments, but not quite the same. While Power Apps has been built in order to allow more people to achieve more by building apps, it can also be a valuable tool for traditional developers looking to create apps quickly, iterate through testing, and get those apps in front of users on tablets, phones, and on the web faster than ever before.

This module will help bridge the gap between your existing traditional development knowledge and how Power Apps works including app logic, user interface creation, and data flow.

## Setting the scene

The management at Munson's Pickles and Preserves Farm have decided to allow the business users in the office to start using Power Apps in order to scale how quickly applications can be built for the business to get their needs met while continuing to overload their IT organization.

:::row:::
  :::column span="4":::
    Crystal is a full-stack developer and software architect specializing in C# and .NET. She has written and designed many of Munson's applications but is getting stretched thin by all the new requests. Crystal has heard of Power Apps, and would like to learn what it can do on its own before using her full-stack skills to add more capabilities to the platform.
  :::column-end:::
  :::column:::
    ![Cartoon depiction of Crystal](../../shared/media/crystal.png)
  :::column-end:::
:::row-end:::

Crystal has been supporting a long-running forms-over-data app written in ASP.NET years ago, which people in the office use to check inventory and order parts if necessary. She has been asked to create a mobile version of the inventory app for use by field workers, and thinks that it would be a good use case to try out Power Apps.

:::row:::
  :::column span="4":::
    Maria works in inventory management and makes sure Munson's runs like a well-oiled machine. She verifies the warehouse has enough materials on hand and if not orders more using a legacy system that Crystal wrote. But more than that—she performs audits on the inventory, checks with vendors for the best prices, and other inventory supply management tasks.
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

![Power Fx and JavaScript comparison][image-01]

[image-01]: ..\media\powerfx-vs-js-example.gif

## Learning Objectives

After completing this module, you will be able to:

* Understand what "low code" is
* How Power Apps low code works in terms that map to other traditional software development stacks 
* How data flows into and out of the apps you can create in Power Apps