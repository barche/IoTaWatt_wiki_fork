In this example, a setup for monitoring 14 circuits over 3 phases will be described, combining data from the IoTaWatt and emonPi. The objective is to determine what the main electricity consumers are and to get an idea of how much the heat pump consumes in particular. Data is first uploaded from the IoTaWatt to the emonPi, and then to emoncms.org.

### System to monitor

The idea is to monitor the following circuits, spread over three phases L1, L2 and L3:

| Circuit         | Phase | Monitor  |
| --------------- | ----- | -------- |
| Total input     | L1    | IoTaWatt |
| Total input     | L2    | IoTaWatt |
| Total input     | L3    | IoTaWatt |
| Heat pump       | L1    | IoTaWatt |
| Heat pump       | L2    | IoTaWatt |
| Heat pump       | L3    | IoTaWatt |
| Tumble dryer    | L1    | IoTaWatt |
| Fan             | L1    | IoTaWatt |
| Fridge          | L1    | IoTaWatt |
| Bathroom        | L2    | IoTaWatt |
| Computer        | L2    | IoTaWatt |
| Washing machine | L2    | IoTaWatt |
| TV              | L3    | EmonPi   |
| Dishwasher      | L3    | EmonPi   |

This is on a European three-phase system with a neutral line, so each phase has its voltage with respect to the neutral line (about 230 V), and each of these needs to be measured for maximum accuracy. This means two inputs of the IoTaWatt are occupied for voltage measurements, so to measure all circuits we will complement the measurement with the two emonPi inputs.

### Physical installation

The final connected setup is as follows:

![Connections](https://i.imgur.com/d20CQom.jpg)

For the voltages, each of the plugs is connected to a known phase. Three of the AC/AC adapters connect to the IoTaWatt, while the last one (phase L3) is connected to the emonPi. Currents are measured with the [20 A SCT-006](https://shop.openenergymonitor.com/20a-max-clip-on-current-sensor-ct/) on all circuits, except for the total power where 3 [100 A SCT-013](https://shop.openenergymonitor.com/100a-max-clip-on-current-sensor-ct/) are used. The advantage of the SCT-006 is that it is much smaller and thus easier to fit when there is little space.

### IoTaWatt setup

The setup of the IoTaWatt follows the normal setup tutorial, with **[explicit reference](https://github.com/boblemaire/IoTaWatt/wiki/Configuring-Explicit-Reference)** for the voltages. Each voltage was calibrated using a multimeter. Data is recorded to the local emonPi system using the instructions for [connecting to emoncms](https://github.com/boblemaire/IoTaWatt/wiki/Connecting-to-eMonCMS).

### emonPI setup

The emonPi uses a separate AC/AC adapter to measure the L3 voltage, and two SCT-006 for current measurement. To calibrate the voltage and to use the SCT-006 rather than the supported SCT-013, the following change was needed in the [firmware](https://github.com/openenergymonitor/emonpi/blob/master/firmware/src/src.ino#L89-L91):

```c
const float Ical1=                36.36;                             // (2000 turns / 22 Ohm burden) = 90.9, 800 turns for the SCT-006
const float Ical2=                36.36;
float Vcal_EU=                    249.1;                             // Adjusted to match IoTaWatt calibration
```

To upload the data to emoncms.org, Node-RED seemed the handiest option. By pointing your browser to the emonPi on port 1880 (default login/pass: emonpi, emonpi2016) it is possible to set up data logging using the following Node-RED graph:

![Connections](https://i.imgur.com/JtN7HBG.png)

The timestamp node is of type `inject`, sending a time stamp every 10 s to trigger the upload. Node `allfeeds` is a http request node, requesting all feeds from the local emonpi in one request to `http://localhost/emoncms/feed/list.json?apikey=YOURKEY`. The feeds are then processed using a function node containing the following code:

```javascript
feed_indices = [0, 1 , 2 , 3, 10, 11, 12, 13, 14, 15, 16, 17, 18, 19, 20, 21, 22, 23, 24, 25]
out_msg = {};
out_msg.payload = {};
for (var i in feed_indices) {
  feed = msg.payload[feed_indices[i]];
  out_msg.payload[feed.name] = feed.value;
}
return out_msg;
```
The `feed_indices` vector allows selecting which feeds to upload. Finally, the result is uploaded using an `emoncms` node.

### Results

After logging data for about 1 month, this is the evolution of the error between the official meter and the total power measurement using the IoTaWatt:

![error](https://i.imgur.com/6NQRIoN.png)

Each point represents a direct comparison between a photograph of the meter reading (for accurate timestamping) and the reading at that time from the total power, measured using the IoTaWatt with the SCT-013 right at the meter output. I don't know the reason for the big jump between 11 and 16 Dec, but at the maximum difference the relative error is 1.9 %.

The heat pump is driven by a three phase motor, so to get the total power the sum of the three phases needs to be taken. This is done using an emonPi feed. The logged power on a typical day (in W):

![heatpump](https://i.imgur.com/D4owwa2.png)

The lower peaks are bursts of heating, while the high peak is the heating of the hot water boiler. This is a heat pump using three 90 m deep holes to extract the heat from the soil, with a nominal electrical power of about 1800 W, so the measurement seems to be close to this as far as the heating is concerned. The boiler stresses the pump more, because the required temperature is 47 °C instead of arount 30 °C for heating.

Daily energy usage (in kWh) looks like this:

![dailyenergy](https://i.imgur.com/vaFVWTQ.png)

The yellow bars represent the total energy, the red bar is the heat pump, which is unsurprisingly the biggest consumer. On Jan 16, the second largest contributor was the electric heater in the bathroom, using almost as much energy as the heat pump.

### Conclusion

Overall, the results are very satisfactory. The absolute error with respect to the official meter appears to be fluctuating, so determining the final bound on the error will require collecting data over a longer period. The objective of determining the main energy consumers in the house is attained.