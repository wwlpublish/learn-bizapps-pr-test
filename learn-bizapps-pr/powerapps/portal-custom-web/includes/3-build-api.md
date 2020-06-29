**Page Template** has a setting that specifies whether the page should use the common Website header and footer templates when Web Template is used. 

![Page template setting to use site header and footer](../media/3-page-template.png)

When Website header and footer are not used, the template assumes responsibility for generating the entire page output. In the case that you're rendering HTML, this means everything from the doctype to the root `<html>` tags, and everything in between. There are couple scenarios where this could be useful:

* Special purpose pages that need to look differently from the rest of the portal, for example, marketing campaign landing pages.

* Web template generates non-HTML content, returning data in XML, json, or other formats.

For example, you can create a web template that returns a list of accounts or any other data the current user has access to, in `json` format. 

```twig
{% entityview logical_name:'account', name:'Active Accounts' %}
[
{% for acc in entityview.records -%}
    {
        "name": "{{ acc.name }}",
        "phone": "{{ acc.telephone1 }}"
    }{% unless forloop.last %},{% endunless %}
{% endfor -%}
]
{% endentityview %}
```

> [!NOTE]
> In this example, instead of the `entityview` tag,  you can use FetchXml query inside the `fetchxml` tag. Using inline FetchXml adds some flexibility to the query. The query can be built dynamically by using template parameters or even `request` object containing query string parameters of a current HTTP page request.

This template would be used without a header and footer with MIME type set to `application/json`. The output would be something like

```json
[
  {
      "name": "A Datum Corporation",
      "phone": "425-555-0182"
  },
  {
      "name": "A Datum Fabrication",
      "phone": "303-555-0134"
  },
  {
      "name": "A Datum Integration",
      "phone": "512-555-0163"
  },
  {
      "name": "A. Datum",
      "phone": "+86-23-4444-0100"
  },
  {
      "name": "Adventure Works",
      "phone": "+27-264-1234567"
  }
]
```

The page using this web template wouldn't be used by users in a browser but, instead, it will be called from JavaScript code, effectively defining an API endpoint for your solution. JavaScript on another page would be able to load and render this data as required.

Of course, authorization will be in place and accessing CDS data using this "headless" template is no different if the output was rendered as HTML. The calling page would typically require user authentication prior to calling the endpoint.
