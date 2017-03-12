Successful startup will be indicated by alternating flashing of the red and blue leds on the ESP8266 module, or more accurately, by the absence of failure which is indicated by a single flashing red led about once per second. 

After successful startup, you can connect to the device with your web browser and run the configuration app. Use the url: iotawatt.local to run the app, or if your device has been renamed, use that name.local.  The configuration app starts with a row buttons:

![config top buttons](http://iotawatt.com/Images/config_bigideas.gif)

Click Device and Web Server.

![configure device](http://iotawatt.com/Images/config_device.gif)

You can change the device name to another 8 character name, or leave it IoTaWatt.  Remember, from now on, this(.local) will be the name that you will use to access the device from your your browser.

Set your local time zone relative to UTC time.  All of the measurements are time stamped using UTC, but the log messages and various reporting apps will use this factor to show the data in local time.

Configuring any Web Service will be covered in a later section and should remain "none" at this point.

Click **save** then **Commit and Restart** at the top.  Your changes will be saved and the device will restart.

After the lights indicate successful restart, restart the config app by refreshing your browser screen.  Remember, if you changed the name of your device, you will need to enter the new url: _yournewname_.local.