To use Explicit Reference three-phase power measurement, it's necessary to first obtain and install two additional VTs (total of three), and to locate each of them in a receptacle supplied by a unique phase. All of this must be in reasonable proximity to the IoTaWatt such that the VT plugs reach the device.  An adapter is needed to reduce the voltage from the two additional VTs and to output to a 3.5mm stereo jack that can be used in a standard input channel of the IoTaWatt that has the burden resistor removed.

Here's what one such adapter looks like.  These should soon be available from the OEM store, along with various splitters and patch cords needed to connect.

![VT Adapter](https://screenshots.firefoxusercontent.com/images/7acefd19-ac36-4de8-90ca-a9f981de431e.jpg)

The output of the two VT adapters should be connected to two input channels on the IoTaWatt.  I suggest 13 and 14 for the sake of standardization.

### Configuring the voltage inputs.

Now the additional VTs can be configured and calibrated.  Do this in exactly the same way that the first VT is configured.  Click the channel number, click "VT" then specify the model.  Click Calibrate and calibrate the voltage to match your reference.  It's not necessary that the VTs be plugged into their eventual phase for this step.  If you have two outlets on any of the phases, use those to plug in each VT in turn along with a voltage reference while you calibrate.  Once calibrated, the VTs can be moved to the appropriate phase/socket.

Name each of the phases to uniquely identify each reference.  You can use Phase_A, Phase_B etc., or maybe use the color coding of your system to be more descriptive - Voltage_Red, Voltage_Black, Voltage_Blue (US).

Now start adding your CTs.  The twist here is that because more than one VT is configured, an additional selection box is displayed to specify which VT is associated with the phase of that particular CT.

![Three Phase VT selection](https://screenshots.firefoxusercontent.com/images/d367d33f-e58b-4c78-ac48-2fd440fa2af3.png)

If your service is consistently color coded, you should know the phase by the color of the conductor that you clamp the CT onto.

### Reporting Power

Once all of the VTs and CTs are configured, there are several ways to view the power used.  For circuits and/or loads that use only one phase, the power value displayed for that channel should be correct as is.  If there are devices that use two or three of the phases, you must add the power from each of the phases to get total power.  For each such device, define an output channel and use the calculator to specify adding the component channels.  If you are reporting the data to a server, the data can be tailored with the calculator to send the single combined aggregate power for those devices.



