Successful startup will be indicated by a dull green glow on the LED.  If the LED is off, or blinking a three color sequence, see the [Troubleshooting](https://github.com/boblemaire/IoTaWatt/wiki/Troubleshooting) section.

After successful startup, you can connect to the device with your web browser and run the configuration app. Use the url: iotawatt.local to run the app, or if your device has been renamed, use that name.local.  The configuration app starts with a row of buttons:

![Config Main Menu](http://iotawatt.com/Images/config_main_menu.PNG)

Click Configure Device.

![Config Device](http://iotawatt.com/Images/Config_device.PNG)

You can change the device name to another 8 character name, or leave it IoTaWatt.  Remember, from now on, this(.local) will be the name that you will use to access the device from your your browser.

The number of input channels will be 7, 14, or 21 for IoTaWatt 2.1 Hardware, depending on the whether you have 1, 2 or 3 ADC boards respectively.  IoTaWatt 3.0 supports 15 channels.  When that is released shortly, there will be a menu pick on thscreen to select which hardware device you have. 

Set your local time zone relative to UTC time.  All of the measurements are time stamped using UTC, but the log messages and various reporting apps will use this factor to show the data in local time.

The configure burden resistors button will allow specification of any burden resistors that are soldered to your board.  The default configuration in this Git specifies 24ohm burden resistors for all inputs.  If your board has another configuration, click this button and specify the values for your particular custom hardware.

Click **save**. Your changes will be saved.   If you changed the name of your device, it will restart when you press save and you will need to restart the configuration application from _newname_.local.