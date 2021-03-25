
Making your custom connector open-source and certified can make it easily available to all users. By making it open source, your connector will be published to the [Power Platform GitHub repository](https://github.com/Microsoft/PowerPlatformConnectors/?azure-portal=true). From there, any user can import your custom connector definition into an environment and use it or make contributions to your connector for you to consider adopting. When you create a custom connector, it is only available to you and the users you explicitly share the connector with. For a connector to be visible in the list of the official connectors for any user of Power Automate, Power Apps, or Logic Apps, it needs to be certified.

## When to certify a custom connector

There are many reasons to certify your custom connector but ease of use, visibility, and expanding the reach of your API are among the top reasons. Certify your custom connector if it provides access to an API that is useful to a broad audience and not internally focused. You do not have to host the API underlying service on Microsoft technologies. In fact, connectors are great for integrating Power Platform solutions with non-Microsoft solutions. Connectors can be certified for free or paid APIs.

Certified connectors are reviewed to ensure they meet the [certification criteria](https://docs.microsoft.com/connectors/custom-connectors/submit-certification#certification-criteria/?azure-portal=true) prior to publishing. A key requirement is you must either own the underlying service or present explicit rights to use the API and provide a user scenario that fits well with the products. There is no charge for the initial certification or updates to the connector. In the next topic, we dive deeper into the certification process.

## When to make a custom connector open-source

Any custom connector you build is a candidate for open-sourcing if you think others could benefit from using it. When you certify a connector, one of the first steps is open-sourcing the definition. The first thing you should do is check to see if there's an existing custom connector definition in the repository for the API that you're building for. If you find one, it would be best to contribute your changes to make that one better by submitting a pull request rather than try to create a duplicate connector.

The following are good and bad examples of when to open source a custom connector.

| **Good candidate to open-source** | **Bad candidate to open-source** |
| --------------------------------- | ---------------------------------|
| Connector for an API that is publicly available for anyone to use | Connector for a private API that is only available inside your company network |

Most contributions require you to agree to a Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant the rights to use your contribution. For details, visit [https://cla.microsoft.com](https://cla.microsoft.com/?azure-portal=true).

In the GitHub repository there are two main folders that contain the connectors, custom-connectors and certified-connectors.

The custom-connectors folder contains fully functional connector samples that can be deployed to the Power Platform for extension and use. These samples may not be certified connectors but are created and maintained by the open-source community to offer useful scenarios or examples of connector concepts.

The certified-connectors folder contains certified connectors that are already deployed and available out-of-box within the Power Platform for use. A requirement of Microsoft connector certification program is that new certified connectors be open-sourced for community contributions. The Microsoft Connector Certification Team manages the certified-connectors folder to ensure that within the master branch, the connector version is identical to that deployed in the Power Platform. The dev branch is maintained by the connector owner and the Microsoft Connector Certification Team to allow community development of the connector prior to certification and deployment of a version.

To contribute to the GitHub repository, you start by forking (taking your own copy) of the repository. The steps are documented [here](https://github.com/Microsoft/PowerPlatformConnectors.md?azure-portal=true#creating-a-fork). Once that's completed, you're ready to prepare your connector for contribution using a pull request. You can download your connector assets using the Power Platform Connector CLI.

## Download using Power Platform Connector CLI

To prepare the necessary files to open-source your connector, use the paconn download command from the [CLI](https://docs.microsoft.com/connectors/custom-connectors/paconn-cli/?azure-portal=true).

Download the custom connector files by running:

`paconn download`

When you run this command, it will walk you through a device login to allow paconn to access your Power Platform environment on your behalf. Once authenticated, it will provide you with a list of environments to select from followed by a list of connectors to select.

If you know your environment ID and connector ID, you can use the following command-line syntax to avoid being prompted:

`paconn download -e [Power Platform Environment GUID] -c [Connector ID]`

The download includes the following four files:

- **apiDefintion.swagger.json** - OpenAPI definition for your connector that includes, for example, all triggers and actions.

- **apiProperties.json** - defines policy templates and other extended connector properties that aren't part of OpenAPI specifications.

- **icon.png** - a small icon used to represent the service in the designer when the connector is used.

- **settings.json** - used instead of providing parameters to paconn.

Making your customer connector open source and certified are great ways to get your API more visibility. By contributing the connector definition to the open-source repository your custom connector becomes available for others to easily use. When someone uses a certified connector, they are using a definition that gets updated automatically when you publish updates. When they use the open-sourced connector definition, they have to apply updates to their copy themselves. In the rest of this module, we will be looking at how to certify your custom connector and how to manage its lifecycle as you evolve it.
