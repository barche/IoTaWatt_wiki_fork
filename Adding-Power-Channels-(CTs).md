### What is a power channel?

Power channels measure the current flow through a circuit and combine that with the voltage to develop the power used, expressed in Watts.  Current is measured with a _current transformer_ hereafter referred to as a CT.  They come in a various capacities, physical connection type, and electrical output.  An excellent reference to learn more about these factors, see this tutorial at [OpenEnergyMonitor.org](https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/introduction).

The good news is that IoTaWatt supports a wide variety of available CTs, and many can be configured simply by clicking on the model.  Most IoTaWatt devices will have burden resistors installed on the input channels, and you will need to specify the values of those resistors when configuring each channel.  As a practical matter, we will assume that your device has 24ohm burden resistors.

Some CTs, called Voltage-type CTs, have burden resistors built in.  Those must be connected to IoTaWatt inputs that have no burden resistors.  More on this later.


