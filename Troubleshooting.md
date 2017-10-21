## Led Indications

The IotaWatt has an external LED indicator that is usefull in determining the current state and for explicitely indicating serious problems. These are the known states and what they indicate:

### Dull Green Glow

This typically means that the device is connected and working properly.

### Not Illuminated

under virtually all circumstances, the led should be illuminated.  If is not, the most probable cause is that there is no 5VDC supply.  The power supply may be faulty or the USB plug may not be inserted all the way.  Check these things first.
Try unplugging the 5VDC USB supply and reconnecting.  Try a different 5VDC supply if available.  If all else fails, a more serious problem with the device must be considered. Consult the supplier or someone who can troubleshoot electronic the hardware.

### Dull Red Glow

This indicates that the device is working properly, but either there is no WiFi connection or the real time clock is not initialized and the time cannot be established from time-servers on the internet via WiFi. As long as the real time clock is initialized, the IotaWatt can run indefinitely without WiFi.  If you are logging to Emoncms or another server, that will be suspended, but IotaWatt will recognize when the WiFi connection is restored, change the led to dull green, and send all of the data that it was unable to send during the outage.

To determine if IotaWatt is connected to the WiFi network, try to run the IotaWatt app from a browser on a device that is connected to the same WiFi network.  If it works, the problem was probably the real time clock. The app will set it automatically using the time on the browsing device and the led should turn green within a minute.

If the app doesn't start, there is a problem with the WiFi connection. To be sure, restart the IotaWatt by disconnecting the 5VDC power momentarily and then observe the led during startup.  Follow the troubleshooting guide for led indications during startup.

### Blinking Red/Green LED

IoTaWatt uses a repeating three color LED pattern to indicate various circumstances. They are:

#### Red-Green-Green

IoTaWatt is having trouble connecting to the WiFi network.
If this is a new IoTaWatt, or the network has changed, you will need to (https://github.com/boblemaire/IoTaWatt/wiki/Connecting-to-WiFi)[specify a new network].
If the network is down, or unavailable for some other reason, IoTaWatt will continue to try to connect indefinitely. After an initial period, if connection is not established, the LED will change to a [https://github.com/boblemaire/IoTaWatt/wiki/Troubleshooting#dull-red-glow](dull red glow).

