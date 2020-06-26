It is important to understand that Power Apps portals are built on top of the Common Data Service (CDS). They extend functionality to both internal and external audiences but this functionality must already be present in either a custom Power App using the Common Data Service or a Dynamics 365 first-party application. For example, if you do not have Dynamics 365 Field Service installed, you will not be able to install the Field Service portal solution.

On the other hand, if you have Dynamics 365 Sales installed, you will be able to configure case management functionality in your portal without any code. In other words, Power Apps portals are **web enablers** of Power Apps for the internal and external audiences.

This architecture comes with a major benefit. All the differentiating features of **model-driven Power Apps** are the features of **Power Apps portals** as well: centralized management, Common Data Model, roles and permissions, forms and views, business rules, declarative workflows and actions, plug-in architecture, integration with other services, Common Data Service extensibility, audit, and more.

Power Apps portals deliver complete content management system out of the box, with all content stored in the Common Data Service. That means the content can be edited not only via the Portal Studio, but also directly using the Portal Management app. Content can be secured using the robust Common Data Service security model.

## Fit or gap analysis

Let's take a look at various scenarios when portals can be a good fit and others where portals probably wouldn't deliver the same value.

### When to consider

* Expose Common Data Service in a simple, secure web interface. This may be external users (like customers and partners) or internal users that do not require full-featured Power Apps.
* Provide access to simple community forums, self-service knowledge base and web forms for service requests, cases, or other Common Data Service entities.
* Requirement for a website to read, update, and create Common Data Service records in an out of the box, ready to deploy manner.
* Limited resources and budget for large-scale web development, business-user, and no-code configuration requirements.
* Need for responsive design, Portal content accessible across all resolutions, devices, and browsers.
* Multi-lingual implementations where you need to serve audiences of different languages or are required to provide multi-language services by law.
* Ability to surface and transact selected information from the Common Data Service to anonymous public access.
* Secure connection to the Common Data Service to key external stakeholders using either the built-in authentication or external authentication providers such as Azure B2C, Facebook, Google, LinkedIn and more.

### When to exercise caution

* Majority of data to surface on the web resides in an external (non-Common Data Service) system.
* Heavy requirements around document management, indexing and searching.
* eCommerce requirements including processing high volume of payments and maintaining an online store.
* Use cases that are more appropriate for direct model-driven or canvas apps.

## Performance considerations

Power Apps portals do autoscale as they get more traffic. How much a portal scales depends on how much CDS capacity is purchased and assigned to the environment the portal is placed in. When planning and building a portal it is important to ensure that the implementation is done in a scalable manner using best practices and tools like solution checker, app checker, and portal checker, etc. It is also important to recognize portal scalability limitations, for example allowing visitors to upload files without restricting file size or type may have a detrimental effect on the overall portal performance.
