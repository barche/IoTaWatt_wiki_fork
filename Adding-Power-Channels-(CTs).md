### What is a power channel?

Power channels measure the current flow through a circuit and combine that with the reference voltage to determine power, expressed in watts, and to accumulate energy used, expressed in watt-hours.  Current through a circuit is measured indirectly by installing a passive sensor, called a _current transformer_ (CT), around one of the conductors in the circuit. CTs come in a various capacities, physical connection type, and electrical output.  To learn more about CTs, visit this excellent reference at [OpenEnergyMonitor.org](https://learn.openenergymonitor.org/electricity-monitoring/ct-sensors/introduction).

The good news is that IoTaWatt supports a wide variety of readily available CTs, and many can be configured simply by clicking on the model. Standard IoTaWatt devices have burden resistors installed on the input channels, and the value of those resistors will have been pre-configured or you will have specified them in the Configure Device section. For purposes of this tutorial, we will assume that your device has 24ohm burden resistors.

IotaWatt is designed to use 3.5mm stereo jacks (headphone jacks) to connect the CTs. There are a few standard CTs available with that connector, and [OpenEnergyMonitor](https://openenergymonitor.org/) has a selection available in their online store.  You can also get screw terminal-to-3.5mm jack adapters on Amazon and on Ebay.

Some CTs, called Voltage-type CTs, have burden resistors built in.  Those must be connected to IoTaWatt inputs that have no burden resistors. That is an advanced topic not covered in this tutorial.

### Connecting the CTs

This tutorial does not cover physical installation of the CTs to your electrical circuits.  That should be done by someone familiar with electrical wiring.  Your qualified installer will know how to do this. The 3.5mm connectors plug into any of the 14 input channels on the IotaWatt.

The only additional recommendation is that all of the CTs be oriented the same way with respect to current flow.  Most CTs have an arrow or other marking to aid in consistent orientation. Not to worry, in the event some end up backward, IoTaWatt will still work, and will tell you which ones appear to be backward.

### Configuring the Input Channels

At this point, you should have the IoTaWatt up and running with the voltage channel connected, configured, and calibrated if necessary. You are using the config app in a browser connected to your WiFi network.  Hover over the Setup menu item and click Inputs in the dropdown buttons.

![Config Inputs](https://screenshots.firefoxusercontent.com/images/f51f5425-ae3f-45ec-9d69-13bee4719ff6.png)

This screen should look familiar. We came here to configure the voltage transformer (VT).  Now we will configure current transformers (CTs), to other inputs. To add or edit the CT specification for an input channel, click the channel's number button.  Let's add a CT to channel 1. 

![Config Input 1](https://screenshots.firefoxusercontent.com/images/052ed1f4-7a1d-4f54-81ab-5811cc30f22c.png)

The app enters channel edit mode. Here you specify the model and other details about the CT connected to this particular channel.  But first, it is helpful to name the channel by typing a name in the name box. You can just use the default "Input_1" or something more meaningful like "Kitchen" or "Living Room" or "Main".

The default type is CT and we will stick with that as input 0 is our VT.

The next drop-down box is the model of the CT.  Initially it will be _generic_, but you probably have a CT that is in the dropdown list, so click the drop-down list and look for your CT.  Lets say you have an SCT019-000 (an inexpensive CT that has a 200 amp capacity suitable for a typical Main in the US).  Click on SCT019-000.

![Config input 1 sct019-000](https://screenshots.firefoxusercontent.com/images/6b943e13-e714-4db1-81dc-15999a7a0602.png
)

Notice that after selecting a specific device from the table, the input fields for "turns" and "phase" disappear.  That's because those values are known for the listed CTs.  If you have a CT that is not found in the list, you will need specify the "generic" entry and provide the turns-ratio and phase-lead for that CT.

Note the checkbox for "Allow negative power values".  This is typically checked only for mains in an installation with grid-tied solar (net-metering).  Checking this box tells IoTaWatt that it is normal for current to flow backward through this circuit, as when a PV system creates more power than you are using locally and the balance is "exported" to the grid.  When you check this box you are affirming that the CT is installed correctly and that negative power should not be automatically "corrected" to positive.

Press ![Save](http://iotawatt.com/Images/save_button.PNG) to finish.

![config input 1 listed](https://screenshots.firefoxusercontent.com/images/1dda8fe4-5df0-4684-9d14-a6446ad44d60.png)

That's it.  The screen returns to the complete list of inputs where you can add more channels or change the configuration of existing inputs. Each time you press save, the new configuration is sent to IoTaWatt and the changes take effect immediately. If the CTs are installed and connected, you will can see the power displayed in the Input Channel Status screen.

### Generic CT

We just configured a _current type_ CT that was of a model known to IoTaWatt.  If your particular CT is not one of the dropdown models, you will need to describe the "generic" parameters. You will recall that this is the initial model designation for a CT when a new channel is added.  Its also a drop-down choice when editing a CT channel.  With this model selected, you must specify additional information depending on the type of CT:

## Current Type CT

Current type CTs are typically described with an output in milliamps (mA).  They have no internal burden resistor.  They must be connected to a standard IoTaWatt input channel that has a burden resistor specified.  For these CTs, you will be asked to specify the "Turns:".  This is the ratio of primary current(what you are measuring)/secondary current (what is presented to IoTaWatt).  Most manufacturers publish the turns ratio for their device.  Typically the primary/secondary currents are printed on the device.  A YHCT SCT013-000 is marked 100A/50mA.  That's 100/.050 = 2000 Turns Ratio.

## Voltage Type CT

Voltage type CTs are typically decribed with an output in volts (V).  They have an internal burden resistor and must be connected to an IoTaWatt input that has had the internal burden resistor removed and specified as zero in the device configuration burden menu.  IoTaWatt will ask for a "Cal:" factor.  This is the current in amps that corresponds to 1 volt of output from the CT.  An example of this is the SCT013-050 from YHDC.  It is marked 50A/1V, so the "Cal:" is 50.  Simple enough.

## Phase

Both of the generic CT types above will also provide a place to specify "Phase:". Representative samples of the CTs in the model list have been tested to determine the phase lead value. If you have a generic CT a good rule of thumb would be to use 2.0 for a split core CT (one that snaps onto a wire), and 0.5 for solid core CTs (Basically a solid doughnut that you pass the conductor through).

Basic installation and configuration are essentially done now.  Use the [Device Status Display](https://github.com/boblemaire/IoTaWatt/wiki/Input-Channel-Status) to see what's happening, and [Connecting to eMonCMS](https://github.com/boblemaire/IoTaWatt/wiki/Connecting-to-eMonCMS) to setup logging to the Emoncms service.

