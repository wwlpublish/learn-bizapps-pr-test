Many authentication options supported by Power Apps portals are configured using site settings. Site settings are stored in the Site Settings entity where each setting is defined as a Name/Value pair.

To view site settings, open Power Apps portals App by navigating to [Dynamics 365 Home](https://home.dynamics.com/?azure-portal=true) and selecting Power Apps portals. In the app, select **Site Settings** in the navigation panel.

> [!div class="mx-imgBorder"]
> [![Active site settings](../media/active-site-settings.png)](../media/active-site-settings.png#lightbox)

Only a few of the many available authentication-related site settings are installed when you provision a starter portal. Settings that are not created assume their documented default values.

## Setting example

As an example of the need to add a site setting, when you provision a Custom Portal, the form for registering a new local account requires both an email address and a username.

> [!div class="mx-imgBorder"]
> [![Register with username](../media/register-username.png)](../media/register-username.png#lightbox)

To enable a local account sign-in using an email address instead of a username, you can add the `Authentication/Registration/LocalLoginByEmail` setting and set it to `True`.

> [!div class="mx-imgBorder"]
> [![Add new site setting](../media/add-new-site-setting.png)](../media/add-new-site-setting.png#lightbox)

As the result of this new site setting, both the form and the process for registering a new local account now require an email address only.

> [!div class="mx-imgBorder"]
> [![Register with email address only](../media/register-email-address.png)](../media/register-email-address.png#lightbox)

And the sign-in form now refers to **Email** instead of **User name**.

> [!div class="mx-imgBorder"]
> [![Sign-in by email](../media/local-sign-email.png)](../media/local-sign-email.png#lightbox)

> [!NOTE]
>Where a function is enabled by default, a site setting needs to be created to disable that function. For example, adding `Authentication/Registration/ResetPasswordEnabled = False` setting is required to disable password reset feature for local authentication.

## Authentication settings categories

All authentication-related site settings start with **Authentication**.

Authentication settings can be grouped into three broad categories, each covering settings to control various aspects of authentication processes.

| Group                                | Description                                                  |
| ------------------------------------ | ------------------------------------------------------------ |
| **Authentication/Registration**      | The most broad group of settings covering options like enabling/disabling specific authentication methods, controlling invitation behaviors, password resets, confirmation emails, two-factor authentication, and many more. |
| **Authentication/UserManager**       | [User credential validation](https://docs.microsoft.com/powerapps/maker/portals/configure/set-authentication-identity#user-credential-validation/?azure-portal=true) are settings for adjusting username and password validation parameters. Validation occurs when users sign up for a new local account or change a password. Also included are [user account lockout settings](https://docs.microsoft.com/powerapps/maker/portals/configure/set-authentication-identity#user-account-lockout-settings/?azure-portal=true). |
| **Authentication/ApplicationCookie** | It's not uncommon to see enterprise requirements for specific cookie behaviors such as expiration time span. This group defines [Cookie authentication site settings](https://docs.microsoft.com/powerapps/maker/portals/configure/set-authentication-identity#cookie-authentication-site-settings/?azure-portal=true) for modifying the default authentication cookie behavior. |

Detailed explanation of various options and descriptions of the individual site settings are available in the [Set authentication identity for a portal](https://docs.microsoft.com/powerapps/maker/portals/configure/set-authentication-identity/?azure-portal=true).
