### What is a power channel?

Power channels measure the current flow through a circuit and combine that with the voltage to measure power, expressed in watts, and to accumulate energy used, expressed in watt-hours.  Current through a circuit is measured indirectly by installing a passive sensor, called a _current transformer_ (CT), around one of the conductors in the circuit. CTs come in a various capacities, physical connection type, and electrical output.  To learn more about CTs, visit this excellent reference at [OpenEnergyMonitor.org](https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/introduction).

The good news is that IoTaWatt supports a wide variety of available CTs, and many can be configured simply by clicking on the model.  Most IoTaWatt devices will have burden resistors installed on the input channels, and you will need to specify the values of those resistors when configuring each channel. For purposes of this tutorial, we will assume that your device has 24ohm burden resistors.

Some CTs, called Voltage-type CTs, have burden resistors built in.  Those must be connected to IoTaWatt inputs that have no burden resistors.  More on that later.

### Connecting the CTs

This tutorial does not cover physical installation of the CTs to your electrical circuits.  That should be done by someone familiar with electrical wiring.  Your qualified installer will know how to do this.

The only additional recommendation is that all of the CTs be oriented the same way with respect to current flow.  Most CTs have an arrow or other marking to aid in consistent orientation. Not to worry, in the event some end up backward, IoTaWatt will still work, and will tell you which ones are backward.

### Configuring the Input Channels

At this point, you should have the IoTaWatt up and running with the voltage channel connected, configured, and calibrated. You are using the config app in a browser connected to your WiFi network.  Click the _Configure Inputs_ button.

![Config Inputs](http://iotawatt.com/Images/config_inputs_1.gif)

Click the drop-down menu _Add Channels_ and choose the channel that you want to add to the configuration. Lets say we chose channel 4.

![Config Chan 4](http://iotawatt.com/Images/config_chan4_1.gif)

The channel is added and the app enters channel edit mode, where you specify the model and other details about the CT connected to this particular channel.  But first, it is helpful to name the channel by typing a name in the name box. You can just use "Chan 4" or something more meaningful like "Kitchen" or "Living Room".

Next there is a drop-down menu to select the type of input channel this is.  At this point, we will stick to CT.

The next drop-down box is the model of the CT.  It will be _generic_, but you probably have a CT that is in the dropdown list, so click peruse the drop-down list and look for your CT.  Lets say you have an SCT013-000 (a popular, inexpensive CT that is widely available).  Click on SCT013-000.

![Config chan4 sct013-000](http://iotawatt.com/Images/config_sct013-000_1.gif)

Notice that now there is a box to specify the _burden_ resistor value.  You should know the value of the burden on each of your IoTaWatt channels.  Enter burden value and a _save_ option should be added to the row of buttons.

![config Chan4 Save](http://iotawatt.com/Images/config_chan4_burden_1.gif)

Click _save_.

![Config Chan4 Done](http://iotawatt.com/Images/config_chan4_done_1.gif)

That's it.  The screen returns to the complete list of inputs where you can add more channels, or you can press _Commit and Restart_ at the top to update the configuration file on the IoTaWatt and restart it using the newly configured channels. If you need to change anything about an existing channel, just click on it's channel number button and edit the contents.

### Other types of CTs

We just configured a _current type_ CT and specified the burden value of that IoTaWatt channel.  As mentioned at the top, there are different types of CTs, and some require other parameters to be specified:

### Voltage Type CTs

These are probably the easiest type of CT to configure, however they contain an integral burden resistor, so must be connected to an IoTaWatt channel with no on-board burden, or the on-board burden must be removed.  To configure one of these (A typical model would be the SCT013-030), just select it from the drop-down list and click _save_.

### Generic Type CT

You will recall that this is the initial model designation for a CT when a new channel is added.  Its also a drop-down choice when editing a CT channel.  With this model selected, you can specify any calibration factor _cal_ and phase shift for the CT.  This method is intended for a user who knows how to develop these numbers.  For their benefit, the _cal_ factor is the primary amps corresponding to a 1V input to the channel.  The cal factor is typically computed by dividing the "turns ratio" of the CT by the burden resistor value.

