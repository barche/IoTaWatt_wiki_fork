#### Overview

The configuration app can provide a continuous updating display of the sample rates, running time, voltage, frequency, power and power-factor data that is being collected.  Simply click the **Input Channels Status** button.

![Input Channels Status](http://iotawatt.com/Images/input_channel_status_1.gif)

#### Samples per AC cycle

The recent average of the number of samples that the IoTaWatt collects each time it samples a channel. It will be around 500 if you are in a 60Hz country (As in North America), or 600 if you are in a 50Hz country (As in most of Europe).

#### AC Cycles sampled per second

The recent average rate that the IoTaWatt sampled input channels. The maximum is 40 times per second at 60Hz, and 33 at 50Hz.  In practice, the average is less than the theoretical maximum because the device does other things in addition to sampling, but most of the time the rate should be 80%-95% of the maximum.

#### Running Time 

The time (hh:mm:ss) that the IoTaWatt has been running since it was last restarted.  In general, the IoTaWatt should run indefinitely unless the power fails or it is deliberately restarted. If the running time is always low and there is no obvious reason for it, there may be a problem that is causing it to restart frequently.  The device is very robust and should not lose more than a few seconds of data during a restart, but the cause of frequent unexplained restarts should be investigated.

#### Channel Status

Each of the configured input channels listed with their associated measurements. Voltage reference channels (typically channel 0) will show the present voltage and AC line frequency.  Power channels will show the present load in watts, and channels with loads above 10 watts also show the power-factor.

