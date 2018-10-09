## Exercise - Connect to a Device

 
### Exercise 1: Configuring Physical Device  

**Scenario **
In this exercise, you will be introduced to setting up the MXChip IoT DevKit. The MXChip IoT DevKit (a.k.a DevKit) is an all-in-one IoT Device Kit, you can use it to develop and prototype IoT solutions that take advantage of Microsoft Azure services.  

It includes an Arduino-compatible development board with rich peripherals and sensors, an open-source board package, and a growing projects catalog.  
To get started with purchasing an MXChip IoT DevKit, visit [http://aka.ms/iot-devkit/](http://aka.ms/iot-devkit/) and click on Get a Kit.  
 
After completing this exercise, you will be able to: 
- Install Firmware onto DevKit 
- Connect DevKit to Wi-Fi Network 
- Configure DevKit to Connect to IoT Hub 
 
  
#### Task 1: Create and Register the Device 
In this task, you will create a new customer asset and register it. 

1. Navigate to the Connected Field Service Hub. 
![Field Resource Hub](../media/1-ie-unit2.png)
2. On the left navigation select Customer Assets. 
![Customer Assets](../media/2-ie-unit2.png)
3. Click New. 
4. Enter MxChip IoT for Name, select Adventure Works for Account, enter MXChip for Device ID and click Save. 
![configure fields and save](../media/3-ie-unit2.png)
5. Click Register Devices. 
![Register Device](../media/4-ie-unit2.png)
6. Click OK. 
 
#### Task 2: Flash Firmware 

1. Download the latest pre-built Microsoft IoT Central firmware for the MXChip from the releases page on GitHub. The current direct link is [https://github.com/Azure/iot-central-firmware/releases](https://github.com/Azure/iot-central-firmware/releases) 
1. Select AZ3166-IoT-Central-x.x.x.bin. 
![Asset Selection](../media/5-ie-unit2.png)
3. Save the file locally. 
4. Connect the DevKit device to your development machine using a USB cable. 
5. In Windows, a file explorer window opens on a drive mapped to the storage on the DevKit device. For example, the drive might be called AZ3166 (E:).  
![Mapped drive location](../media/6-ie-unit2.png)
6. Drag the AZ3166-IoT-Central-X.X.X.bin file onto the drive window. 
![window dragging location](../media/7-ie-unit2.png)
7. When the copying is complete, the device will reboot with the new firmware. 
 
#### Task 3: Configure Wi-Fi 
 
After the device reboots, you need to configure the Wi-Fi on the Device.  
 
1. Hold down button B. While still holding button B push and release the reset button. Then release button B.  
![Board showing location](../media/8-ie-unit2.png)
2. Your DevKit enters AP mode for configuring Wi-Fi. The screen displays the service set identifier(SSID) of the DevKit and the configuration portal IP address: 
  
If your Wi-Fi SSID starts with AZ and not AZ3166 after applying the firmware, you need to follow the following steps to make sure the firmware gets applied correctly. 
 
	![Bad Message](../media/10-ie-unit2.png) 
	Bad – Firmware Not Applied Correctly 
	![Good message](../media/11-ie-unit2.png)
	Good – Firmware Applied Correctly 
 
		- Click Reset on the AZ3166 
		- Hold down A+B Button AZ3166 will hard reset 
		- Press Reset 
		- Remove from Power 
		- Place AZ3166 into AP Mode 
		- If the SSID is AZ3166_XXXXXX, the firmware is applied correctly.  
		- If the SSID still shows AZ-XXXXXXXXXX, please refer to:  [https://microsoft.github.io/azure-iot-developer-kit/docs/use-configuration-mode/](https://microsoft.github.io/azure-iot-developer-kit/docs/use-configuration-mode/)  and use SSH to update the IoT Hub Connection String. 

3. Go to your Azure portal, select All Resources and click to open the IoT Hub. 
![Azure IOT Hub](../media/12-ie-unit2.png)
4. Select IoT Devices and open the device you registered. 
![Device ID](../media/13-ie-unit2.png)
5. Copy the Connection String - Primary Key 
![Primary Key Copy Icon](../media/14-ie-unit2.png)
6. Use another Wi-Fi enabled device (computer or mobile phone) to connect to the DevKit SSID. Locate AZ3166 and click Connect. 
![Wi-Fi Connect](../media/15-ie-unit2.png)
7. Wait for the device to connect. 
8. In your browser paste http://192.168.0.1/start and <enter> 
9. Select the Wi-Fi Network you want to join and enter your Wi-Fi password.
![Wi-Fi Configuration](../media/16-ie-unit2.png)
10. Paste the connection string you copied. 
![Connection String Location](../media/17-ie-unit2.png)
11. Get the Pin Code from the device and enter in the Device Pin Code field. 
![Telemetry data to send](../media/18-ie-unit2.png)
12. Select all of the telemetry options and click Configure Device. 
![Configure Device](../media/19-ie-unit2.png)
13. You will be asked to reset the device.
![Device Configured Message](../media/20-ie-unit2.png) 
14. Press the Reset Button on the device. 
15. The device will reset and connect. Wait until you see messages getting sent to the IoT Hub. 
![Message Sent](../media/21-ie-unit2.png)
16. You have now configured your physical device to connect with Azure IoT Hub. 
 
### Exercise 2: Using Device Explorer    
 
#### Task 1: Download and Install Device Explorer 


1. Navigate to https://github.com/Azure/azure-iot-sdk-csharp/releases  
2. Scroll down to locate SetupDeviceExplorer.msi and click on it.
![Set up Device Explorer](../media/22-ie-unit2.png) 
3. Click Run. 
4. Click Next. 
![Setup Wizard](../media/23-ie-unit2.png)
5. Complete the installation and click Close. 
![Close Wizard](../media/24-ie-unit2.png)
 
#### Task 2: Connect 


1. Go to your Azure Portal and open the IoT Hub again. 
![IOT Hub](../media/25-ie-unit2.png)
2. Select Shared Access Policy and click on the iothubowner. 
![Shared Access](../media/26-ie-unit2.png)
3. Copy the Connection String - Primary Key. 
![Primary Key](../media/27-ie-unit2.png)
4. Start the Device Explorer you installed on your machine. 
5. Paste the Connection String and click Update. 
![Update](../media/28-ie-unit2.png)
6. Click OK. 
![OK Icon](../media/29-ie-unit2.png)
7. Select the Data tab and click Monitor.
![Data Tab](../media/30-ie-unit2.png) 
8. You should sensor data from your device in JSON format. 
![Event Hub Data Window](../media/31-ie-unit2.png)
