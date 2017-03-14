### What is a power channel?

Power channels measure the current flow through a circuit and combine that with the voltage to measure the current power, expressed in watts, and over time energy used, expressed in watt-hours.  Current is measured with a _current transformer_ hereafter referred to as a CT.  They come in a various capacities, physical connection type, and electrical output.  To learn more about CTs, visit this excellent reference at [OpenEnergyMonitor.org](https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/introduction).

The good news is that IoTaWatt supports a wide variety of available CTs, and many can be configured simply by clicking on the model.  Most IoTaWatt devices will have burden resistors installed on the input channels, and you will need to specify the values of those resistors when configuring each channel.  As a practical matter, we will assume that your device has 24ohm burden resistors.

Some CTs, called Voltage-type CTs, have burden resistors built in.  Those must be connected to IoTaWatt inputs that have no burden resistors.  More on this later.

### Connecting the CTs

This tutorial does not cover physical installation of the CTs to your electrical circuits.  That should be done by someone familiar with electrical wiring.  Your qualified installer will know how to do this.

The only additional recommendation is that all of the CTs be oriented the same way with respect to current flow.  Most CTs have an arrow or other marking to aid in consistent orientation. Not to worry, in the event some end up backward, IoTaWatt will still work, and will tell you which ones are backward.

### Configuring the Input Channels




