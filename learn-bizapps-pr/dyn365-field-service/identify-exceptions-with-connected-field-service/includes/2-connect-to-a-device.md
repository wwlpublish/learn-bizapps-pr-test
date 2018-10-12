### Exercise 1: Set up the physical device

**Scenario**

In this exercise, you'll learn how to up an MXChip IoT DevKit. The MXChip IoT DevKit (*the DevKit*) is an all-in-one IoT device kit. You can use this chip to develop and prototype IoT solutions that take advantage of Microsoft Azure services. It includes an Arduino-compatible development board with rich peripherals and sensors, an open-source board package, and a growing projects catalog.

If you don't have an MXChip IoT DevKit, you can go to <http://aka.ms/iot-devkit/> and select **Get a Kit**.

After you finish this exercise, you'll be able to do the following:

- Install firmware onto the DevKit.
- Connect the DevKit to a Wi-Fi network.
- Set up the DevKit to connect to Azure IoT Hub.

#### Task 1: Create and register the device
In this task, you'll create and register a new customer asset.

1. Go to the Connected Field Resource Service hub.

    ![Field Resource Hub](../media/1-ie-unit2.png)

2. In the left navigation, select **Customer Assets**.

    ![Customer Assets](../media/2-ie-unit2.png)

3. Select **New**.
4. In the **Name** field, enter *MxChip IoT*.
5. In the **Account** field, select *Adventure Works*.
6. In the **Device ID** field, enter *MXChip*.
7. Select **Save**.

    ![MxChip IoT customer asset](../media/3-ie-unit2.png)

8. Select **Register Devices**.

    ![Register Devices button](../media/4-ie-unit2.png)

9. Select **OK**.

#### Task 2: Flash the device firmware

1. On GitHub, download the latest pre-built Microsoft IoT Central firmware for the MXChip IoT DevKit from the releases page. The current direct link is [https://github.com/Azure/iot-central-firmware/releases](https://github.com/Azure/iot-central-firmware/releases).

2. Select **AZ3166-IoT-Central-x.x.x.bin**.

    ![Select AZ3166-IoT-Central-x.x.x.bin](../media/5-ie-unit2.png)

3. Save the file locally.
4. Connect the DevKit to your development computer by using a USB cable.

    In Microsoft Windows, a **File Explorer** window appears and is opened and shows a drive that's mapped to the storage on the DevKit. For example, the drive might be named *AZ3166 (E:)*.

    ![Mapped drive location](../media/6-ie-unit2.png)

5. Drag the **AZ3166-IoT-Central-X.X.X.bin** file onto the drive to copy (*flash*) it to that drive.

    ![Drag the file to the drive](../media/7-ie-unit2.png)

    After the file is copied, the device is restarted with the new firmware.

#### Task 3: Set up Wi-Fi

After the device is restarted, you must set up the Wi-Fi on it.

1. On the DevKit, press and hold down button B, press and release the Reset button, and then release button B.

    ![DevKit board](../media/8-ie-unit2.png)

    Your DevKit enters AP mode for setting up Wi-Fi. The screen shows the service set identifier (SSID) of the DevKit and the IP address of the configuration portal.

    After you apply the firmware, if the SSID starts with "AZ" instead of "AZ3166," the firmware wasn't applied correctly. Here are some examples.

    **Bad – The firmware wasn't applied correctly**

    ![SSID starts with AZ (Bad)](../media/10-ie-unit2.png)

    **Good – The firmware was applied correctly**

    ![SSID starts with AZ3166 (Good)](../media/11-ie-unit2.png)

    If the firmware wasn't applied correctly, you must follow these steps to make sure that it gets applied correctly.

    1. Press the Reset button on the device.
    2. Press and hold down buttons A and B. The device does a hard reset.
    3. Press the Reset button.
    4. Remove from Power.
    5. Put the device into AP mode.

	If the SSID starts with "AZ3166," the firmware was applied correctly. If the SSID still starts with "AZ," see [Use configuration mode](https://microsoft.github.io/azure-iot-developer-kit/docs/use-configuration-mode/), and use Secure Shell (SSH) to update the connection string of the Azure IoT hub.

2. Go to your Azure portal, select **All resources**, and then select the IoT hub to open it.

    ![IoT hub](../media/12-ie-unit2.png)

3. Select **IoT devices**, and then open the device that you registered.

    ![Registered IoT device](../media/13-ie-unit2.png)

4. Copy the value in the **Connection string – primary key** field.

    ![Copy button](../media/14-ie-unit2.png)

5. On another Wi-Fi-enabled device (like a computer or mobile phone), connect to the DevKit SSID. Find **AZ3166**, and then select **Connect**.

    ![Connect button](../media/15-ie-unit2.png)

6. Wait for the device to connect.
7. In your browser, enter `http://192.168.0.1/start` in the Address bar, and then press Enter.
8. Select the Wi-Fi network that you want to join, and enter your Wi-Fi password.

    ![Wi-Fi credentials](../media/16-ie-unit2.png)

9. In the **Device connection string** field, paste the connection string that you copied earlier.

    ![Device connection string](../media/17-ie-unit2.png)

10. Get the PIN code from the device, and enter it in the **Device Pin Code** field.

    ![Device Pin Code](../media/18-ie-unit2.png)

11. Select all the telemetry options, and then select **Configure Device**.

    ![Configure Device](../media/19-ie-unit2.png)

    You're prompted to reset the device.

    ![Prompt to reset the device](../media/20-ie-unit2.png)

12. Press the Reset button on the device. The device is reset and connects.
13. Wait until you see that messages are being sent to the IoT hub.

    ![Messages sent](../media/21-ie-unit2.png)

Your physical device is now set up to connect to IoT Hub.

### Exercise 2: Use Device Explorer

#### Task 1: Download and install Device Explorer

1. Go to <https://github.com/Azure/azure-iot-sdk-csharp/releases>.
2. Scroll down to find **SetupDeviceExplorer.msi**, and select it.

    ![SetupDeviceExplorer.msi](../media/22-ie-unit2.png)

3. Select **Run** to start the DeviceExplorer Setup Wizard.
4. On the **Welcome** page, select **Next**.

    ![Next button](../media/23-ie-unit2.png)

5. Finish the installation, and then select **Close**.

    ![Close button](../media/24-ie-unit2.png)

#### Task 2: Connect

1. Go to your Azure portal, and open the IoT hub again.

    ![IoT hub](../media/25-ie-unit2.png)

2. Select **Shared access policies**, and then select **iothubowner**.

    ![iothubowner](../media/26-ie-unit2.png)

3. Copy the value in the **Connection string – primary key** field.

    ![Copy button](../media/27-ie-unit2.png)

4. Start the Device Explorer that you installed on your computer.
5. Paste the connection string that you copied earlier, and then select **Update**.

    ![Update button](../media/28-ie-unit2.png)

6. Select **OK**.

    ![OK button](../media/29-ie-unit2.png)

7. On the **Data** tab, select **Monitor**.

    ![Monitor button](../media/30-ie-unit2.png)

    You should receive sensor data from your device in JavaScript Object Notation (JSON) format.

    ![Event Hub Data](../media/31-ie-unit2.png)
