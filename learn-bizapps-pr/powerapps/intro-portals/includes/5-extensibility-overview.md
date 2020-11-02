Power Apps portals is considered a no-code, low-code solution to building portal apps. However, situations might occur where certain requirements necessitate extended development. An advanced maker or professional developer can extend a Power Apps portal in several ways.

## Liquid

Liquid is an open-source markup language that can be embedded into content (webpages content, content snippets) and web templates.  Liquid is used to add dynamic content to webpages and can also be used to surface Common Data Service records dynamically.

For more information, see [Work with Liquid templates](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-overview).

## Web templates

Portals are provisioned with a predefined set of web templates that define how a webpage is structured. Portal customizers can modify or create new web templates to address specific requirements. For example, a web template can be created to display static and dynamic content in a specific layout.

For more information, see [Create a custom page template](https://docs.microsoft.com/powerapps/maker/portals/liquid/create-custom-template).

## JavaScript

Custom JavaScript code can be embedded in different portal assets such as webpages, web templates, entity forms, and entity lists.  JavaScript can be used to enhance the client interface, add complex user input validation, or call external web services. Scripting in Power Apps portals is specific to portal components and does not use scripts from model-driven apps in entity forms or views.

For more information, see [Add custom JavaScript](https://docs.microsoft.com/powerapps/maker/portals/configure/add-custom-javascript).

## CSS

Cascading Style Sheets (CSS) can be used to control the appearance and the behavior of portal webpages. CSS can also implement specific portal features instead of JavaScript code, for example, to hide certain page elements.

For more information, see [Edit CSS for themes in Power Apps portal](https://docs.microsoft.com/powerapps/maker/portals/edit-css).

## Companion apps

Some situations might occur where custom code is required to create or update data in Common Data Service without submitting an entity form or web form. A common technique is to create a custom web app outside of Power Apps portals, by using the Web Apps feature of Azure App Service or Azure Functions, that will expose an API that can be securely called from JavaScript on portal pages. The web app can interact with data by using the standard Common Data Service web API.
