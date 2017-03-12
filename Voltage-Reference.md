A prime component of electrical power is voltage.  Also, the AC line frequency is the heartbeat of the IoTaWatt.  A reliable and accurate AC voltage reference is very important. You should have installed the device with a 9-12Vac voltage reference transformer plugged into the channel zero 5mm power jack. The initial configuration has this channel pre-configured as a generic "VT" or voltage-transformer. Your lights are blinking on the device because it is rhythmically sampling that voltage.

For accurate measurements, the VT input must be calibrated. To do this, you will need to have a decent voltmeter that can measure your AC line voltage.  The IoTaWatt is capable of very accurate voltage measurements, but the actual accuracy will depend on the accuracy of the reference used in this step.

While running the config app, click the "Configure Inputs" button:

![Configure VT](http://iotawatt.com/Images/config_inputs.gif)

Click on the "0" to edit the voltage channel:

![Edit VT](http://iotawatt.com/Images/config_edit_vt.gif)

Initially, the VT defaults to a "generic" transformer. Check the pull-down list of devices to see if your particular device is listed.  If it is, select it and skip to the calibration procedure below. The generic entry is a reasonable starting point that will get you in the ball park for a 9-12Vac adapter in a 120V installation.  If your country is 240V double it to 20.   

### calibration:

Now click calibrate->**voltage**:

![Calibrate voltage](http://iotawatt.com/Images/config_voltage_cal.gif)

Follow the instructions on the page. Increase or decrease the "cal" factor until the voltage shown settles down and is a pretty good match with your reference meter. It's not possible to match exactly.  .2V in a 120V installation is 0.2% variation.  Your meter accuracy is 1% at best, probably less.  Just get the two to jump around the same set of fractional digits.

As instructed on the page, click save to record the calibration factor, then save again from the edit channel screen.  I recommend then clicking "commit and Restart" to update the IoTaWatt and restart using the new value.

After restart, click the Status button to display the voltage:

![Voltage Status](http://iotawatt.com/Images/status_voltage.gif)
(gotta fix the 0.0Hz. Only happens when there's no CTs configured)

Check that the voltage displayed is still in the ball park.  If not, repeat the calibration procedure.

Once calibration is complete and verified, you will not need to do it again unless you change your VT transformer.  The IoTaWatt has a very accurate internal calibration reference and will maintain its accuracy indefinitely. You should have no further need for the voltmeter.


