### What is a power channel?

Power channels measure the current flow through a circuit and combine that with the reference voltage to measure power, expressed in watts, and to accumulate energy used, expressed in watt-hours.  Current through a circuit is measured indirectly by installing a passive sensor, called a _current transformer_ (CT), around one of the conductors in the circuit. CTs come in a various capacities, physical connection type, and electrical output.  To learn more about CTs, visit this excellent reference at [OpenEnergyMonitor.org](https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/introduction).

The good news is that IoTaWatt supports a wide variety of available CTs, and many can be configured simply by clicking on the model.  Most IoTaWatt devices will have burden resistors installed on the input channels, and the value of those resistors will have been pre-configured or you will have specified them in the Configure Device section. For purposes of this tutorial, we will assume that your device has 24ohm burden resistors.

IotaWatt is designed to use 3.5mm stereo jacks for CT input. There are a few standard CTs available with that connector, and [OpenEnergyMonitor](https://openenergymonitor.org/) has a selection in different current ranges available in their online store.  You can also get screw terminal-to-3.5mm jack adapters on Amazon and on Ebay.

Some CTs, called Voltage-type CTs, have burden resistors built in.  Those must be connected to IoTaWatt inputs that have no burden resistors. That is an advanced topic not covered in this tutorial.

### Connecting the CTs

This tutorial does not cover physical installation of the CTs to your electrical circuits.  That should be done by someone familiar with electrical wiring.  Your qualified installer will know how to do this.

The only additional recommendation is that all of the CTs be oriented the same way with respect to current flow.  Most CTs have an arrow or other marking to aid in consistent orientation. Not to worry, in the event some end up backward, IoTaWatt will still work, and will tell you which ones are backward.

### Configuring the Input Channels

At this point, you should have the IoTaWatt up and running with the voltage channel connected, configured, and calibrated. You are using the config app in a browser connected to your WiFi network.  Click the _Configure Inputs_ button.

![Config Inputs](http://iotawatt.com/Images/Config_edit_vt.PNG)

This screen should look familiar. We came here to configure the voltage transformer (VT).  Now we will configure current transformers (CTs), to other inputs. To add or edit the CT specification for an input channel, click the channel's number button.  Let's add a CT to channel 1. 

![Config Input 1](http://iotawatt.com/Images/Config_input_1.PNG)

The app enters channel edit mode, where you specify the model and other details about the CT connected to this particular channel.  But first, it is helpful to name the channel by typing a name in the name box. You can just use the default "Input_1" or something more meaningful like "Kitchen" or "Living Room" or "Main".

The default type is CT and we will stick with that as input 0 is our VT.

The next drop-down box is the model of the CT.  It will be _generic_, but you probably have a CT that is in the dropdown list, so click the drop-down list and look for your CT.  Lets say you have an SCT019-000 (an inexpensive CT that has a 200 amp capacity suitable for a typical Main in the US).  Click on SCT019-000.

![Config input 1 sct019-000](http://iotawatt.com/Images/Config_input_1_device.png)

Notice that after selecting a specific device from the table, the input fields for "turns" and "phase" disappear.  That's because those values are known for the listed CTs.  If you have a CT that is not found in the list, you will need specify the "generic" entry and provide the turns-ratio and phase-lead for that CT.

Note the checkbox for "Allow negative power values".  This is typically checked only for mains in an installation with grid-tied solar (net-metering).  Checking this box tells IoTaWatt that it is normal for current to flow backward through this circuit, as when a PV system creates more power than you are using locally and the balance is "exported" to the grid.  When this box is checked IoTaWatt assumes that the CT is installed correctly and will not automatically assume the CT is backwards and correct the result to a positive value.

Press ![Save](http://iotawatt.com/Images/save_button.PNG) to finish.

![config input 1 listed](http://iotawatt.com/Images/Config_input_1_list.PNG)

That's it.  The screen returns to the complete list of inputs where you can add more channels or change the configuration of existing inputs. Each time you press save, the new configuration is sent to IoTaWatt and the changes take effect immediately. If the CTs are installed and connected, you will can see the power displayed in the Input Channel Status screen.

### Other types of CTs

We just configured a _current type_ CT and specified the burden value of that IoTaWatt channel.  As mentioned at the top, there are different types of CTs, and some require other parameters to be specified:

### Voltage Type CTs

These are probably the easiest type of CT to configure, however they contain an integral burden resistor, so must be connected to an IoTaWatt channel with no on-board burden (specified as zero in the Configure Burden Resistors screen), When an input has no burden resistor, voltage type CTs will be displayed in the device dropdown menu. To configure one of these (A typical model would be the SCT013-030), just select it from the drop-down list and click _save_.

### Generic Type CT

You will recall that this is the initial model designation for a CT when a new channel is added.  Its also a drop-down choice when editing a CT channel.  With this model selected, you can specify any calibration factor _cal_ and phase shift for the CT.  This method is intended for a user who knows how to develop these numbers.  For their benefit, the _cal_ factor is the primary amps corresponding to a 1V input to the channel.  The cal factor is typically computed by dividing the "turns ratio" of the CT by the burden resistor value.  If the input has a burden resistor specified, you need will specify the turns ratio of the CT and the calibration factor will be computed.

Basic installation and configuration are essentially done now.  Use the [Input Channel Status Display](https://github.com/boblemaire/IoTaWatt/wiki/Input-Channel-Status) to see what's happening, and [Connecting to eMonCMS](https://github.com/boblemaire/IoTaWatt/wiki/Connecting-to-eMonCMS) to setup logging to the Emoncms service.

