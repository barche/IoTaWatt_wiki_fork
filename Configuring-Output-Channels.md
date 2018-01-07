Output channels provide useful values that are computed from input channel values using a calculator like interface. For instance, in a typical US installation, there are two MAIN circuits, the sum of the two is the total power into a panel.  Its nice to know at a glance what that total is, but the two mains are measured separately using two input channels.  We need a way to add them together to display the total usage.

Click Configure Outputs.

![Config Outputs](https://screenshots.firefoxusercontent.com/images/3f88592b-9af1-45ed-8061-7000b2536f35.png)

This screen will list any outputs that you have already configured, and allow you to click "add" to create new ones.  You may click "edit" on existing outputs to change or delete them.  There is no practical limit to the number of outputs that you may create.  The only requirement is that they be uniquely named.

So lets click ADD:

![Config Outputs Calculator](https://screenshots.firefoxusercontent.com/images/1f76a452-cd68-4728-a64e-229b81280836.png)

This is the "calculator" interface that IoTaWatt uses to specify how to calculate an output using input channel values.  It works just like the simple four function calculators we are all used to, with the exception that by pressing the "input" key, you can select that an input channel value is to be inserted to the formula that you are creating. The resulting expression is evaluated left to right, except that calculations within parenthesis are evaluated before being used.

So lets make an output channel that combined two main inputs called Main_1 and Main_2. We enter the name Total_power in the Name box and hover over the "inputs" button of the calculator to see a list of the inputs.

![Config Output Total1](https://screenshots.firefoxusercontent.com/images/ff82ab33-ddd6-487f-bc1d-d994cd6fb4d7.png
)

Select Main_1 from the list and it will appear in the calculator formula display.  Next press the + key, then repeat the input process selecting Main_2.

![Config Output Total 2](https://screenshots.firefoxusercontent.com/images/f9e6d9cf-766e-4ae6-a330-ad493b80a369.png)

Easy as that.  Now press save to return to the outputs list.  Your new output should appear within a second or two.

![Config Outputs Total 3](https://screenshots.firefoxusercontent.com/images/46e8b31a-4ca4-4f3c-9e7f-9b853ec626ea.png)

Now go back to the Channels Status screen and see that the new output channel is listed and indeed has a value that is the sum of the two inputs Main_1 and Main_2.

![Config Output Total 4](https://screenshots.firefoxusercontent.com/images/66705480-9d8e-48ff-91e5-bec4d4660d81.png)

Some other useful outputs would be:
* Power used in a solar PV system, calculated by adding the Solar inverter input to the (signed) Main input.  If for instance the inverter were putting out 4500 watts and your Main(s) indicated an outflow represented as -3100 watts, local usage would be 1400 watts with 3100 watts exported.
* You can measure some (US) 240volt circuits with a single CT on one of the conductors, then create an output that multiplies that value by 2 to get the true watts.
* Where the Main(s) are monitored and selected circuits within the panel are also measured, you can create an output that shows what the aggregate unmeasured usage is by subtracting the measured inputs from the Mains (or local use if PV).

![Config Outputs Misc](https://screenshots.firefoxusercontent.com/images/b3e9b20b-7406-435e-ab94-a6e58f7c97ed.png)
![Config Outputs Disp](https://screenshots.firefoxusercontent.com/images/a9cb6fa4-0399-4a04-8239-cdbc38798b82.png)
 