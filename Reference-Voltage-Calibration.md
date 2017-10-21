A prime component of electrical power is voltage.  Also, the AC line frequency is the heartbeat of the IoTaWatt.  A reliable and accurate AC voltage reference is very important. You should have installed the device with a 9-12Vac voltage reference transformer plugged into the channel zero 5mm power jack. The initial configuration has this channel pre-configured as a generic "VT" or voltage-transformer. Your lights are blinking on the device because it is rhythmically sampling that voltage.

At this point, IoTaWatt doesn't know exactly what VT has been connected, and can only make generalizations about AC reference.  We need to tell it what VT has been used, or supply generic parameters for a VT that it doesn't recognize. While running the config app, click the "Configure Inputs" button:

![Configure VT](http://iotawatt.com/Images/Config_edit_vt.PNG)

Click on the "0" to edit the voltage channel:

![Edit VT 0](https://screenshots.firefoxusercontent.com/images/22ab7a04-2aaf-48d3-8efe-302e9a07c0e5.png?download=Screenshot-2017-10-21%20IoTaWatt%20Configuration%20app.png&sig=jlfECjEBzfpbZoedOnc7EZowdYo)
 
Click the Model dropdown menu:

![Model Dropdown Menu](http://iotawatt.com/Images/Screenshot51.png)

If your make and model is listed, select it from the list.  At this point, you can just click SAVE and the standard calibration for your VT will be used.  That calibration should be good for all but the most discerning users.  If you have access to a very good voltmeter or other reliable high accuracy voltage reference, you can fine tune with the calibration procedure below, but for average users, you should be good to go on to the next step [Adding Power Channel CTs](https://github.com/boblemaire/IoTaWatt/wiki/Adding-Power-Channels-(CTs))

If your VT wasn't listed in the dropdown above, the generic entry is a reasonable starting point that will get you in the ball park for your 9-12Vac adapter. If your country is 230V or 240V select "generic240V".  Now you must perform the calibration procedure below.

### Calibration
You will need a halfway decent voltage reference for this step.  If you don't have a decent true RMS voltmeter and can't borrow one, go out and get a Kill-a-Watt.  They cost less than $20 (some libraries lend them out) and I've found their voltage readings are quite accurate. 

click ![Calibrate](http://iotawatt.com/Images/calibrate_button.PNG)

![Calibrate voltage](http://iotawatt.com/Images/Config_vt_calibrate.PNG)

Follow the instructions on the page. Increase or decrease the "cal" factor until the voltage shown settles down and is a pretty good match with your reference meter. It's not possible to match exactly.  .2V in a 120V installation is 0.2% variation.  A very good meter accuracy is 1% at best.  Just try to get the two to dwell around the same set of fractional digits.

As instructed on the page, click save to record the calibration factor.  The new calibration factor will take effect immediately. Click ![Input Channels Status](http://iotawatt.com/Images/input_channel_status_button.PNG) to display the voltage:

![input status screen](http://iotawatt.com/Images/Capture1.JPG)

Check that the voltage displayed is still in the ball park.  If not, repeat the calibration procedure.

Once calibration is complete and verified, you will not need to do it again unless you change your VT transformer.  The IoTaWatt has a very accurate internal calibration reference and will maintain its accuracy indefinitely. You should have no further need for the voltmeter.

Now the device is ready for the next step [Adding Power Channel CTs](https://github.com/boblemaire/IoTaWatt/wiki/Adding-Power-Channels-(CTs))


