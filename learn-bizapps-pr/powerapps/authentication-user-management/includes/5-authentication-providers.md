## Local authentication

Local authentication is the common forms-based authentication uses the contact records for authentication. Local authentication settings are configured using portal site settings, including disabling local sign-in option for the entire portal: [Set authentication identity for a portal](https://docs.microsoft.com/powerapps/maker/portals/configure/set-authentication-identity/?azure-portal=true).

## External authentication

When external authentication is used, credentials and password management are handled by third-party identity providers. Supported authentication protocols include:

* WS-Federation and SAML 2.0.
* OAuth2 (Microsoft, Twitter, Facebook, Google, LinkedIn, Yahoo ).
* OpenID Connect (Azure Active Directory, Azure AD B2C).

## Authentication and provider configuration

Setting up authentication is a core customization in any portal. Simplified identity provider configuration in Power Apps portals provides in-app guidance for identity provider setup and abstracts setup complexities. Makers and administrators can easily configure the portal for supported identity providers by following steps documented at [Simplified authentication and identity provider configuration](https://docs.microsoft.com/powerapps/maker/portals/configure/use-simplified-authentication-configuration/?azure-portal=true).

> [!div class="mx-imgBorder"]
> [![Identity providers](../media/portal-authentication-settings.png)](../media/portal-authentication-settings.png#lightbox)

## Azure Active Directory B2C

A portal owner can configure the portal to accept Azure Active Directory (AD) B2C as an identity provider. Azure AD B2C enables external customer sign-ins through local credentials and federation with various common social identity providers.

> [!IMPORTANT]
>Azure AD B2C identity provider is the recommended provider for authentication. If third-party provider support, e.g. Facebook, is required then it can be configured in Azure AD B2C instead of the portal.

The advantages of using Azure AD B2C:

* Customer identity and access management, not just authentication.
* Customizable. Use built-in templates or build sophisticated custom policies.
* Branded experience for your customers.
* Platform-agnostic, supports third-party providers.
* Identity protection via security controls and multi-factor authentication.
* Supports open standards and all technology stacks.
* Scalable and reliable, built and supported by Microsoft, backed by SLA.

### Migration to Azure AD B2C

The portal supports a configurable security system that lets our customers support multiple authentication systems. Going forward, it is recommended that you use only Azure AD B2C identity provider for authentication and that you deprecate other identity providers.

You can configure your portal to mark other identity providers as deprecated and allow users to migrate to Azure AD B2C identity provider. If a specific provider, e.g. Twitter, is required to be supported, it can still be supported by Azure AD B2C, instead of the portal.

The steps involved in migration:

* Mark other identity providers as deprecated
* Migrate deprecated identity providers to Azure AD B2C
* Disable local login

Following these steps will ensure uninterrupted authentication experience for the users. See [Migrate identity providers to Azure AD B2C](https://docs.microsoft.com/powerapps/maker/portals/configure/migrate-identity-providers/?azure-portal=true) for the step-by-step instructions.
