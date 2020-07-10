Using JavaScript and CSS to manipulate client-side visibility and functionality of portal pages can go a long way to satisfy some key business requirements.  To satisfy more complex scenarios, a developer can be creative to utilize other strategies to extend Power Apps portals.

### Third-party libraries

JavaScript can use third-party JavaScript libraries delivering functionality like UX enhancements (masked controls, for example), real-time communications (SignalR), sophisticated UI building (Angular, Vue, React), various third-party business services like address validations, map API, routing services, logistics, and so on.

Power Apps portals create clean responsive layout with predictable element names making it easy to manipulate the data and UI.

As an example of a sophisticated implementation that can be hosted in Power Apps portal and uses Angular framework for communications, take a look at [Set up the event website](https://docs.microsoft.com/dynamics365/customer-engagement/marketing/set-up-event-portal/?azure-portal=true) documentation for Dynamics 365 Marketing.

### API calls

Combined with custom web templates that use Liquid code to deliver *data* instead of HTML, JavaScript can easily call *back* into Power Apps portal to retrieve the data and then use this data to create alternative UX. For example, instead of using Entity List calendar view, it's possible to retrieve list data in json format instead and then use third-party calendaring libraries like FullCalendar to create sophisticated calendar visualization. Or retrieve opportunity data and use third-party charting JavaScript library for sophisticated interactive charting.

> [!IMPORTANT]
> Using web templates it is only possible to implement REST service for GET operations. No other operation like PUT is supported by Liquid code.

### Companion app

There are situations where you may want to communicate securely with external services while maintaining the security context, for example, to process online payments. Power Apps portals enable this scenario by providing support for [OAuth 2.0 implicit grant flow within your portal](https://docs.microsoft.com/powerapps/maker/portals/oauth-implicit-grant-flow/?azure-portal=true).

This feature allows a customer to make client-side calls to external APIs and secure them by using OAuth implicit grant flow. The identity information of a signed-in user is passed in a secured manner to the external calls.

In this scenario, you build a custom web application and Power Apps portals would communicate to this application using JavaScript to call the API.  

As you can see, CSS and JavaScript enable a number of integration and extensibility scenarios ranging from simple UI adjustments, validation and data input, to sophisticated client-side applications interacting with third-party services.
