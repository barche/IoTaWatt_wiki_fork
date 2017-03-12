When the device powers up, it attempts to connect to the last WiFi network used. Although the device can run without WiFi, at present a connection must be established during startup.

If the device has never been connected to a WiFi network (new), or the last used network is not available, the ESP8266 will start up in AP (access point) mode. It will have a recognizable SSID (either "IoTaWatt" or the name previously assigned to the device).  Connect to it using a smartphone or tablet. After connecting, a page will be rendered allowing you to select (or specify) your network SSID and access key.

Once connected, the access point will disappear, the name of the new WiFi network will be saved, and the device will continue its startup procedure.