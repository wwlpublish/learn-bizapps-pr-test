Register and Manage Customer Devices with Connected Field Service Overview

##Device Registration and Digital Twins##

When you begin to work with the Connected Field Service solution, you will find that there are two critical aspects that drive how effective the solution is when working with and administrating IoT devices.  These aspects are: 

- Effectively registering IoT devices with either an Azure IoT Hub or IoT Central.  
- Effectively managing IoT devices and streamlining how you interact with them.   

In this module, we will examine both of these items in much more detail.  However, before we do that let’s take a quick high-level look as them.   
 
**IoT Device Registration:**  
When you want to track a specific piece of customer equipment at a customer location in Field Service, you create a Customer Asset record.  Since many Customer Assets will often be IoT enabled devices, customer assets can also be registered as IoT devices.  The IoT device entity plays a critical role in the Connected Field Service solution, because the IoT device entity is what is used to connect IoT devices with either an Azure IoT Hub or IoT Central.   IoT devices could represent a physical device or a non-physical device in the application.   
 
**Device Management and Interaction** 
Once your devices have been registered as IoT devices, readings from those devices will be captured and communicated back to the Azure IoT Hub or IoT Central.  When a device raises an exception, it will be sent back into Dynamics 365 as an alert.  For example, let’s say that you have a smart thermostat.  The smart thermostat will constantly send temperature readings to Azure IoT Hub or IoT Central.   As soon as a temperature reading that is outside of your specified threshold is discovered, it will generate an IoT alert record in Dynamics 365.  

Many times, the first step in dealing with an IoT alert is to remotely interact with the device and send specific commands to the device.  The Connected Field Service solution contains several record types that can be leveraged to assist in remotely managing and interacting with these devices.   

Let’s examine some of the key record types that Connected Field Service uses for device management and interaction.   

**Device Category:** Device categories are used to group together multiple devices by the type of device it is.  Device categories can be leveraged for reporting purposes, management, and to simplify device interactions. 
 
- **For Example:**  You might create temperature and humidity categories to separate out temperature related IoT devices or commands from IoT devices or commands that are more humidity focused.      
 
**Command:** A command record is the actual action or command that you want to execute against a specific IoT device.  They typically consist of different JSON properties that are passed to the device to do that does something to the device. 
 
- **For Example:**  If you wanted to set the temperature and humidity of a device to specific values, you would pass the following JSON script to the device using a command record. 
{"CommandName":"Set Values","Parameters":{"Reading":{"Temperature":"60","Humidity":"40"}}} 
 
**Command Definition:** A command definition represents a predefined command that can be added directly to a command record.  The definition contains multiple pre-configured properties that can then be modified to help streamline the process of sending to devices.  When creating a command, a command definition can be selected.  Any properties in the definition will be populated with default values, but those values can be over ridden. 
 
- **For Example:**  You could create a command definition called set values.  In the command definition you could pre-define the parameters; such as reading, temperature, and humidity.  When the command definition is selected, it will auto-populate the command, and you can manually change any parameters needed.   
 
**Property Definition:** A property definition is used to define what specific properties are available and that can be passed as part of a command definition. 
 
- **For Example:** If you created the set values command definition as defined above each parameter such as reading, temperature, and humidity would have a property definition defined for them that was associated with the set values command definition.    
 
In future units, we will examine each of these element is much more detail.  