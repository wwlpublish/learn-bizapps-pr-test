Liquid extensions in Power Apps portals give portal makers access to the Common Data Service. Entity permissions govern all data accessed by Liquid objects and tags and it's not possible to switch it off. It also makes the output truly dynamic as it may vary with the current portal user, their Web Roles, and associated Entity Permissions records.

To improve rendering performance and alter the template in response to the current user's privileges, developers can assert particular access rights before executing the data retrieval. For example, instead of trying to access contact records, check whether the user has read privileges for the contact entity and handle the response appropriately without retrieving the data.

Consider this Liquid fragment:

```twig
{% if user %}
<p>
  {% assign account = entities.account[user.parentcustomerid.id] %}
  {% if account and account.permissions.can_read %}
    Company: {{account.name}}
  {% else %}
    Unknown company
  {% endif%}
</p>  
{% endif %}
```

In this example, the code does the following:

1. Displays data only if the user is signed in.
1. Retrieves the parent account record.
1. Checks that the account exists and the user has permissions to read that record. The **Permissions** property of the **entity** object returns the [Entity Permissions](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-objects#entity-permissions/?azure-portal=true) object that can be used to verify specific privileges.
1. Displays name of the account if available, otherwise displays the "Unknown company" message.

You can test the code inside the Portal Studio and then by browsing to the site. Check the different values rendered by the code because of the maker privileges within the Studio.

You can find additional information on working with Liquid in Power Apps portals, code samples, a full list of available objects, tags, supported data types, and conditional operators here: [Work with Liquid templates](https://docs.microsoft.com/powerapps/maker/portals/liquid/liquid-overview/?azure-portal=true).
