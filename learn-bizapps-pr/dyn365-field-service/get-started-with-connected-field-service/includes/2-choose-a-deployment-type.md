An important part of architecting your Connected Field Service solution is choosing the underlying deployment approach. There are currently three primary approaches to choose from. All three use Microsoft Azure IoT Hub for secure bidirectional communication with connected Internet of Things (IoT) devices.

- **Connected Field Service Template** – This is the default setup when you install Connected Field Service. It includes a template application that's based on a generic temperature scenario. The default deployment creates an IoT hub and automation, using Azure Logic Apps to register devices and raise alerts in Microsoft Dynamics 365 for Field Service. Azure Stream Analytics is used for anomaly detection. The components can be customized and tailored to suit your scenario.
- **Azure IoT Solution Accelerators** – These are a collection of ready-to-deploy IoT solutions for common scenarios like remote monitoring and predictive maintenance. The source code for the solutions is open source and is on GitHub. You can customize the accelerators to meet your requirements. Currently, none of these accelerators work directly with the Connected Field Service components. But through customizations, you can adapt them so that they communicate with Field Service like the Connected Field Service Template application does.
- **Microsoft IoT Central** – This is a software as a service (SaaS) solution that abstracts many of the low-level components of an IoT solution into a customizable model-based approach. The solution is set up in Microsoft IoT Central, at a similar level of abstraction to what's done in Microsoft Dynamics 365 applications. Currently, you can use Microsoft IoT Central with Connected Field Service by implementing some of your own flows. The upcoming release of Dynamics 365 will include a directly supported action from the rules that you build in Microsoft IoT Central. 

The following table compares these three approaches to help you understand the trade-offs. Because the Connected Field Service Template and Azure IoT Solution Accelerators approaches share many of the characteristics that we're comparing, they're included in the same column.

<table>
    <thead>
        <tr>
            <th>Characteristic</th>
            <th>Microsoft IoT Central</th>
            <th>Connected Field Service Template/Azure IoT Solution Accelerators</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>Primary usage</td>
            <td>To accelerate the time to market for straightforward IoT solutions that don't require deep service customization</td>
            <td>To accelerate development of custom IoT solutions that need maximum flexibility</td>
        </tr>
        <tr>
            <td>Access to underlying platform as a service (PaaS) services</td>
            <td>SaaS. The solution is fully managed. The underlying services aren't exposed.</td>
            <td>You can access the underlying Azure services to manage them or replace them as needed.</td>
        </tr>
        <tr>
            <td>Skill level</td>
            <td>Similar to Dynamics 365 customization</td>
            <td>Developer skills are required to customize many of the components that generate insights.</td>
        </tr>
        <tr>
            <td>Pricing</td>
            <td>Simple, predictable pricing structure</td>
            <td>Can be fine-tuned at the component level to manage cost</td>
        </tr>
    </tbody>
</table>

The following diagram shows the components that are set up as part of the Connected Field Service Template application when you deploy the Connected Field Service add-on (which you'll do in the next unit).

![Connected Field Service components](../media/1-gs-unit2.png)

These components are set up to support a temperature-based scenario. When the temperature is outside the acceptable range, an IoT Alert is generated and sent to Field Service. As part of using this template, you'll likely customize the Logic Apps and Stream Analytics jobs to support your unique requirements. If you use it with an Azure IoT solution accelerator, you'll deploy the accelerator first and then connect to the existing IoT hub during deployment. If you use Microsoft IoT Central, you'll delete the Azure resource group, because the resource group is provided by Microsoft IoT Central. Soon, there will be a deployment option that's tailored to Microsoft IoT Central, so that you don't have to delete the Azure assets after deployment.

In the next unit, you'll deploy Connected Field Service by using the default template.
