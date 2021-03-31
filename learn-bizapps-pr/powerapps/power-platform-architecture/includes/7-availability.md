A solution architect needs to consider how to include high availability in the solution design. Microsoft handles high availability and disaster recovery for the Power Platform and its components. The solution architect needs to focus on non-Power Platform components, custom code, and integrations.

## Principles of High Availability

When creating a solution, the solution architect should follow these principles:

- There should be no single points of failure.
- Use the capabilities of Microsoft Azure whenever possible.
- Use monitoring and health checks to predict and detect problems.

Microsoft deploys a Power Platform environment within an Azure region. Within a region, services and data are replicated redundantly across the datacenter(s) to increase availability. Each Azure region has a paired region where Power Platform resources are replicated automatically. Microsoft monitors the Power Platform on your behalf as part of the service.

![Diagram of Azure availability locations.](../media/7-azure-availability.png)

## Handling failover

The Power Platform components handle internal integrations, solution architects should focus on external integrations and custom code.

If there is an issue with the primary datacenter, Microsoft will initiate the failover automatically, if necessary, from the primary location to the regional pair. Microsoft also handles any service recovery required.

Users should not notice any interruption in service. At worst, they will have transient error when saving data. Model-driven apps for instance will handle such errors themselves.

For custom code, however, there could be issues. For example, the endpoint for the environment may change. Integrations, should use the global discovery service for endpoint discovery to get the latest environment endpoint. Custom code should have transient error handling with automatic retries.
