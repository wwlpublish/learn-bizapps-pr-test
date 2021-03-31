Microsoft has a worldwide network of datacenters, that support the Power Platform, set up around the world in 17 different locations. This level of localization helps organizations more easily meet data residency, sovereignty, and compliance requirements.

When creating an environment, you cans specify the geographical location for the environment. The data for the environment will be held in the chosen geographical location.

> [!NOTE]
> An environment can be relocated after it has been created, but it is easier to select the correct region to begin with.

## Regions

Microsoft offers the option of choosing global, local, and sovereign clouds:

- Global cloud: A public internet cloud deployment option that lets customers access globally connected cloud services deployed from regional Microsoft datacenters. The global clouds are United States, Europe, and Asia Pacific.
- Local cloud: A cloud option that addresses local data residency requirements by letting all public cloud users within a country keep their data in the country. The local clouds are: Canada, Brazil, United Kingdom, France, Germany, India, Japan, Australia, United Arab Emirates, Switzerland, Republic of South Africa.
- Sovereign cloud: A cloud option that adheres to the strictest standards of operation.Data remains inside the country of residence at all times. Sovereign clouds are: US Government, China.

> [!NOTE]
> New locations are planned so the list above may not be complete. Check <https://docs.microsoft.com/power-platform/availability> for the latest information.

The following diagram shows the locations support for the Power Platform.
![Diagram representing supported Power Platform locations.](../media/3-location.png)

## Data residency

There are several aspects that influence the choice of location for environments and data:

- Are the user geographically dispersed?
- What latency is acceptable?
- Does the organization have separate autonomous business units where data must not be shared?
- Are the required features available in the region?
- Are the security requirements to bbe considered?
- Are there specific data & compliance requirements?

If there are no other factors, you should select a location close to the majority of users that need to share data.

> [!NOTE]
> The location of the tenant (billing) can be different from location of an environment and its data.

## Compliance and Data Protection

The solution architect must consider regulatory and compliance requirements such as GDPR when deciding on a location for the environment and data.

Microsoft will not transfer customer data outside the selected Azure geographic location (geo) except when it is necessary for Microsoft to provide customer support, troubleshoot the service, or comply with legal requirements.

The Power Platform stores information that is global in nature, such as user identities and profile information, in a datacenter located in the United States. All Power Platform customer data, as well as the geo-redundant mirrors, is maintained within the selected geo.

## When to use multiple environments

In the last module we saw how the Power Platform uses environments to separate development from production and to separate different user groups. When you further consider the location of users in a global organization there are other reasons to create multiple environments:

- To handle application lifecycle management (ALM) – Dev / Test / Prod.
- To isolate resources that are not used by same users or share data.
- To allow conflicting customizations between different regions or markets, or for compliance with legal and regulatory constraints.
- To keep environments close to users that don’t share data.
- To isolate data that cannot be co-located.
- To provide places for makers to experiment.

Let us now look at working with data.
