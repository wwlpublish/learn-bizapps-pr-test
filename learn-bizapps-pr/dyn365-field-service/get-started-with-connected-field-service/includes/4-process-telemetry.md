Now that you've finished deploying the Connected Field Service add-on, the next step is to learn how to register a device and integrate the Microsoft Dynamics 365 data with Microsoft Azure IoT Hub devices.

This is done by creating a customer asset record in Dynamics 365 and then triggering the registration process. The following diagram shows how the customer asset is at the center of integrating a connected device into the Microsoft Dynamics 365 for Field Service process.

![Customer asset relationship](../media/1-gs-unit4.png)

When you define a customer asset, you can handle different scenarios, including assets that have multiple parts. You can wire these up by using connections to establish the relationship to the customer asset. Customer assets can also be categorized, making management easier and letting commands be sent in bulk.

After you create the customer asset and select the **Register** button, a message is sent to an Azure Service Bus queue to request registration with the associated IoT hub. This triggers a logic app that's provided as part of the Connected Field Service template that's deployed. The logic app communicates with the IoT hub, registers the device, and then returns to Dynamics 365 to update the registration status.

![Logic app](../media/2-gs-unit4.png)

After the device is registered, telemetry can be ingested and evaluated for anomalies. The Connected Field Service template application does this using an Azure Stream Analytics job that processes the raw telemetry. This job evaluates the incoming data for temperatures that exceed the reference temperature. Remember that these are just the starting rules in the template. You can customize them to include any detection logic that's appropriate for your scenario. For some scenarios, you might even find that these rules serve as a good example that inspires you to create your own stream jobs and associated logic apps. They can even be replaced by a micro service that does the heavy lifting, as you see in some of the Azure Internet of Things (IoT) solution accelerators.

The following diagram shows the overall flow of telemetry as it's evaluated and turned into an IoT Alert in Dynamics 365. When the temperature is exceeded, a message is queued in the Service Bus alert queue. This message is then picked up by a logic app that creates the actual IoT Alert record in Dynamics 365.

![Logic app queue](../media/3-gs-unit4.png)

After the IoT Alert is received in Dynamics 365, it can be evaluated. It can be put into a queue for human review, or an automated corrective command can first be sent to the device. Commands that are sent to a device can perform actions like doing a reset, sending a notification, or running any other custom command that the device expects to receive. Device settings can also be adjusted to accommodate changing environments at the remote device. From there, a custom business process can be established to do triage and dispatch a technician as needed. The technician will be matched and allocated by using the standard Field Service scheduling board.

![Scheduling flow](../media/4-gs-unit4.png)

In the next unit, you'll register a simulated device and interact with the simulator to see an alert generated and sent to Dynamics 365.
