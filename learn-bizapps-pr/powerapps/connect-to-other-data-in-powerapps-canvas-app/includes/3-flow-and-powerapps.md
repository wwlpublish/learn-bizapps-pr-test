Flow is a standalone component in the Microsoft 365 ecosystem but also a great Power Apps companion. This is because Flow has actions and triggers for interfacing directly with Power Apps. This connection allows you to easily leverage Flow's functionality in your app.

## Business logic

Power Apps is great in scenarios where you have a direct action you want
to be taken after a user performs an activity. An example might be
sending an email after a user submits a new expense report. If you need
to notify someone the expense report was submitted, then you can do that
easily directly from Power Apps.

But what if instead of just notifying someone, you also want to start an approval process. This is a great example of where connecting to Power Automate makes your app stand out. You can have Power Apps trigger a Flow when the user submits the data. Power Automate can then look up who the user's manager is, and send the manager an approval request. Flow will then facilitate getting a response from the manager, updating the data source with the status based on their response, and ultimately sending the original submitter an update.

Approvals are just one example of how you can use Power Automate's native abilities to augment your app's capabilities.

## Data connections

Power Apps offers many of options for connecting to data through the built-in connectors, premium connectors, and custom connecters, however sometimes you need more than that. Some data sources, like custom APIs, can provide data back in a difficult to use format. For example, complex JSON structures are not user-friendly in your app. This is where Power Automate can help. Power Automate has additional actions and expressions natively built in that are better at handling these complex data structures. And more importantly, these actions and expressions can parse through the data and restructure it into a much easier to use object. After the data is parsed, Power Automate can respond to Power Apps with just the friendly data.

Use Flow to interact with complex data sources, restructure the objects,
and then return to Power Apps only the data that you need.


> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2ORdw]


After viewing the video, you can connect Power Apps and
Flow and bring greater functionality into your apps. 
