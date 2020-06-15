Microsoft Power Apps works with other technologies to help you build powerful apps for your organization. Some of these technologies include:

- **Data sources** - Without data, you don't have a business. Data sources bring cloud and on-premises data into your apps. You access data through built-in connections, custom connectors, and gateways.
- **Common Data Service** - A compliant and scalable data service that's integrated into Power Apps.
- **Power Automate** - Allows you to build automated workflows to receive notifications, run processes, collect data, and more.


## Data sources, connections, and gateways
In Power Apps, most canvas apps use external information that is stored in Data Sources. A common example is a table in an Excel file that is stored in OneDrive for Business or SharePoint. Apps access these data sources by using connections. Some connections allow Power Apps to read and write stored data. In Power Apps, you can add many data sources to your apps through built-in or custom connectors. Some of the most popular data sources are shown in the following figure.

![Power Apps data sources](../media/powerapps-datasources.png)

Many data sources are cloud services, like Salesforce. Even Twitter can be a data source if, for example, you're tracking your company's hashtags. Connectors might not seem like the most exciting part of app development; however, they're essential when you work with data that you, your colleagues, and your customers care about. When an app shows up with your data source for the first time, you might suddenly find that they are, in fact, exciting.

For data that's stored on-premises instead of in the cloud, you can use a gateway to provide a reliable connection between Power Apps and your data source. The gateway sits on an on-premises computer and communicates with Power Apps. 

An advantage of building your business apps in Power Apps is being able to connect to many data sources in a single app. With the connectors in Power Apps, you can connect to where your data lives. To learn more about data sources in Power Apps, refer to the Working With Data learning path. 


## Common Data Service
An important data source option to explore further is the Common Data Service. Common Data Service lets you store and manage data that's used by business applications. Data within Common Data Service is stored within a set of entities. An entity is a set of records that are used to store data, similar to how a table stores data within a database. Common Data Service includes a base set of standard entities that cover typical scenarios, but you can also create custom entities that are specific to your organization and then populate them with data by using Power Query. App makers can then use Power Apps to build rich applications by using this data.

![Platform Overview](../media/platform.png)

