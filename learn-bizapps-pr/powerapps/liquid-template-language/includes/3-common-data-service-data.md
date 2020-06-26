Portal makers can use a template language to build the output that combines static content, the same for multiple pages, and dynamic content, that comes from Common Data Service (CDS) and changes from one page to the next. The static elements are written in HTML, and the dynamic elements are written in Liquid. The Liquid elements act as placeholders: before the output is sent to the browser, the Liquid is replaced by data from CDS.

Power Apps portals implement a number of extensions specific to the portals and Common Data Service.

[Available Liquid objects](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-objects/?azure-portal=true) include:

* `page`
* `user`
* `website`
* even generic `entities`

[Power Apps Common Data Service entity tags](https://docs.microsoft.com/powerapps/maker/portals/liquid/portals-entity-tags/?azure-portal=true) include:

* `chart`
* `powerbi`
* `entitylist`
* `entityview`
* `fetchxml`

In the following example we load Active Currencies view and display all returned records. In Portal Studio this code produces output because of the implicit design-time privileges of the maker. On the portal, however, the user would need to have read privilege on the **currency** entity for the fragment to return any data.

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

This is what the output would look like:

> We support 4 currencies.
>
> * Australian Dollar
> * Canadian Dollar
> * Euro
> * US Dollar

By using Liquid in Power Apps portals, you can:

* Add dynamic content directly to the content of either a web page or of a content snippet.
* [Store source content by using web templates](https://docs.microsoft.com/dynamics365/customer-engagement/portals/store-content-web-templates/?azure-portal=true), entirely through configuration within Power Apps, for use throughout the Power Apps portals content management system.
* [Render a website header and primary navigation bar](https://docs.microsoft.com/powerapps/maker/portals/liquid/render-site-header-primary-navigation/?azure-portal=true), entirely through configuration within Power Apps.

In all of these scenarios, you'll have dynamic access to Power Apps portal features, such as site settings, content snippets, entity lists and forms, and so on.

> [!IMPORTANT]
> Liquid statements are only processed as an *output*. Liquid does not have the capacity to extend server-side code that deals with user interactions such as form submissions.
