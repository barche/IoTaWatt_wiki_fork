A prime component of electrical power is voltage.  Also, the AC line frequency is the heartbeat of the IoTaWatt.  A reliable and accurate AC voltage reference is very important. You should have installed the device with a 9-12Vac voltage reference transformer plugged into the channel zero 5mm power jack. The initial configuration has this channel pre-configured as a generic "VT" or voltage-transformer. Your lights are blinking on the device because it is rhythmically sampling that voltage.

For accurate measurements, the VT input must be calibrated. If your IoTaWatt was supplied as a calibrated VT/IoTaWatt pair, you're good to go.  Calibration has been done and this step isn't necessary. If not already calibrated, or you have installed a new voltage transformer, you should perform this simple procedure.

You will need a halfway decent voltage reference for this step.  If you don't have a decent true RMS voltmeter and can't borrow one, go out and get a Kill-a-Watt.  They cost less than $20 (some libraries lend them out) and I've found their voltage readings are quite accurate. It pretty much matches my Fluke true-rms voltmeter. (Amps and power on the units I tested seem to be a bit low but voltage is great). 

While running the config app, click the "Configure Inputs" button:

![Configure VT](http://iotawatt.com/Images/Config_edit_vt.PNG)

Click on the "0" to edit the voltage channel:

![Edit VT](http://iotawatt.com/Images/Config_edit_vt0.PNG)

Initially, the VT defaults to a "generic" transformer. Check the pull-down list of devices to see if your particular device is listed.  If it is, select it and skip to the calibration procedure below. The generic entry is a reasonable starting point that will get you in the ball park for a 9-12Vac adapter in a 120V installation.  If your adapter is not listed and your country is 240V select the "generic240V" entry.

### calibration:

Now click ![Calibrate](http://iotawatt.com/Images/calibrate_button.PNG)

![Calibrate voltage](http://iotawatt.com/Images/Config_vt_calibrate.PNG)

Follow the instructions on the page. Increase or decrease the "cal" factor until the voltage shown settles down and is a pretty good match with your reference meter. It's not possible to match exactly.  .2V in a 120V installation is 0.2% variation.  A very good meter accuracy is 1% at best.  Just try to get the two to dwell around the same set of fractional digits.

As instructed on the page, click save to record the calibration factor.  The new calibration factor will take effect immediately. Click ![Input Channels Status](http://iotawatt.com/Images/input_channel_status_button.PNG) to display the voltage:

![Voltage Status](http://iotawatt.com/Images/input_status_vt.PNG)

Check that the voltage displayed is still in the ball park.  If not, repeat the calibration procedure.

Once calibration is complete and verified, you will not need to do it again unless you change your VT transformer.  The IoTaWatt has a very accurate internal calibration reference and will maintain its accuracy indefinitely. You should have no further need for the voltmeter.

Now the device is ready for the next step [Adding Power Channel CTs](https://github.com/boblemaire/IoTaWatt/wiki/Adding-Power-Channels-(CTs))


