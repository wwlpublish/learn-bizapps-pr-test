Now that you have officially started to collect data, detect anomalies, and extract the relevant data form our IoT Devices, the final step is to decide what to do with it and provide guidance for uses as then work with these devices.  Before you start to define processes, it is important to understand what the desired outcome is that you are trying to achieve and determine what is needed to get to that Point.  

The example below shows an example of a Business Process Flow that branches based on the reading value provided on a temperature alert.  

![Sample Branching Business Process Flow](../media/1-rm-unit5.png)   

The Business process flow is associated with the IoT Alert entity and leverages the value in the Device Reading field.  

**Based on this value, we can:**

- *Send a reset command directly to the device if the temp reading is between 70 and 85 degrees.*
- *Branch into our standard resolution process that first creates the case - then generates a Work Order - Dispatches the Work Order - Finally has the technician servicing the Work Order when the temp reading is between 86 and 100 Degrees.*
- *Skip the case stages completely and go directly to the Work Order creation stage if the temp reading is above 100 Degrees.* 

By leveraging Workflow automation in conjunction with Business Process Flows, this concept could be taken one step further, and instead It could execute a different business process flows based on the alert.   
   
For example:  Let’s say that you have created the following Business Process Flows for the IoT Alert Entity.
  
- Temperature Alert Process Flow
- Humidity Alert Process Flow
- Compressor Alert Process Flow

When an alert is generated, we could execute a workflow that uses the JSON-Based Field Value - Get String action to capture the “readingtype” property from the JSON passed into the Alert Data field.  The Workflow could then populate a custom field called “Reading Type” on the alert record.  

Since we have the ability to interact with Business Process Flows using workflow, it would be possible to design a work flow that would execute the appropriate Business Process Flow based on the value in the Reading Type field.

![Using Workflow to Trigger Process Flows](../media/2-rm-unit5.png)   

Additionally, you can execute Workflows when you enter or exit a specific stage of a Business Process Flow.  This could be handy when you are thinking about sending commands or device registration based on items that you have captured in record you are working with.  Out of the box, Connected Field Service ships with the following Actions. 

| **Display Name** | **Description** |
| :-------------- | :--- |
| **IoT- Register Customer Entity** | Registers any custom entity that may or may not already have connected IoT devices. This action invokes the IoT – register device action. |
| **IoT- Register Device** | Publishes the registration for an IoT device. |
| **IoT – Debounce IoT Alerts** | Links potential redundant alerts to an existing parent alert.  |


By creating workflows that call those actions, you could then associate those workflows with either the entry or exit of a specific stage in your Business Process Flow.  For example: You might have a Business Process Flow that is associated with a Custom Entity that is also going to be leveraged as an IoT Device.  By creating a workflow that calls the IoT-Register Customer Entity action and setting it to run on exit of a specific stage, you could then evaluate specific items on the record and have the BFP register the device automatically if specific conditions are met.  

Regardless of how you plan to automate and guide users through specific processes, it is important to remember that each process you design should:

- Have a specific beginning. *(Example: Alert Being Triggered)*
- Have a specific end. *(Example: A Work order being closed)*
- A repeatable procedure with specific stages and steps. *(Example: Alert – Case – Work Order -Service Delivery)*
- Take into consideration variables that might affect the Process Flow. *(Example: an Outage, vs a Warning)*

  