The platform does not provide an infinite amount of resources and there are limits in the number of API calls that can be made.

A solution architect needs to ensure that the solution does not exceed the limits imposed by the platform by designing appropriately and ensuring custom code can handle when limits are breached.

## What is an API Request?

Requests in the Power Platform consist of various actions that a user makes across various products. At a high level, below is what constitute an API request:

- Power Apps: all API requests to connectors and Microsoft Dataverse.
- Power Automate: all API requests to connectors, HTTP actions, and built-in actions from initializing variables to a simple compose action. Both succeeded and failed actions count towards these limits. Additionally, retries and other requests from pagination count as action executions as well. As a basic rule each step in a Power Automate cloud flow is an API request.
- Dataverse: all create, read, update, and delete (CRUD), assign, and share operations including user-driven and internal system requests required to complete CRUD transactions, as well as special operations like share or assign. These can be from any client or application and using any endpoint. These include, but are not limited to, plug-ins, classic workflows, and custom controls making the earlier-mentioned operations.

## Entitlement limits

These limits represent the number of API requests users are entitled to make each day. The allocated limit depends on the type of license assigned to each user. API entitlement limits are based on a 24-hour period as shown in the following table.

| User license                   | Number of API requests / 24 hours |
| ------------------------------ | --------------------------------- |
| Dynamics 365 Enterprise apps   | 20,000                            |
| Dynamics 365 Professional apps | 10,000                            |
| Dynamics 365 Team member       | 5,000                             |
| Power Apps per user plan       | 5,000                             |
| Power Automate per user plan   | 5,000                             |
| Office 365 license             | 2,000                             |
| Power Apps per app plan        | 1,000 per app pass                |

If a user has multiple plans assigned from different product lines, the total number of requests allowed would be the sum of requests allocated to each license type. For example, if a user has both a Dynamics 365 Customer Service Enterprise license as well as Office 365 E3 user license then that user will have a total of 20,000 + 2,000 = 22,000 requests available per 24 hours.

Dataverse provides the ability to have identities that do not require any user license to interact with the service. There are four types of these users:

- Application users
- Non-interactive users
- Administrative users
- SYSTEM user

Each tenant has a base request capacity per tenant that can only be used by these users and not by users with standard licenses. This base request capacity is based on the type of subscription, as follows:

- If a tenant has at least one Dynamics 365 enterprise subscription, they will get 100,000 requests per 24 hours.
- If a tenant has at least one Dynamics 365 professional subscription, they will get 50,000 requests per 24 hours.
- If a tenant has at least one Microsoft Power Apps or Power Automate subscription, they will get 25,000 requests per 24 hours.

Power Apps and Power Automate capacity add-on allows customers to increase the limits for a given user. Each capacity add-on raises the request limits by an other 10,000 per 24 hours.

> [!NOTE]
> For more information, see <https://docs.microsoft.com/power-platform/admin/api-request-limits-allocations>

## Service Limits

Apart from the daily API request limit, there are service protection limits specific to each service. As with the daily limits, these limits help maintain the quality of service by protecting the service from malicious or noisy behavior that would otherwise disrupt service for all customers.

Service protection API limits help ensure that users running applications cannot interfere with each other based on resource constraints. The limits will not affect normal users of the platform. Only applications that perform a large number of API requests may be affected. The limits provide a level of protection from random and unexpected surges in request volumes that threaten the availability and performance characteristics of the Dataverse platform.

Microsoft limits the number of concurrent connections per user account, the number of API requests per connection, and the amount of execution time that can be used for each connection. These are evaluated within a five-minute sliding window. When one of these limits is exceeded, an exception will be thrown by the platform.

> [!IMPORTANT]
> Service protection limits cannot be increased.

> [!NOTE]
> For more information, see <<https://docs.microsoft.com/powerapps/developer/common-data-service/api-limits> >

## Retry policies and patterns

Custom logic using the APIs should handle retries. When a service protection API limit error occurs, it will provide a value indicating the duration before any new requests from the user can be processed.

The Web API returns a 429 error if the limit is reached. The response will include a Retry-After with number of seconds. With the Organization Service, a TimeSpan value is returned in the OrganizationServiceFault.ErrorDetails collection with the key Retry-After.

> [!NOTE]
> Care should be taken to not make it worse by over retrying.

For more on service protection limits and what to do see <https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/api-limits>

## How to minimize API calls

The solution design must not depend on infinite capacity being available. For normal users of interactive apps, the limits have been set high enough that users should be affected.

Applications designed to load data into Dataverse or perform bulk updates must also be able to manage service protection API limit errors. These applications prioritize throughput so they can complete their work in the minimum amount of time. These applications must have a strategy to retry operations.

Portal applications typically send requests from anonymous users through a service principal account. Because the service protection API limits are based on a per user basis, portal applications can hit service protection API limits based on the amount of traffic the portal experiences.

Integrations should be optimized to minimize the number of API calls.

The solution architect must also consider high availability in the design of the solution.
