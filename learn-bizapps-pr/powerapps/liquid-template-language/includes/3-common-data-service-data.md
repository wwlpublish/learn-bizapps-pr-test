Portal makers can use a template language to build the output that combines static content. Similarly, makers can use a template language when working with multiple pages and dynamic content that comes from Common Data Service and making changes from one page to the next. The static elements are written in HTML, and the dynamic elements are written in Liquid. The Liquid elements act as placeholders: Before the output is sent to the browser, the Liquid elements are replaced by data from Common Data Service.

Power Apps portals implements numerous extensions that are specific to the portals and Common Data Service.

[Available Liquid objects](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-objects/?azure-portal=true) include:

- Page
- User
- Website
- Generic entities

[Power Apps Common Data Service entity tags](https://docs.microsoft.com/powerapps/maker/portals/liquid/portals-entity-tags/?azure-portal=true) include:

- chart
- Power BI
- entitylist
- entityview
- fetchxml

In the following example, the **Active Currencies** view is being loaded and all returned records are displayed. In portals Studio, this code produces output because of the implicit design-time privileges of the maker. However, on the portal, the user needs to have Read privileges assigned on the **currency** entity for the fragment to return any data.

```twig
{% entityview logical_name:'transactioncurrency', name:'Active Currencies' %}
<p>We support {{ entityview.total_records }} currencies.</p>
<ul>
  {% for cur in entityview.records -%}
  <li>{{ cur.currencyname }}</li>
  {% endfor %}
</ul>
{% endentityview %}
```

The output would look like the following example:

> We support 4 currencies.
>
> * Australian dollar
> * Canadian dollar
> * Euro
> * US dollar

By using Liquid in Power Apps portals, you can:

- Add dynamic content directly to webpage content or to a content snippet.
- [Store source content by using web templates](https://docs.microsoft.com/dynamics365/customer-engagement/portals/store-content-web-templates/?azure-portal=true), entirely through configuration within Power Apps, for use throughout the Power Apps portals content management system.
- [Render a website header and primary navigation bar](https://docs.microsoft.com/powerapps/maker/portals/liquid/render-site-header-primary-navigation/?azure-portal=true), entirely through configuration within Power Apps.

In these scenarios, you'll have dynamic access to Power Apps portals features, such as site settings, content snippets, entity lists and forms, and so on.

> [!IMPORTANT]
> Liquid statements are only processed as *output*. Liquid does not have the capacity to extend server-side code that deals with user interactions such as form submissions.
