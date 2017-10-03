Successful startup will be indicated by a dull green glow on the LED.  If the LED is off, or blinking a three color sequence, see the [Troubleshooting](https://github.com/boblemaire/IoTaWatt/wiki/Troubleshooting) section.

After successful startup, you can connect to the device with your web browser and run the configuration app. Use the url: iotawatt.local to run the app, or if your device has been renamed, use that name.local.  The configuration app starts with a row of buttons:

![Config Main Menu](http://iotawatt.com/Images/config_main_menu.PNG)

Click Configure Device.

![Config Device](http://iotawatt.com/Images/Capture.JPG)

You can change the **Device name** to another 8 character name, or leave it IoTaWatt.  Remember, from now on, [Device name].local will be the name that you will use to access the device from your browser, and the name you will need to change to switch to a different WiFi network.

Set your local **Time Zone** relative to UTC time.  All of the measurements are time stamped using UTC, but the log messages and various reporting apps will use this factor to show the data in local time.

**Auto-update Class** tells IotaWatt whether you want to receive automatic updates of the firmware and what type of updates you are interested in.  The choices are:

* NONE - Do not Auto-update this device.
* MAJOR - only update major releases of the software.  This is recommended.
* MINOR - update with minor releases.  More frequent but somewhat tested firmware.
* BETA - Latest production firmware.
* ALPHA - Recently released firmware with the latest features - and the latest bugs.

IotaWatt checks the IotaWatt.com site for new software regularly, and the update process takes less than a minute.  The new firmware is digitally signed.

The **Configure Burden Resistors** button will allow specification of the burden resistors that are soldered to your board. Your device should be preconfigured and you should not need to go there.  If you have changed the resistors or built your own board with different values, click this button and specify the values for your particular custom hardware.

Click **save**. Your changes will be saved.   If you changed the name of your device, it will restart when you press save and you will need to restart the configuration application from [Device name].local.

The next step is checking the calibration of the voltage reference [Reference Voltage Calibration](https://github.com/boblemaire/IoTaWatt/wiki/Reference-Voltage-Calibration)