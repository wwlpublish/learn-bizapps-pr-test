## Identify exceptions with Connected Field Service overview

One important function of a Connected Field Service application is to identify anomalies and escalate them into the application, where action can be taken. When you install the Connected Field Service add-on for Microsoft Dynamics 365 for Field Service, it includes a pre-built template application that uses a temperature-based scenario where a specific format of data comes from the IoT device. This template also uses static rules to detect anomalies. In this unit, you'll learn how to customize the template components to handle the unique requirements of your own scenario. For example, the customizations will let the template components handle different data that's sent from the device, change the rules that are used to evaluate the data, and generate Internet of Things (IoT) Alerts.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE2EbBx]

The following image shows the architecture of the default components that are installed with the Connected Field Service add-on. The telemetry from the device is evaluated by a Microsoft Azure Stream Analytics job for exceptions to the static rules.

![Default components](../media/1-ie-unit1.png)

When you install the Connected Field Service add-on, the simulator application generates the following device data that's consumed by the Stream Analytics job.

![Device data](../media/2-ie-unit1.png)

In the next unit, you'll connect a real device by using the Azure IoT DevKit that has the Microsoft IoT Central firmware installed. When that firmware is used, the device will generate the following data.

![Simulator device data](../media/3-ie-unit1.png)

A quick comparison will reveal some noticeable differences. First, all the data attributes under **JSON** are in lowercase letters. Additionally, the `Temperature` attribute is now named `temp`, and the temperature is reported in Celsius, not Fahrenheit. The real device also has more sensors and is set up to send more data. Although the extra data won't affect the current template components, they can also be enhanced to use that data.

The following image shows the default Stream Analytics query, so that you can see how the data is currently transformed.

![Default Stream Analytics query](../media/4-ie-unit1.png)

When the data is processed by the Stream Analytics job, and the IoT Alert is generated, some of the raw data and also some augmented data from the rule are entered as alert data on the IoT Alert record in the Microsoft Dynamics 365. You should start to see how we'll have to change this query to accommodate the differences between the simulated device and the real device.

![IoT Alert](../media/5-ie-unit1.png)

The Alert data properties can be evaluated as part of any automation that's run after the IoT Alert record is created. As you look at your unique scenario, consider what data you must promote from the device telemetry into the alert data.

In addition to looking at alerts, you might want to store detailed telemetry, so that you can drill down as part of the process of diagnosing an alert. The default template uses an Azure SQL database together with Microsoft Power BI to give you a real-time look at the activity from your devices. Later in this module, we'll look at different options for storing the detailed telemetry.

In the next unit, you'll set up your device. Later, you'll change the default template so that it picks up the new data format.
