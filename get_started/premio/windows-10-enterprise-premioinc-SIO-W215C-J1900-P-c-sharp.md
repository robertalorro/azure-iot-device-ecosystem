---
platform: Windows 10 Enterprise LTSC
device: SIO-W215C 15.6in 16x9 IP69K PCAP Washdown Panel PC
language: csharp
--- 

Run a simple Csharp sample on SIO-W215C 15.6in 16x9 IP69K PCAP Washdown Panel PC device running Windows 10 Enterprise LTSC
===
---

# Table of Contents

-   [Introduction](#Introduction)
-   [Step 1: Prerequisites](#Prerequisites)
-   [Step 2: Prepare your Device](#PrepareDevice)
-   [Step 3: Build and Run the Sample](#Build)
-   [Next Steps](#NextSteps)

<a name="Introduction"></a>
# Introduction

**About this document**

This document describes how to connect SIO-W215C 15.6in 16x9 IP69K PCAP Washdown Panel PC device running Windows 10 Enterprise LTSC with Azure IoT SDK. This multi-step process includes:
-   Configuring Azure IoT Hub
-   Registering your IoT device
-   Build and deploy Azure IoT SDK on device

<a name="Prerequisites"></a>
# Step 1: Prerequisites

You should have the following items ready before beginning the process:

-   [Prepare your development environment][setup-devbox-windows]
-   [Setup your IoT hub][lnk-setup-iot-hub]
-   [Provision your device and get its credentials][lnk-manage-iot-hub]
-   SIO-W215C 15.6in 16x9 IP69K PCAP Washdown Panel PC.


<a name="PrepareDevice"></a>
# Step 2: Prepare your Device

-   After powering up your SIO-W215C 15.6in 16x9 IP69K PCAP Washdown Panel PC device, be sure that it has established a network connection whether it is through ethernet, Wi-Fi, or cellular. For more information, please download the device's <a href="https://premio.blob.core.windows.net/premio/uploads/resource/user-manual/UM_SIO-200.pdf" rel="nofollow">User's Manual</a>.

<a name="Build"></a>
# Step 3: Build and Run the sample

-   Download the [Azure IoT SDK](https://github.com/Azure/azure-iot-sdk-csharp) and the sample programs and save them to your local repository.
-   Open a device console (command prompt or a powershell window) and change to your local SDK **azure-iot-sdk-csharp** directory.

-  Add the Iot Hub device connection string on your device as an environment variable:

		setx IOTHUB_DEVICE_CONN_STRING <yourDeviceConnectionString>

-  Run the following command to build the SDK:

		build.cmd -config Release
        
- From the device console, run the sample using following command:

	**If HTTP protocol:**

		cd iothub\device\samples\DeviceClientHttpSample\bin\Debug\netcoreapp2.0
		dotnet DeviceClientHttpSample.dll

	**If MQTT protocol:**

		cd iothub\device\samples\DeviceClientMqttSample\bin\Debug\netcoreapp2.0
		dotnet DeviceClientMqttSample.dll
		
	**If AMQP protocol:**

		cd iothub\device\samples\DeviceClientAmqpSample\bin\Debug\netcoreapp2.0
		dotnet DeviceClientAmqpSample.dll

-   Use the **DeviceExplorer** utility to observe the messages IoT Hub receives from the **Device Client Sample** application.
-   Refer "Monitor device-to-cloud events" in [DeviceExplorer Usage document](https://github.com/Azure/azure-iot-sdk-csharp/blob/master/tools/DeviceExplorer/doc/how_to_use_device_explorer.md) to see the data your device is sending.
-   Refer "Send cloud-to-device messages" in [DeviceExplorer Usage document](https://github.com/Azure/azure-iot-sdk-csharp/blob/master/tools/DeviceExplorer/doc/how_to_use_device_explorer.md) for instructions on sending messages to device.

<a name="NextSteps"></a>
# Next Steps

You have now learned how to run a sample application that collects sensor data and sends it to your IoT hub. To explore how to store, analyze and visualize the data from this application in Azure using a variety of different services, please click on the following lessons:

-   [Manage cloud device messaging with iothub-explorer]
-   [Save IoT Hub messages to Azure data storage]
-   [Use Power BI to visualize real-time sensor data from Azure IoT Hub]
-   [Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]
-   [Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]
-   [Remote monitoring and notifications with Logic Apps]   

[Manage cloud device messaging with iothub-explorer]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-explorer-cloud-device-messaging
[Save IoT Hub messages to Azure data storage]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-store-data-in-azure-table-storage
[Use Power BI to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-power-bi
[Use Azure Web Apps to visualize real-time sensor data from Azure IoT Hub]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-live-data-visualization-in-web-apps
[Weather forecast using the sensor data from your IoT hub in Azure Machine Learning]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-weather-forecast-machine-learning
[Remote monitoring and notifications with Logic Apps]: https://docs.microsoft.com/en-us/azure/iot-hub/iot-hub-monitoring-notifications-with-azure-logic-apps
[setup-devbox-windows]: https://github.com/Azure/azure-iot-sdk-csharp/blob/master/doc/devbox_setup.md
[lnk-setup-iot-hub]: ../../setup_iothub.md
[lnk-manage-iot-hub]: ../../manage_iot_hub.md
