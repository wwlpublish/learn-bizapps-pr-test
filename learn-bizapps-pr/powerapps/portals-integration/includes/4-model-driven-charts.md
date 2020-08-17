You add a chart to a web page by using the Liquid tag [chart](https://docs.microsoft.com/powerapps/maker/portals/liquid/portals-entity-tags#chart). As with any Liquid code, you can add the `chart` tag in the page content inside a content snippet, or insert it as part of a web template.

```twig
{% chart id:"EE3C733D-5693-DE11-97D4-00155DA3B01E" viewid:"00000000-0000-0000-00AA-000010001006" %}
```

### Parameters

There are two parameters to provide with the `chart` tag.

* **id**. Visualization identifier of the chart. You can get this by exporting the chart.

* **viewid**. Entity view identifier when opened in the model-driven view editor. If not specified, default view will be used.

Surfacing a model-driven chart in Power Apps portals doesn't require any additional configuration. Only system charts and system views are supported in configuration.

* To obtain the `chart id`, export the chart definition from a model-driven app and look for `visualizationid` in the exported chart file.
* To obtain the `viewid`, start customizing the view and copy the view ID from the URL.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Avkv]

Read privilege is asserted for the target entity being queried in the chart. To allow users to view the chart, you must ensure the appropriate Entity Permission records are created and assigned to applicable web roles. If permission is not granted, the user will see an access denied message.

> [!NOTE]
> Different users may see different resulting charts based on their specific entity permissions

Some chart types and some out-of-the-box charts aren't supported. See [Unsupported charts and chart types](https://docs.microsoft.com/powerapps/maker/portals/configure/add-chart#unsupported-charts-and-chart-types/?azure-portal=true).

For more information and step-by-step instructions, see [Add a chart created in a model-driven app to a webpage in portal](https://docs.microsoft.com/powerapps/maker/portals/configure/add-chart/?azure-portal=true).
