Connected Field Service is an add-on solution to Microsoft Dynamics 365 for Field Service that connects IoT (Internet of Things) telemetry to business actions. Therefore, in many cases, businesses can become proactive instead of reactive, transforming the business model of how they work with their customers.

**NEED CORRECT VIDEO LINK**
[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2rlss]

In this module, we look at how Connected Field Service works with Microsoft Azure IoT capabilities to implement a complete IoT solution.

In basic terms, a complete IoT solution covers three key areas, as shown in the following diagram.

![IoT key areas: things, insights, actions](../media/1-gs-unit1.png)

Given all the hype about IoT, it's easy to focus on the low-level details of ingesting telemetry. But it's important not to forget about handling issues that are detected and getting a technician on site to fix them.

Connected Field Service is an important part of the "Actions Based on Insights" area. When an IoT device is connected to a customer as a customer asset, work orders can be created, and a technician can be dispatched. Therefore, issues can be detected and diagnosed before the customer is even aware of them. Fixing an issue can include proactively scheduling an on-site visit or just sending an automated reset command to the device. When technicians do on-site visits, they have a Field Service mobile application that has the customer details connected to the work order. The scheduling capabilities in Field Service are used to schedule technicians' visits and optimize their routes.

The following diagram is from the Microsoft Azure IoT Reference Architecture. It highlights Business Integration, which is where Connected Field Service fits into the reference architecture.

![Core subsystem of key areas](../media/2-gs-unit1.png)

As part of the process of building an overall Connected Field Service solution, you might also be involved in generating insights. For example, you might change the stream processing to detect an anomaly in the telemetry. Consider a scenario where you're monitoring a temperature-controlled room. It's easy to detect that the temperature in the room is suddenly too high. But there's more business value if you can detect and generate the insight as the temperature is slowly rising over a period of eight hours. You can then have a technician dispatched before the temperature reaches the point where it becomes a crisis for the customer.

When you install the Connected Field Service add-on (which you'll do in a later unit), two solutions are installed in your environment. These solutions build on the Field Service application, and they include the following entities that are a key subset of entities that support the integration with Azure IoT. These are the entities that you'll work with when you do customizations.

<table>
    <thead>
        <tr>
            <th>Entity name</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>IoT Alert</td>
            <td>An event that's sent because of a notable event from the Azure IoT Hub telemetry</td>
        </tr>
        <tr>
            <td>IoT Device</td>
            <td>A connected device that can be registered with IoT Hub</td>
        </tr>
        <tr>
            <td>IoT Device Category</td>
            <td>A grouping of devices</td>
        </tr>
        <tr>
            <td>IoT Device Command</td>
            <td>An outgoing message to a device that's connected to IoT Hub</td>
        </tr>
        <tr>
            <td>IoT Device Registration History</td>
            <td>An entity that tracks the history of device registration activities</td>
        </tr>
    </tbody>
</table>

The solution also installs several workflows and actions that can be used to automate work as you customize your Connected Field Service solution. Additionally, it installs a template solution for detecting anomalies and raising alerts in Field Service.

In the next unit, we'll look at the deployment options and discuss how you can choose what's appropriate for your solution.
