Outbound data integration is concerned with taking data from Microsoft Dataverse and making it available to other systems.

## Dataverse Event publishing

Dataverse provides an event model for integrating with other systems. Dataverse supports triggering of custom code and external actions when events are detected in the platform. This is known as the Event Framework. The Event Framework provides the capability to register custom code to be run in response to specific events. The Event Framework is typically used to trigger custom plug-in code but can also be used for integrations with other systems.

To leverage the Event Framework for your solution, you must understand:

- What events are available
- How the event is processed
- What kind of data is available when the event occurs
- What time and resource constraints apply
- How to monitor performance

You can specify different stage

- PreValidation: For the initial operation, this stage will occur before the main system operation. This provides an opportunity to include logic to cancel the operation before the database transaction. This stage occurs before any security checks are performed to verify that the calling or logged-on user has the correct permission to perform the intended operation.
- PreOperation: Occurs before the main system operation and within the database transaction. If you want to change any values for an entity included in the message, you should do it here.
- MainOperation: For internal use only except for Custom API and Custom virtual table data providers.
- PostOperation: Occurs after the main system operation and within the database transaction. Use this stage to modify any properties of the message before it is returned to the caller.

> [!NOTE]
> Integration typically use the PostOperation stage and the asynchronous execution mode.

The event framework can trigger:

- Plug-ins
- Classic workflows
- Power Automate cloud flows
- Messages to Azure Service Bus and Azure Event Hub
- WebHooks

## Event vs Batch

The solution architect should categorize the data that is required in Dataverse. A key category is event or batch based. The following diagram compares these two approaches.

![Diagram of outbound integration approaches.](../media/4-outbound.png)

## Push pattern

Event-based processing is associated with the push pattern. An event in Dataverse runs a process that connects to the external system and updates the data in that system. When linking directly to another system, the solution architect needs to ensure that they are creating performance issues for both systems and are not creating a tightly coupled system.

> [!IMPORTANT]
> If using plug-ins, the solution architect needs to be aware of the 2-minute time limit for plug-in processing.

## Pull pattern

The pull pattern uses external events from the other system or a scheduled trigger to retrieve a set of data from Dataverse and process the set of data returned.

> [!NOTE]
> The Recurrence trigger in Power Automate is often used in the pull pattern.

## Change Tracking

The change tracking feature in Dataverse provides a way to keep the data synchronized in an efficient manner by detecting what data has changed since the data last synchronized. Without change tracking, it is difficult to build a reliable and efficient mechanism to determine what rows have changed in Dataverse.

When retrieving data with change tracking, a set of delta changes is returned by Dataverse.

> [!NOTE]
> Change tracking must be enabled on the table.

## Azure integration

The Dataverse platform supports outbound integration with Azure. Dataverse can send messages to Azure services using the Event Framework as shown in the following diagram.

![Diagram of integrations with Azure.](../media/4-azure-integrations.png)

## Service Bus

One of these services that Dataverse can integrate with is the Azure Service Bus.

The Azure Service Bus is used to decouple applications and services from each other, providing the following benefits:

- Load-balancing work across competing workers.
- Safely routing and transferring data and control across service and application boundaries.
- Coordinating transactional work that requires a high-degree of reliability.

The Azure Service Bus can provide a secure and reliable communication channel between Dataverse runtime data and external cloud-based or on-premises line-of-business (LOB) applications as shown in the following diagram.

![Diagram of integration with Azure Service Bus.](../media/4-azure-sb.png)

In this image, an Azure Service Bus resource has been created in Azure. A listener process has been developed that waits for messages to be posted onto an Azure Service Bus. In Dataverse, the Azure Service Bus endpoint has been registered using the Plugin Registration Tool, and a step defined that posts the plug-in context to the Service Bus as a message when an event occurs such as a row being created in Dataverse.

The listener process will automatically be able to read the message and extract the details of the event from the context (which table, ID of the row, user who triggered the event, the list of data changes, etc.) and perform the appropriate processing on this data.

The listener process can be:

- a C# program running on an on-premise system that polls the Service Bus for new messages.
- an Azure Logic App that is triggered automatically when a new message is posted.
- An Azure Function that is triggered automatically when a new message is posted.

The integration with Azure Service Bus is useful when there is the likelihood that the other system is not available or is limited in its ability to process high volumes of messages as the messages can be queued, allowing the receiving system to process the messages as fast as they can,.

