As previously explained, real three-phase power measurement requires a reference voltage/phase signal that is in phase with the current signal from the circuit.  That means in three-phase systems, you need three voltage signals, each 120° from the others.  IoTaWatt can accommodate three different VTs, each on a different "leg" of the three-phase system to do this.  In IoTaWatt terminology, that method is called Explicit Reference.

But there's another way to approach the problem, which, while not as exact, can produce pretty good results.  The IoTaWatt can numerically shift a single voltage/phase reference by 120° and 240° to measure power on the additional two legs. Using this method, a three-phase system can be monitored using the exact same equipment as for single phase.

This chapter explains how to configure IoTaWatt to use "Derived Reference" measurement.  It's pretty simple and straightforward.

Set up your IoTaWatt with the voltage reference VT on whatever leg of the three-phase is convenient.  For purposes of this discussion, we will henceforth call that leg "phase A".  The other two legs will be "phase B" and "phase C".  It's just a big circle anyway, so it's just a matter of where you start.  There are color coding schemes for the phases, but they vary so widely that I'm not going to try to reconcile this scheme with any of them.  That exercise is left to the reader.  The good news is that you really don't have to know what any of the phases are to complete this setup.

Connect CTs to each of the circuits that you want to measure, and configure them as described [here](https://github.com/boblemaire/IoTaWatt/wiki/Adding-Power-Channels-(CTs)).

If you've done everything correctly, your IoTaWatt status display should be displaying the correct power for all of the circuits on phase A, and roughly half power for all of the circuits on phases B and C.

Now in the input configuration menu, click the box for "Enable derived three-phase" at the bottom.

