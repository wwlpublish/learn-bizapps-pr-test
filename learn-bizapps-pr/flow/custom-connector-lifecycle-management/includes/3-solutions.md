Solutions are containers that include the components of your solution and can be used to transport your components from one environment to another. Custom connectors are one of the available component types along with apps, flows, and many other item types. Solutions can be unmanaged or managed.

-   **Unmanaged solutions** - Used in development environments while you make changes to your components. Unmanaged solutions can be exported either as unmanaged or managed. Exported unmanaged versions of your solutions should be checked into your source control system. A tool named Solution Packager can be used to prepare solutions to be checked in. You can automate this process using the Power Platform Build tools.

-   **Managed solutions** - Used to deploy to any environment that is not a development environment for that solution. Managed solution components cannot be directly modified in the managed solution. You can however include the component in an unmanaged solution and make changes there. This creates a dependency on the managed solution. Managed solutions can be serviced independently from other managed solutions in an environment. While you can manually export an unmanaged solution as managed, managed solutions are recommended to be generated as a build artifact from an automated build process.

The following highlights building a custom connector in a development environment and installing a copy in test as a managed solution:

> [!div class="mx-imgBorder"]
> [![Diagram of distributution of a solution from development to test environments.](../media/development-test-environments.png)](../media/development-test-environments.png#lightbox)

When you build a custom connector, it is recommended first to create a solution for your connector and then to create the custom connector inside that solution. One solution can contain multiple connectors. Currently, it recommended that your apps and flows that use the connectors are contained in their own solution, separate from the one containing any custom connectors. This allows a proper reference and dependency to be established and tracked in the solution that has your connectors. Currently, placing the custom connector in the same solution as the apps and flows that use it, does not work.

## Connectors

When your connector is transported from one environment to another using a solution all the definitions you configured are maintained. This includes triggers, actions, policy templates, and connection properties. Any sensitive information on the custom connector definitions such as OAuth client ID, secret, and resource are not transported with the solution. Prior to first use of the connector by an application or flow you must edit the custom connector and provide those values. The same values must be provided anytime you update the connector and they will be blanked out by the import of an update.

## Connections

When an app or a flow uses your connector in a solution a connection reference is created to abstract the actual connection that is specific to an environment. The connection reference becomes a component in the solution that uses the custom connector and is transported from one environment to the next. When you import a solution that has a connection reference to a custom connector, during the import process it will prompt for establishing a connection that is associated with that connection reference. The connection reference ensures that when updates are done you do not have to reestablish the connection each time the solution is imported. The following image shows the first time a solution is imported that references a custom connector as it prompts the user to provide a connection.

> [!div class="mx-imgBorder"]
> [![Screenshot showing setting connection reference to a valid connection upon import.](../media/import-solution.png)](../media/import-solution.png#lightbox)

When you are ready to update your custom connector, make the changes in your development environment and then export the solution as managed. You then would import the new managed solution version into your other environments. All the changes you have made become available for apps and flows once the upgrade is completed; except for sensitive configuration information that must be entered each time and no other editing required each time an update is done.

Using solutions to manage the lifecycle of your custom connector provides a consistent way of doing it with how you manage other Power Platform resources. The same techniques you use for automating the export, import, and source control of your assets can be consistently applied for custom connectors as well. Later in this module we will look at automating the process using Power Platform build tools. You can read more about the Power Platform ALM capabilities in the [product documentation](https://docs.microsoft.com/power-platform/alm/?azure-portal=true).

