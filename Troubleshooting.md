## Led Indications

The IotaWatt has an external LED indicator that is usefull in determining the current state and for explicitely indicating serious problems. These are the known states and what they indicate:

### Dull Green Glow

This typically means that the device is connected and working properly.

### Not Illuminated

under virtually all circumstances, the led should be illuminated.  If not, the most probable cause is that there is no 5VDC supply.  The power supply may be faulty or the USB plug may not be inserted all the way.  Check these things first.
Try unplugging the 5VDC USB supply and reconnecting.  Try a different 5VDC supply if available.  If all else fails, a more serious problem with the device must be considered. Consult the supplier or someone who can troubleshoot electronic the hardware.

### Dull Red Glow

This indicates that the device is working properly, but either there is no WiFi connection or the real time clock is not initialized and the time cannot be established from time-servers on the internet via WiFi. As long as the real time clock is initialized, the IotaWatt can run indefinitely without WiFi.  If you are logging to Emoncms or another server, that will be suspended, but IotaWatt will recognize when the WiFi connection is restored, change the led to dull green, and send all of the data that it was unable to send during the outage.

To determine if IotaWatt is connected to the WiFi network, try to run the IotaWatt app from a browser on a device that is connected to the same WiFi network.  If it works, the problem was probably the real time clock. The app will set it automatically using the time on the browsing device and the led should turn green within a minute.

If the app doesn't start, there is a problem with the WiFi connection. To be sure, restart the IotaWatt by disconnecting the 5VDC power momentarily and then observe the led during startup.  Follow the troubleshooting guide for led indications during startup.

### Blinking Red/Green Pattern

IoTaWatt uses a repeating three color LED pattern to indicate various circumstances. They are:

#### Red-Green-Green

IoTaWatt is having trouble connecting to the WiFi network.
If this is a new IoTaWatt, or the network has changed, you will need to [specify a new network](https://github.com/boblemaire/IoTaWatt/wiki/Connecting-to-WiFi).
Otherwise, wait several minutes and the LED pattern should change to a new code.  Follow the advice for that code.

#### Green-Red-Red

IoTaWatt is having trouble accessing the SDcard inside the device.  This typically happens during a restart of the device. You will need to power off the device and open it up by removing the four screws located under the rubber feet.  Check that the SDcard is firmly seated in the socket and retry.

If problem persists, your card may have failed. You can try to insert the card into a computer that accepts SD cards to see if it can be read.  If so, the problem is probably the IoTaWatt SD card socket and the device will need to be replaced.  The good news is that the card should work in a replacement device and pick up where you left off with all historical data intact.

If your card cannot be read by another device, it is probably the card itself. Unfortunately, these things do fail from time-to-time. To be sure, insert any other available SDcard and try to restart.  If the error indication changes to something else, it is probably a failure of the SDcard.  Sadly, you will need to obtain a new one and initialize it with the files that are in the SD directory on this GitHub project.  All historical data is lost and you will need to reconfigure the device as if were new.

#### red-red-green

The configured WiFi network is unavailable and the real-time-clock is not running.  IoTaWatt can run without WiFi, but it cannot accumulate log data if it doesn't know what time it is, and it sets the real-time-clock from the internet. Restart and configure to use another WiFi network.

#### red-red-red

This is the catch-all panic code, where the firmware has detected a situation that should not happen, or is impossible to deal with.  Possibly there will be some diagnostic clues in the message log, or it may require connecting a serial terminal to the USB port to obtain further diagnostics.  Problems in this category are beyond the scope of this document.

