The OpenAPI document defines a standard and programming language-agnostic interface description for web APIs. It allows both humans and computers to discover and understand the capabilities of a service without having to access to source code, additional documentation, or inspection of network traffic.

![OpenAPI][image-01]

From web API consumers' point of view, with the OpenAPI document, they understand and communicate with the web APIs with spending minimum efforts for implementation.


## What Does OpenAPI Document Do? ##

As the OpenAPI document is a contract, the consumer doesn't have to know its actual implementation. Therefore, the consumer side can quickly build their application without having dependencies on the web API side.

In the previous unit, you used [Azure API Management][az apim], to create a custom connector. At the same time, it also creates a dependency on Azure API Management. In other words, if any change occurs on Azure API Management, your custom connector must be updated to reflect the change.

With the OpenAPI document, you don't have to know where the API is located, nor is up and running because you already know all the information defined in the document. Therefore, you can instantly create a custom connector with this OpenAPI document.

![Many Ways Creating Custom Connector][image-02]

Once you create the custom connector from the OpenAPI document, you will be able to see it on your Power Apps page.

![Custom Connector on Power Apps Page][image-03]


## Why Should Use OpenAPI Document for Custom Connector? ##

There are many advantages of using the OpenAPI document for your custom connector creation. But these two benefits are the most crucial for citizen developers.

* **Remove dependency**: Suppose your professional development team is fully stretched out and temporary unavailable for support you as a citizen developer. In this case, you should be able to create a custom connector by yourself. If the web APIs has already got the OpenAPI document generation capability, you can download the OpenAPI document and create the custom connector with it.
* **Increase agility**: Once you cut the dependency on the professional development team using the OpenAPI document, your cadence of the Power App development will increase because your app development is not relevant to the web APIs any longer.

As you can see the diagram below, OpenAPI document doesn't have to know the actual implementation of the web API, as long as the contract remains the same.

![OpenAPI without Having to Know Web API][image-04]


## Custom Connector from OpenAPI or Azure API Management ##

To create a custom connector, you can use either Azure API Management or OpenAPI document. Then, which one do you choose to create the one? Here are some comparisons between Azure API Management and OpenAPI for custom connectors.

|     | Azure API Management | OpenAPI Document |
| ---:|:---:|:---:|
| API Control | Centralized | Distributed |
| API Structure Layer | Complex | Simple |
| Extra Security Layer | Yes | No |
| Usage Control | Yes | No |
| Extra Cost | Yes | No |
| Architectural Complexity | Higher | Lower |


## Key Takeaways ##

After this unit, you are now able to:

* Know what the OpenAPI document is,
* Understand what advantages the OpenAPI document can bring about the Power Apps development, and
* Compare between Azure API Management and OpenAPI document for custom connectors.


[image-01]: ../media/04-what-is-openapi-and-why-should-use-it-01.png
[image-02]: ../media/04-what-is-openapi-and-why-should-use-it-02.png
[image-03]: ../media/04-what-is-openapi-and-why-should-use-it-03.png
[image-04]: ../media/04-what-is-openapi-and-why-should-use-it-04.png

[az apim]: https://docs.microsoft.com/azure/api-management/api-management-key-concepts

[pa]: https://powerapps.microsoft.com/
