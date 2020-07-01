You have a variety of configuration-only tools and features when building a Power Apps portal application. Examples include entity lists, entity forms, web forms, and the ability to integrate other technologies such as SharePoint and Power BI. You may encounter features that are not easily configured using the available low-code or no-code features.

Liquid template language in portal pages and templates begins to extend your web application and allows you to manipulate and display content in a variety of ways.

Power Apps portals features can also be further extended using standard web technologies such as HTML, JavaScript, and CSS.

You may also encounter situations where you need to update or create data in the Common Data Service without submitting an entity form or a web form. A common method is to build a standalone web application with an API that can be called from the Power Apps portal, that will act as a liaison to update the Common Data Service.

Another common question is that once you have configured and customized your portal, how can you ensure that your work is saved in a source control system and how can it be deployed to a test or production portal?

## Server-side extensibility

Power Apps portals do not support client-side Business Rules, JavaScript web resource, or Power Apps Components Framework controls that are commonplace with the model-driven forms. As a result, portal deployments sometimes get blocked because expectations of the same or similar form behavior cannot be met. Instead, entity lists, entity forms, and web forms include a Custom JavaScript option that allows developers to add scripts implementing the equivalent functionality.

However, the portals are based on model-driven apps underpinned by Common Data Service. In fact, portals deliver functionality that is already available in a model-driven app, but to the portal users. That means that:

* Entity-scope Business Rules still apply as they are executed on the server
* Workflows and Power Automate flows still get triggered regardless whether triggering action was executed inside a model-driven app or a portal. The workflows can also be called explicitly by using form configuration on the portal.
* When a portal user interacts with the Common Data Service records, the server-side code runs as usual. Developers can pass relevant portal context to the plugins when the records are updated by the portal users using entity forms. That adds some server-side code extensibility to the portals and enables various integration scenarios.