For information on purchasing a plan to use Common Data Service, refer to the [License](https://docs.microsoft.com/power-platform/admin/pricing-billing-skus) and [Pricing](https://powerapps.microsoft.com/pricing/) information pages.

## Reasons to use Common Data Service
Standard and custom entities within Common Data Service provide a cloud-based storage option for your data. Entities let you create a business-focused definition of your organization's data for use within apps. If you're unsure if entities are your best option, consider the following benefits:
- **Simple to manage** - Both the metadata and data are stored in the cloud. You don't need to worry about the details of how they're stored.
- **Helps to secure data** - Data is stored so that users can see it only if you grant them access. Role-based security allows you to control access to entities for different users within your organization.
- **Access your Dynamics 365 Data** - Data from your Dynamics 365 applications is also stored within the Common Data Service, which allows you to quickly build apps that use your Dynamics 365 data and extend your apps by using Power Apps.
- **Rich metadata** - Data types and relationships are used directly within Power Apps.
- **Logic and validation** - Define calculated fields, business rules, workflows, and business process flows to ensure data quality and drive business processes.
- **Productivity tools** - Entities are available within the add-ins for Microsoft Excel to increase productivity and ensure data accessibility.

## Related Power Platform technologies

As you continue developing your application, you may want to consider implementing additional Power Apps related technologies such as Power Automate and or Power BI. For example, you may have a simple Expense Report App that requires an approval before an item can be purchased. With Power Automate, you can create a simple Flow to make this happen. Or maybe you want to display your data with custom charts and graphs giving your users a more visual look into the data, which can often be useful. In this section, you will learn more about some of the other Power Platform technologies and how you could apply them in your own Power Apps solution. Keep in mind, if you decide to implement these Power Apps related technologies you should also review their licensing structure and associated costs.

![Related apps icons.](../media/power-platform-technologies.png)

### Power Automate

Power Automate brings automation to your business. This can be traditional workflows via flow, Robotic Process Automation (RPA) for automating legacy systems via UI Flows, or business process automation via Business Process Flows. Each of these capabilities increases your productivity to connect disjointed systems to build the business solution you need and make your app more powerful. 

You can use Power Automate to create logic that performs one or more tasks when an event occurs in a canvas app. For example, configure a button to execute a flow to do one of the following: create an item in a SharePoint list, send an email or meeting request, or add a file to OneDrive.  The button could be configured to do all of those in a single Power Automate flow. You can configure any control in the app to start the flow, which continues to run even if you close Power Apps.  Below is an example using Power Automate to send a flow:

![Power Automate flow.](../media/power-automate-flow.png)

### Identify Flows in your Solution

Now that you have a general overview of Power Automate, how do you determine if the solution you’re building requires a Flow? There are a number of simple functions Power Apps can do, like sending an email when a button is pressed in your application. This email generated from Power Apps can also contain dynamic/specific information and be sent to any email address you would like. Often, customers will use Power Automate to create this same functionality even though Power Apps can do this out of the box. Power Automate should be used for more complex solutions, such as the approval workflows. With Power Automate you can run an approval when a button is pressed, on a schedule, when an item is created or modified, and so on. 

For many Power Apps solutions Power Automate is used to handle complex business logic. Do you need a way to make sure someone actioned on the incident report that was generated by your app? Or, do you need a process to kick off every time new data is created in another system so Power Apps will have the data it needs? Do you need to check each morning to see if an inspection is due that day and then send an email with a link to your Power Apps inspection form? These are great uses of Power Automate to transform your app from a point solution to a fully featured business solution.

## Power BI

Power BI is an analytics tool within the Power Platform suite.  Power BI connects data from multiple sources and transforms the data into graphical visualizations to gain insights.  It allows business users to utilize a number of different visualizations to build comprehensive reports and dashboards.  When creating Power BI reports to view and analyze your app data, you have the ability to customize them for personal use and will only be accessible by you, providing you with a more unique and custom experience. If you need to share the report with others, you and each of the report consumer will need a Power BI Pro license. This license allows you to not only share the content but also control what others are able to do with the shared report or dashboard.  

While Power Apps has capabilities to include simple graphs or tables, many solutions would be better served with a visualization provided by Power BI.  Power Apps and Power BI have two options for seamless integration:

### Embed a Power BI tile in a Power Apps app

By embedding a Power BI tile in a Power Apps solution, you are able to bring valuable visualizations into the app to allow the user to consume that data within the context of the app.  

In the example below, you will see a simple Power BI Tile embedded in a Sales Planning app built in Power Apps. The visual is displaying the Profit and Gross Sales and the Power Apps form allows the user to enter sales predictions.

![Power BI sales dashboard.](../media/embed-power-bi-power-apps.png)

### Embed a Power Apps app in a Power BI Dashboard

Another integration between these two applications, is to embed a Power Apps app in your Power BI report.  This allows the user to action on data while never leaving the dashboard resulting in a better user experience.  Consider an inventory management dashboard for a manufacturing facility.  Without leaving the dashboard, the user can submit to purchasing an order for additional material.  While the solution may have been utilizing both the Power Apps and Power BI platforms, the user simply experiences a complete end to end solution in one window on their desktop.

In the example below, we are analyzing the Sale Price and Profit by Country and Segment. Notice once you have embedded your Power App in a Power BI Dashboard you can navigate between screens.

![Power BI with Power Apps.](../media/navigate-multiple-screens-details.png)

In this next screenshot, still working with the same data as the previous example, you can utilize the native Power Apps features like Search with Power BI data.

![Power BI with Power Apps filtered.](../media/power-apps-search-pbi-data.png)

In this last screenshot, for this example, you will see the embedded Power App is filtered by the Power BI selection.

![Power BI with Power Apps filtered.](../media/apps-filtered-pbi-selection.png)

### Translating needs to the appropriate technology

To build the best solution, think through the use cases and determine how you want to collect the data, use the data, and analyze the data.  Once you have determined how the solution will be used in each one of those cases, you can begin to select the right technology to execute each function. 

It would be difficult to cover every use case and decision point, but to help you understand the decision-making process let’s explore sending an email via Power Automate versus sending an email via Power Apps. First consider the look and feel of the email, does your solution require special formatting of the email? To format the text of your email in Power Apps, like adding italics or bold text, you would need to write HTML. In Power Automate though, this functionality can be implemented by using the simple Design Interface that is provided out of the box. 

Below are examples of the formulas to execute sending an email via Power Apps versus via Power Automate.

**Send an Email via Power Apps**

![Send and email with Power Apps.](../media/send-email-power-apps.png)


**Send an Email via Power Automate**

![Send and email with Power Apps.](../media/send-email-power-automate.png)

Also, the number of steps in your solution/process will aid you in determining which technology best suits your needs. Power Apps is great for performing simple solutions with minimal steps but as your solutions become more complex and requires multiple steps, Power Automate would be the better solution.

Again for this particular example, both technologies can provide the same solution, but there are little nuances that should be considered and thoroughly discussed during the design process to determine your requirements and help you choose the best product for your solution. 

Let's not forget about discussing Power Apps and Power BI, and when to use one vs. the other. When deciding whether to use the basic charts, graphs, and visuals that come with Power Apps out of the box or to utilize a more powerful software like Power BI it really depends on your business solution and requirements. For example, if in your solution, you are wanting to add some basic graphs and charts to improve the apps overall look and feel while adding some visual flair for your users, Power Apps has you covered.

Here is a quick look at one of the simple, out of the box Power Apps charts.

![Power Apps chart example.](../media/power-apps-chart-example.png)

Simple and minimal design above, nothing crazy but it gets the job done.

On the other hand, if your solution requires in-depth analysis of your data, and robust visuals, Power BI will be the best product for your solution. Keep in mind, with Power BI, each app user will need an additional license on top of the Power Apps license. This is a small price to pay though if our solution relies on intuitive dashboards, charts, graphs, and several other features to help you get the most out of your solution.

![Embedded Power BI tile in Power Apps.](../media/embedded-power-bi-tile-power-apps.png)

By identifying the needs of related Power Apps technologies in your solution and strategically implementing them, you will be able to provide your users with a better overall experience when using the solution.