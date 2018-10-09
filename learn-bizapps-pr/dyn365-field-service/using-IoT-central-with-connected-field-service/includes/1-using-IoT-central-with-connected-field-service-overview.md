## Using Microsoft IoT Central with Connected Field Service overview

Microsoft IoT Central is a software as a service (SaaS) solution that abstracts many of the low-level components of an Internet of Things (IoT) solution into a customizable model-based approach. The solution is set up in Microsoft IoT Central, at a similar level of abstraction to what's done in Microsoft Dynamics 365 applications. Currently, you can use Microsoft IoT Central with Connected Field Service by implementing some of your own flows. The upcoming release of Dynamics 365 will include a directly supported action from the rules that you build in Microsoft IoT Central.

The following illustration highlights the division of work between Microsoft IoT Central, Connected Field Service, and the core features of the Microsoft Dynamics 365 for Field Service application.

![Enhanced Microsoft IoT Central integration](../media/1-ic-unit1.png)

A key difference in a Microsoft IoT Central deployment is that, although the components of Microsoft Azure IoT Hub are present, they aren't available for direct extension. All customizations are done via the Microsoft IoT Central abstractions. You'll use the Microsoft IoT Central portal to define and interact with the solution that you build.

To build a solution, you create a Microsoft IoT Central application. To make it easy for you to try out this process, a sample application is available. Alternatively, you can create a custom application where you define all the device characteristics. In the exercises in this module, you'll create a custom application for a smart trash container and connect it to Dynamics 365.

When you create an application, the device template defines the behavior and capabilities of the devices. For example, the device template for our smart trash container might include the state of the lid (open or closed) and other telemetry that's related to the device.

The following illustration shows the key components of a device template

![Template architecture](../media/2-ic-unit1.png)

The following table gives more details about each key template component.

<table>
<thead>
<th>Component</th>
<th>Description</th>
</thead>
<tbody>
<tr>
<td>Measurements</td>
<td>Measurements can be telemetry, which is time series data from the device. Examples include a state (for example, the lid is open) or an event (for example, the customer presses a button to request trash pickup). Time series data is stored for use by the analytics service. In this case, the analytics service is Azure Time Series Insights.</td>
</tr>
<tr>
<td>Properties</td>
<td>Properties are device metadata. Examples include the pickup location for the container, the customer account number, or any other static metadata.</td>
</tr>
<tr>
<td>Settings</td>
<td>Settings control the behavior of the device. For example, if the container has an odor control feature, a setting can control how active the feature is (high, medium, or low).</td>
</tr>
<tr>
<td>Commands</td>
<td>Commands let remote commands be sent to the device. When Connected Field Service is used, the command can be extended into the Dynamics 365 user interface. For example, a command can be sent to force the lid to close if it was left open.</td>
</tr>
<tr>
<td>Dashboards</td>
<td>Dashboards include tiles that have information about the device. Dashboards can include settings, properties, and even maps. For example, you can include a map that shows the location of the device. Such a map might be useful after a severe weather event that caused trash containers to be blown all over the place.</td>
</tr>
<tr>
<td>Rules</td>
<td>Rules let you monitor the measurements from the device and trigger actions. In our case, rules will let us use Microsoft Flow to generate a Connected Field Service IoT Alert.</td>
</tr>
</tbody>
</table>

After your template is set up, you can create simulated devices or connect a real device. In the next unit, you'll build the custom application to manage a smart trash container and then connect it to Dynamics 365 by using the Microsoft Flow IoT Central connector.
