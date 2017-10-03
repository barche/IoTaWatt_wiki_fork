When the device powers up, it attempts to connect to the last WiFi network used. Although the device can run without WiFi, a connection must be established if the real time clock is not set, or to run the configuration utility, or if logging to an external server like Emoncms is desired. It is strongly recommended to connect the device to a WiFi network that has a reliable internet connection.

If the device has never been connected to a WiFi network (new), or the last used network is not available, the ESP8266 will start up in AP (access point) mode. This state is indicated when the LED flashes the three color sequence RED-GREEN-GREEN.  It will have a recognizable SSID of iota + a unique number.  Connect to it using a smartphone or tablet. It will ask for a password.

The device password for a new IotaWatt device is simply IotaWatt (case sensitive).  If the device was previously configured and the device name was changed, that new name will be the password required in this step. After connecting, a page will be rendered allowing you to select (or specify) your network SSID and access key.

Once connected, the name of the new WiFi network will be saved, and the device will continue its startup procedure. If the device displays another three color LED sequence, see [Troubleshooting](https://github.com/boblemaire/IoTaWatt/wiki/Troubleshooting)

If the led begins blinking a rapid dull green, proceed to the next step [Device Configuration](https://github.com/boblemaire/IoTaWatt/wiki/Device-Configuration)