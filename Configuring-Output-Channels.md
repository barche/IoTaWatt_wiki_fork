Output channels provide useful values that are computed from input channel values using a calculator like interface. For instance, in a typical US installation, there are two MAIN circuits, the sum of the two is the total power into a panel.  Its nice to know at a glance what that total is, but the two mains are measured separately using two input channels.  We need a way to add them together to display the total usage.

Click Configure Outputs.

![Config Outputs](http://iotawatt.com/Images/Config_outputs_add.PNG)

This screen will list any outputs that you have already configured, and allow you to click "add" to create new ones.  You may click "edit" on existing outputs to change or delete them.  There is no practical limit to the number of outputs that you may create.  The only requirement is that they be uniquely named.

So lets click ADD:

![Config Outputs Calculator](http://iotawatt.com/Images/Config_outputs_calc.PNG)

This is the "calculator" interface that IoTaWatt uses to specify how to calculate an output using input channel values.  It works just like the simple four function calculators we are all used to, with the exception that by pressing the "input" key, you can select that an input channel value is to be inserted to the formula that you are creating. The resulting expression is evaluated left to right, except that calculations within parenthesis are evaluated before being used.

So lets make an output channel that combined two main inputs called Main_1 and Main_2. We enter the name Total_power in the Name box and hover over the "inputs" button of the calculator to see a list of the inputs.

![Config Output Total1](http://iotawatt.com/Images/Config_output_total1.png)

Select Main_1 from the list and it will appear in the calculator formula display.  Next press the + key, then repeat the input process selecting Main_2.

![Config Output Total 2](http://iotawatt.com/Images/Config_output_total2.PNG)

Easy as that.  Now press save to return to the outputs list.  Your new output should appear within a second or two.

![Config Outputs Total 3](http://iotawatt.com/Images/Config_output_total3.PNG)

Now go back to the Channels Status screen and see that the new output channel is listed and indeed has a value that is the sum of the two inputs Main_1 and Main_2.

![Config Output Total 4](http://iotawatt.com/Images/Config_output_total4.PNG)

Some other useful outputs would be:
* Power used in a solar PV system, calculated by anning the Solar inverter input to the (signed) Main input.  If for instance the inverter were putting out 4500 watts and your Main(s) indicated an outflow represented as -3100 watts, local usage would be 1400 watts with 3100 watts exported.
* You can measure some (US) 240volt circuits with a single CT on one of the conductors, then create an output that multiplies that value by 2 to get the true watts.
* Where the Main(s) are monitored and selected circuits within the panel are also measured, you can create an output that shows what the aggregate unmeasured usage is by subtracting the measured inputs from the Mains (or local use if PV).

![Config Outputs Misc](http://iotawatt.com/Images/Config_outputs_misc.PNG)
![Config Outputs Disp](http://iotawatt.com/Images/Config_outputs_disp.PNG)
 