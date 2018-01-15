(Note: This functionality is available with IoTaWatt release 02_02_28)

As previously explained, real three-phase power measurement requires a reference voltage/phase signal that is in phase with the current signal from the circuit.  That means in three-phase systems, you need three voltage signals, each 120° from the others.  IoTaWatt can accommodate three different VTs, each on a different "leg" of the three-phase system to do this.  In IoTaWatt terminology, that method is called Explicit Reference.

But there's another way to approach the problem, which, while not as exact, can produce pretty good results.  The IoTaWatt can numerically shift a single voltage/phase reference by 120° and 240° to measure power on the additional two legs. Using this method, a three-phase system can be monitored using the exact same equipment as for single phase.

This chapter explains how to configure IoTaWatt to use "Derived Reference" measurement.  It's pretty simple and straightforward.

Set up your IoTaWatt with the voltage reference VT on whatever leg of the three-phase is convenient.  For purposes of this discussion, we will henceforth call that leg "phase A".  The other two legs will be "phase B" and "phase C".  It's just a big circle anyway, so it's just a matter of where you start.  There are color coding schemes for the phases, but they vary so widely that I'm not going to try to reconcile this scheme with any of them.  That exercise is left to the reader.  The good news is that you really don't have to know what any of the phases are to complete this setup.

Connect CTs to each of the circuits that you want to measure, and configure them as described [here](https://github.com/boblemaire/IoTaWatt/wiki/Adding-Power-Channels-(CTs)). Be sure to orient all of the CTs the same way with respect to whatever polarity indicator they employ. The following instructions may not work as described if any CTs on the derived phases are reversed.

If you've done everything correctly, your IoTaWatt status display should be displaying the correct power for all of the circuits on phase A, and roughly half power for all of the circuits on phases B and C.

Now in the input configuration menu, click the box for "Enable derived three-phase" at the bottom.

![derived 3ph input](https://screenshotscdn.firefoxusercontent.com/images/a8befa90-45f8-42a4-a552-6e2179d8c8d2.png)

The configured input channels should now have "phase:**A**" appended to their descriptions. Now go to the status display and evaluate which of the inputs appear to be showing power that is half what is expected.  Note them and go back to the input configuration screen.

Edit each of the incorrect inputs in turn, changing the "Mains Phase" to phase B.
![Edit mains phase](https://screenshotscdn.firefoxusercontent.com/images/51a220a2-9209-43db-a0fb-e241a29d57ac.png)

Now go back to the status display and see which inputs still appear to be half of the expected value, go back to the input menu and change those to phase C.

![derived 3ph inputs](https://screenshotscdn.firefoxusercontent.com/images/91a8d4cc-23fa-4d4c-a595-a406cc077282.png)

The status display should now indicate the correct power for all of the phases.

One additional point.  Once you configure inputs to indicate mains phase B or C, the "Enable derived three-phase" checkbox will remain set and cannot be turned off unless all of the inputs are reconfigured back to phase A.