# Portals extensibility overview

Power Apps portals is considered a no-code, low-code solution to build portal apps.  However, there are situations where certain requirements require extended development.  There are a number of different ways and advanced maker or professional developer can extend Power Apps portal.

## Liquid

Liquid is an open-source mark-up language that can be embedded into content (web pages content, content snippets) and web templates.  Liquid is used to add dynamic content to web pages and can also be used to surface Common Data Service records dynamically.

For more information see [Work with Liquid templates](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-overview).

## Web Templates

Portals are provisioned with a predefined set of Web Templates which define how a web page is structured.  Portal customizers can modify or create new web templates to address specific requirements.  For example, a web template can be created to display static and dynamic content in a specific layout.

For more information see [Create a custom page template](https://docs.microsoft.com/powerapps/maker/portals/liquid/create-custom-template).

## JavaScript

Custom JavaScript code can be embedded in different portal assets such as web pages, web templates, entity forms and entity lists.  JavaScript can be used to enhance the client interface, add complex user input validation, or call external web services.  Note that scripting in Power Apps portals is specific to portal components and does not use scripts from model-driven apps in entity forms or views.

For more information see [Add custom JavaScript](https://docs.microsoft.com/powerapps/maker/portals/configure/add-custom-javascript).

## CSS

Cascading Style Sheets (CSS) can be used to control the look and the behavior of the portal web pages. CSS can also implement specific portal features instead of the JavaScript code, for example to hide certain page elements.

For more information see [Edit CSS for themes in Power Apps portal](https://docs.microsoft.com/powerapps/maker/portals/edit-css).

## Companion Apps

There are some situations where custom code is required to create or update data in the Common Data Service without submitting an entity form or web form.  A common technique is to create a custom web app outside of Power Apps portals -- using either a custom Azure Web Apps or Azure Functions -- that will expose an API that can be securely called from the JavaScript on portal pages. The web app can interact with the data using the standard Common Data Service Web API.
