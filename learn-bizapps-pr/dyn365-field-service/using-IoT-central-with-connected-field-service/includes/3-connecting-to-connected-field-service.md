Now that you have built an Azure IoT Central application let’s look at how we can connect that up with Connected Field Service.  To accomplish that we are going to use the Microsoft Flow connectors to register devices and raise alerts with Dynamics 365.  

Today, when you install the Connected Field Service add-in it installs several Azure components that aren’t required when working with IoT Central. This is because IoT Central includes similar components packaged as part of the overall service.  In the future it is on the roadmap to provide an install that does not include installing these redundant components.  The key components that you will be leveraging to complete the integration are the solutions that are installed on the Dynamics 365 side that include entities like IoT Alert and IoT Device.  If you were doing this for a real project you could also turn off some of the Azure components like IoT Hub, so you aren’t being billed for it.

Typically, with a Connected Field Service solution you would create the customer asset and then register the device.  You can accomplish the same task using Microsoft Flow by creating a selected record flow. This means either you select the customer asset from the list or run the flow from a specific customer asset record.  The flow will use the IoT Central connector to register the device with IoT Central (and also with the embedded IoT Hub instance).  The following is the flow you will build in the next unit to do the registration.

![the flow to register the device with IoT Central](../media/1-ic-unit3.png)

Notice that in addition to updating the customer asset with the Device ID, you will also be creating the IoT device record which is used if you send any commands or other actions from Dynamics 365.

Once you have the device registered you have created a connection between the device in IoT Central and the customer asset in Dynamics 365 for Field Service.  To continue our scenario of a smart trash container, in the prior module we set up an event to indicate the container was ready for pickup.  Now let’s look at how we can raise an alert into Dynamics 365 so it could be scheduled for pickup.

To start the process, we are going to use the rules feature of IoT Central.  Rules are built to monitor telemetry of the device and perform an action when a condition is met.  In addition to looking at the real time values, rules can also look at device properties.  For example, the properties might include threshold information that varies by device based on the installation.  The following is an example of the rule you will build to react to the ready for pickup event.  Notice there are several options for actions when a rule's conditions are met.  In fact, out of the box Dynamics 365 actions are coming soon.  For now, we will be using the Microsoft Flow action to create an IoT Alert record.

![the rule to react to the ready for pickup eventl](../media/2-ic-unit3.png)


To create the flow, you will again be using the IoT Central flow connector that allows building a flow that is triggered by a specific rule in IoT Central.  The flow itself is quite simple, it matches the customer asset using the device ID that triggered the flow.  Then an IoT Alert record is created for each of the matching assets.

![a flow that is triggered by a specific rule in IoT Central](../media/3-ic-unit3.png)

With the IoT Alert created, it can then flow into the normal business process capabilities of Dynamics 365 for Field Service, including scheduling a visit to the location.  In the next unit, you will be adding device registration and raising of alerts to your IoT Central application you built in Unit 2.