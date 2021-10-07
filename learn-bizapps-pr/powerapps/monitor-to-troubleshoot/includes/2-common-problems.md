There are two common ways you can use Monitor as part of your regular
app building process:

- **Reactively** - You are aware of a problem and need help with identifying the root cause. For example, if someone using your app
    reported an error and you can use Monitor to pinpoint the cause.
    Most the time you have a pretty good idea where in the app  error
    occurs, and you can Monitor events for a specific action in the app.

- **Proactively** - As part of your normal app building process
    before you release your app to the end users you use Monitor to
    identify possible problems. When doing proactive testing, it is most
    common to just run the app while Monitor is capturing events. By
    reviewing the event log, you can look for long response times, other anomalies, or errors. Problems
    identified proactively at the build stage lead to fewer problems
    seen by the end users in production and result in perception of a
    higher-quality app.

In the rest of this module, we will look at how to identify and resolve
common problems using Monitor.

Regardless of which approach you are using it is generally best to start
your capture with an empty event log. You can accomplish this by
clicking the Clear data button in Monitor before you start your actions
in the app you are testing.

:::image type="content" source="../media/clear-data.png" alt-text="![Screenshot showing the clear data button highlighted]":::

## Use meaningful control names

The control names included in the captured events are a key corelation of
the event to where it happened in your app. Using good names for
controls can make it easier for you to work with the event data. Take
the following example where we compare the default-generated names to
more meaningful ones that are recommended. You can see how it would be
easier to identify what control was involved in the activity when
meaningful names are used.

:::image type="content" source="../media/control-names.png" alt-text="![Screenshot showing generic names versus meaningful names and how they can make the data more useful]":::

## Finding similar events

When working to identify the source of a problem a common task is to
find other occurrences that might be related. Monitor makes that easy by
offering two approaches to filter the event data that has been captured.
First, you can use the global filter option to search across all columns
in the event log data. You can find the global filter in the upper right
corner of Monitor.

:::image type="content" source="../media/filter-tool.png" alt-text="![Screenshot showing filter box]":::

This filter is good when you don\'t have a specific field that you\'re
looking for the data in. For example, you want to look broadly across
all the columns for something matching a pattern like the name of a
control or a connector action.

Each column also offers the ability to filter and provide more data type
specific filtering options. You can activate the column filter by
clicking the chevron next to each column name and selecting Filter by.

:::image type="content" source="../media/filter-column.png" alt-text="![Screenshot showing the filter by option]":::

This option can also be done on multiple columns concurrently, giving
you the ability to create criteria that includes more than one column
having your requested values. When you have filters on multiple columns
each event must qualify for all column filters to show.

Using the filter capabilities can be helpful if you have captured a
large quantity of events and are looking to isolate specific problems.

## Identifying and resolve errors

Most commonly, errors are found because they presented an error message
to the user or triggered some error handling logic in the app. Even in
these cases Monitor is still useful because it has much more detailed
information about the specific error when the error involves a
connector. As app error handling gets more sophisticated it\'s also possible that the error is absorbed by error handling logic and the only way, you see it is by looking at the data captured. This is a good
example of where proactive monitoring of an app can catch errors that
you weren\'t expecting or didn\'t know were occurring.

The easiest way of identifying an error in the event data log is to look
at the result column where it contains the word Error instead of
Success.

:::image type="content" source="../media/event-log.png" alt-text="![Screenshot showing the error in the event log]":::

There is also a red X circle indicator at the beginning of lines that
contain errors to help you visually identify them.

The status column often will contain a detailed Http status code that
will give you a more specific error category. The resulting information
often contains a text summary of the status code. You can find more
details on the different HTTP status code values on
[docs.microsoft.com](https://docs.microsoft.com/dotnet/api/system.net.httpstatuscode?view=net-5.0).

To work toward resolving errors your best information will come from the
Formula, Request and Response tabs in the detail area that is shown when
you select one of the errors. The formula is useful to correlate to what
caused the error in the app, but the request and response will provide
the underlying details.

The most common cause of errors is bad or missing data when using a
connector. You can review the request to see what was sent to the
connector that caused the error.

While the contents of the request can vary from connector to connector,
the two most common things to look for in the request are the URL and
the body.

:::image type="content" source="../media/request-screen.png" alt-text="![Screenshot showing the request highlighting the URL and the body property]":::

In most cases, for connector actions that make changes to data you will
find the most valuable information in the body. Generally, you are
looking for bad or missing data from what you expected to see sent to
the connector for the request. Comparing the request body to the
connector action API documentation can also highlight problems.

For query type actions the URL typically would contain other useful
information in the query string.

The Response tab contains the data returned from the connector. While
each connector can have a uniquely defined response structure many
errors can just be found by looking at hints from scanning the response
message. In the following example, a business rule blocked the request
to create a test contact record and an error message was included in the
response.

:::image type="content" source="../media/response-message.png" alt-text="![Screenshot highlighting the error message in the response data]":::

While the contents of the request and response might seem to intimidate,
a quick scan of them can often result in hints to help you resolve the
problem. In the event they don\'t help you, providing these details to
the connector developer or support can help them understand how you were
using the connector.

## Identifying and resolving slow actions

While you may have a user that tells you specifically what is slow
in your app, the duration column is another good indicator. You can use
a filter on the duration column after you\'ve run the application to
allow you to focus on only the slow actions. The value for duration is
tracked in milliseconds (ms). In the following, we look for any event log
entry that took longer than one second.

:::image type="content" source="../media/column-filter.png" alt-text="![Screenshot showing the column filter for duration greater than one second]":::

If your app does numerous data loading during start-up, you want to make
sure that the monitor is running, and you force running your on start
logic.

:::image type="content" source="../media/run-onstart.png" alt-text="![Screenshot showing the run on start option in Power Apps Studio]":::

The most common way to resolve slow actions is to reduce the amount of
work that is done by the action or the amount of data that is returned
from the action. By looking at the request, you might be able to identify
if all your criteria have been properly passed and if there\'s
additional criteria that could be provided to reduce the work. You can
also look at the response to identify if more data is being returned
than you need. Some connectors can automatically identify and return the
proper data while others require you to specify options on the request
to return only the data that\'s relevant.

## Identify and resolve delegation problems

[Delegation](https://docs.microsoft.com/powerapps/maker/canvas-apps/delegation-overview)
issues occur when you compose a query that contains criteria that can't
completely be resolved and executed remotely by the connector service.
When this occurs, the app sends only part of the criteria to the
connector to bring back more records than necessary and to postprocess
the results from the connector in the app. The number of records that
can be pulled back and postprocessed is limited by an app setting and
defaults to 500. If there are more eligible records available from the
connector than the specified limit, the results will be truncated, and
you may have inaccurate results in your app.

In many cases app checker in Power Apps Studio will identify the
delegation problem and you can resolve the problem without Monitor.
Monitor also flags these events and provides more detail. If you
can't identify the problem with the information App Checker provided
look at the request that was sent to the connector. Specifically review
the query criteria data that is missing, and it can help you understand
what is not able to be sent to the connector as delegable criteria.

In many cases, delegation problems can be resolved by rewriting the
formula to not include dynamic data calculations in the criteria sent to
the connector. Different connectors support different functions for
delegation, and you may find what worked for one connector does not work
for another. You can use Monitor to verify that the formula returns the
correct results.

In this unit we\'ve looked at some of the common errors that you might
try to resolve using the Monitor tool. Monitor should be your go-to tool
when you need more detailed information about what is happening in your
application. By running Monitor regularly, you will be able to identify
abnormal behaviors and issues in your application quicker.
