In addition to the telemetry sent automatically by the Power Apps runtime to Application Insights you can use the Power Fx Trace() function to send custom events. By instrumenting your app with trace calls, you can capture important events and associated data. The following are some examples of when you might add Trace() function calls:

-   OnStart to log the parameters passed to your app when it was started

-   When users enable or disable options in your application

-   When a button is selected to perform an action

-   When the user cancels an action

-   When an error occurs for example, submitting a form or data source errors

-   To log validation errors

-   To log search criteria so, you can determine what are the popular searches

-   To log feedback from what a user likes or doesn't like in an app (or)

-   Anything that you'd like to be able to query later

In addition to logging the data for Application Insights, trace data is also visible in the Monitor tool and Test Studio results.

The syntax for the function is:

`Trace(message, trace_severity, custom_record )`

The message parameter is required and should be used to identify why you called trace. For example, Trace("Timesheet Validation Failed").

You can optionally pass a severity level of information, warning, error or critical. When used to consistently categorize your traces severity can be helpful in query the data. For example, you could get a daily email with a list of all the errors that were captured.

The trace function also allows you to pass a data record with context information. This record can have one or more data fields that would be helpful when you analyze the trace event data later. This data can also be used in the log queries to narrow down the set of trace records you review. The inline record is composed using curly braces that contain named field values. For example, we could enhance our previous validation by passing more context information:

`Trace(“Timesheet Validation Failed”,Warning, { hoursWorked:ThisItem.HoursWorked”)`

When you are composing Trace() function calls you should keep the following in mind:

-   Avoid any sensitive data being recorded in Application Insights that might cause compliance problems, for example customer's name and email address.

-   Watch out for bad data or a formula that might cause unexpected results.

-   Don't send too much data, only what you need to analyze or query the data

-   Use consistent field names to make querying easier across related trace calls

## Querying the traces

You can query and view the data captured by each Trace() function call by querying the log and using **traces** as the table name.

> [!div class="mx-imgBorder"]
> [![Screenshot of building a query of traces from the log data.](../media/query.png)](../media/query.png#lightbox)

In the results, you will see that each line has an itemType of trace. In each row, you can see the message and severityLevel. If you expand the row, you will see a customDimensions property that can be further expanded to show the fields you logged as context data when you invoked the Trace() function.

> [!div class="mx-imgBorder"]
> [![Screenshot of query results with custom dimensions highlighted.](../media/custom-dimensions.png)](../media/custom-dimensions.png#lightbox)

In the above image JobId and JobName were context data. All of the ms- fields are automatically added to every trace. Any of this data can be used to build a query like the following that queries for all the trace records from specific JobId.

> [!div class="mx-imgBorder"]
> [![Screenshot of the query traces.](../media/traces.png)](../media/traces.png#lightbox)

You can use ms-appId to find all the traces for a specific app and ms-appSessionId to find all the traces for a user for that session of running the app. Each app that logs data will have a unique ms-appid.

Adding traces to your app can provide you a valuable resource to track down problems. Traces are especially valuable because they can be used to capture data for an app running in production and doesn't require you to run the app in Power Apps Studio. By proactively adding trace function calls to your application, you will be ready when users report a challenging problem in production.