You can post a message to the Service Bus in one of two ways:

- No code: Create a step for the event in Dataverse against the Azure Service Bus endpoint. The plug-in execution context is posted to the Service Bus.
- Code: Create and register a plug-in in Dataverse that calls the Azure Service Bus endpoint. The message posted to the Service Bus can be customized.

Azure Service Bus can be used to:

- Build reliable and elastic cloud apps with messaging
- Protect your application from temporary peaks
- Distribute messages to multiple independent backend systems
- Decouple your applications from each other
- Ordered messaging scaled out to multiple readers

## Relay

Azure Relay is a service that used to be part of Azure Service Bus but has been separated into its own service.

The Azure Relay service facilitates tight integration between systems by helping you more securely expose services that reside within a corporate enterprise network to the public cloud. You can expose the services without opening a firewall connection, and without requiring intrusive changes to a corporate network infrastructure.

Azure Relay supports the following scenarios between on-premises services and applications running in the cloud or in another on-premises environment.

- Traditional one-way, request/response, and peer-to-peer communication
- Event distribution at internet-scope to enable publish/subscribe scenarios
- Bi-directional and unbuffered socket communication across network boundaries

> [!IMPORTANT]
> Azure Relay allows two systems to be connected without needing a direct connection. Azure Relay follows a request/response pattern so that the calling system can receive a response such as a piece of data or a success message from the other system.

## Event Hub

Azure Event Hub is a big data streaming platform and event ingestion service. It can receive and process millions of events per second. Data sent to an event hub can be transformed and stored by using any real-time analytics provider or batching/storage adapters.

Multiple other systems can subscribe to events processed by the Event Hub. The Event Hub can filter events using Consumer Groups so that systems only receive the events that are relevant to them at their own pace.

![Diagram of Azure Event Hub.](../media/4-event-hub.png)

> [!NOTE]
> Topics in the Azure Service Bus service provide a similar method for systems to subscribe to filtered messages.

You should consider using the Azure Event Hub if you require multiple subscribers.

An example of using Event Hub is to publish events to stream analytics that in turn populates a Power BI dataset for visualization.

## Webhooks and Azure Functions

Dataverse supports the calling of a Webhook with the Event Framework. Webhooks are registered with the Plugin Registration Tool and can be triggered by a specified event in a step.

Webhooks is a lightweight HTTP pattern for connecting Web APIs and services with a publish/subscribe model. Webhook senders notify receivers about events by making requests to receiver endpoints with some information about the events. Webhooks are simply a pattern that can be applied using a wide range of technologies. There are no required frameworks, platforms, or programming languages you must use.

Webhooks enable developers to integrate Dataverse data with their own custom code hosted on external services. By using the WebHook model, you can secure your endpoint by using authentication header or query string parameter keys. This is simpler than the SAS authentication model used by Azure Service Bus integration.

Azure Functions provides an excellent way to deliver a solution using WebHooks.

When deciding between the WebHook model and the Azure Service Bus integration, here are some items to keep in mind:

- Azure Service Bus works for high scale processing, and provides a full queueing mechanism if Dataverse is pushing many events.
- Webhooks can only scale to the point at which your hosted web service can handle the messages.
- Webhooks enables synchronous and asynchronous steps. Azure Service Bus only allows for asynchronous steps.
- Webhooks send POST requests with JSON payload and can be consumed by any programming language or web application hosted anywhere.
- Both WebHooks and Azure Service Bus can be invoked from a plug-in or custom workflow activity.

## Process Integration: Power Automate vs Logic Apps

Power Automate cloud flows are based on Azure Logic apps and can generally both can meet the same requirements. However, there are some differences. As a solution architect you should consider when to use Power Automate cloud flows or Logic Apps:

Power Automate:

- Dataverse Connector has more capability.
- Be packaged as part of a solution.
- Can perform RPA with desktop flows.
- Use Approvals connector.
- Send Notifications connector.
- Have a limit on the number of flow runs per month.

Logic Apps:

- Perform Enterprise Integration including EDI.
- Have higher performance.
- Can be more easily monitored using Azure tools.
- Have better error handling.
- Cannot be packaged in solutions.
- Consumption-based or fixed pricing model via an Azure subscription.
