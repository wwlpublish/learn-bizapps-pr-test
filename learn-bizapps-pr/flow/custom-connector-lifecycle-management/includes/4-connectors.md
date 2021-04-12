Not every task in a custom connector lifecycle can be performed using custom connector user interface in the maker portal. The **paconn** command-line tool should be used as part of your custom connector lifecycle for the following tasks:

-   Downloading a custom connector for editing and source controlling after creating or editing it using the maker portal. For example, to add any custom connection properties you must download and edit the files.

-   Creating a new custom connector in an environment from the individual downloaded definition files. The connector created is not contained within a solution. For example, this could be used to create the same connector with a different unique ID in the same environment if you wanted a copy while keeping the original intact.

-   Updating an existing connector. This can be used to update a standalone custom connector or one that is contained in a solution. For example, you can update a connector after editing connection properties.

-   Validating your connector. This is a required step for certification but many of the errors detected can improve the quality of any custom connector.

Use care to ensure someone is not editing your custom connector using the portal and the downloaded files at the same time to avoid losing changes. When you upload using the command-line tool, it does not check for conflicts and just replaces the existing definition without any merging.

## Installing command-line tool

The **paconn** command-line tool requires Python 3.5 or above. Python should be installed first followed by **pip install paconn** command to install the tool. Detailed [installation instructions](https://docs.microsoft.com/%20connectors/custom-connectors/paconn-cliy/?azure-portal=true) are available.

## Setting file or parameters

You can configure the tool options using either command-line parameters when executing a command or by using a settings.json file. Specify a settings file using the -settings or -s parameter. When the settings file is used the rest of the command-line parameters are ignored.

Using the settings file can make it easier to run commands multiple times. When you download a custom connector, a settings.json file is created as part of the download. The following is an example of a settings.json file:

> [!div class="mx-imgBorder"]
> [![Screenshot example of the settings file contents.](../media/settings-json.png)](../media/settings-json.png#lightbox)

You can review the [detailed list of settings](https://docs.microsoft.com/connectors/custom-connectors/paconn-cli?azure-portal=true#settings-file) for more specific on values for each setting.

## Authenticating

To use any of the paconn commands, you must authenticate first using the **paconn login** command. This command will give you a code and direct you to [https://microsoft.com/devicelogin](https://login.microsoftonline.com/common/oauth2/deviceauth) where you will sign in with your account and provide that code.

> [!div class="mx-imgBorder"]
> [![Screenshot of the authentication dialog asking for the device code.](../media/enter-code.png)](../media/enter-code.png#lightbox)

Once the interactive sign-in is completed this will establish a session to be used by other **paconn** commands. The session will expire after some time and will have to be reestablished to continue using the tool. You can force an end of the session at any time using the **paconn logout** command.

Since an interactive user sign-in is required to authenticate, the command-line tool can be used with attended automation scripts but would not work in unattended scenarios like a build pipeline.

## Downloading

Use the **paconn download** command to download an existing connector. If you do not provide any parameters, you will be prompted to pick from an environment list and then from a list of connectors in the selected environment.

Use the -e parameter to preselect a specific environment and skip the environment list. The easiest way to get an environment identifier is from the maker portal URL.

> [!div class="mx-imgBorder"]
> [![Screenshot of the environment URL showing how to pull out the identifier.](../media/maker-portal-url.png)](../media/maker-portal-url.png#lightbox)

Using this would present a choice of just the connectors in that environment.

> [!div class="mx-imgBorder"]
> [![Screenshot showing a list of connectors from the command line tool.](../media/environment-connectors.png)](../media/environment-connectors.png#lightbox)

Instead of selecting a connector interactively you can specify a particular connector by passing connector identifier in the -c parameter. The easiest way to get the connector identifier is to download the connector once and then copy the value from the settings file.

> [!div class="mx-imgBorder"]
> [![Screenshot showing where to find the connector ID in the settings file.](../media/connector-identifier.png)](../media/connector-identifier.png#lightbox)

Then your command would be the following:

```
paconn download -e d80faec4-eb14-4076-9681-9b46b97adbfd -c shared_cr83e-5fcontoso-20invoicing-5f20493607d490e1e0
```

This would download your connector files without any prompts.

The other advantage of using identifiers is that, unlike the order numbers in the selection lists, the identifiers do not change as environments and connectors are created or deleted.

The files downloaded are placed in a folder named using the connector ID. If the directory already exists the command will fail and you must manually remove the folder. The downloaded files consist of the following four files:

-   **apiDefinition.swagger.json** - This is the API definition file describes the API for the custom connector using the OpenAPI specification.

-   **apiProperties.json** - The API properties file contains properties for the custom connector and policy templates.

-   **Icon.png** - The icon file is a small image representing the custom connector icon.

-   **settings.json** - This is a preconfigured settings file you can use instead of providing parameters to each command.

## Creating

The **paconn create** command would create a custom connector in the target environment using the specified definition files. The API definition, API properties, and icon must be specified by either parameters or a settings file. The create command will prompt for any other parameters like environment ID if not provided. The following is an example of the create command:

```
paconn create ^
  -e [Power Platform Environment GUID] ^
  --api-prop [Path to apiProperties.json] ^
  --api-def [Path to apiDefinition.swagger.json] ^
  --icon [Path to icon.png] ^
  --secret [The OAuth2 client secret for the connector]
```

If your connector uses OAuth2 then you can use the -secret parameter to specify the client secret value.

## Updating

The **paconn update** command updates an existing custom connector in the target environment using the specified definition files. The API definition, API properties and icon must be specified by either parameters or a settings file. The update command will prompt for any other parameters like environment ID if not provided. The following is an example of the update command:

```
paconn update ^
  -e [Power Platform Environment GUID] ^
  -c [Connector ID] ^
  --api-prop [Path to apiProperties.json] ^
  --api-def [Path to apiDefinition.swagger.json] ^
  --icon [Path to icon.png] ^
  --secret [The OAuth2 client secret for the connector]
```

> [!IMPORTANT]
> Update will replace the definition in the target environment even if it had been modified since you downloaded your copy. It is important to coordinate with anyone else making updates to the connector.

The Microsoft Power Platform Connectors CLI is an essential tool when you are building custom connectors. Use it as part of your lifecycle to help make changes to the connectors and to download copies of the connector definition files for source control.