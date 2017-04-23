As a standalone unit, IoTaWatt is a very capable data logger with an integrated web server/API interface that can provide real-time as well as historical data to any web connected client. That said, there are limitations in that a typical historic query has about a 4 second response time and the web server currently only works with locally connected clients on the same WiFi network.

There are services available that will store uploaded data logger information and present that data to client applications across the internet.  IoTaWatt has the capability to upload its data to those servers while still maintaining all of its own local logging and reporting capabilities.

One such service is emoncms.org which runs an open-source system to save time-series data and has multiple reporting apps developed by them and contributed by users in the open community.  The graph application used locally by IoTaWatt is a fork of that effort.

Configuring an IoTaWatt to upload to emoncms.org is easy.  First, go to emoncms.org and establish an account.  As of this writing, there is no cost to use the service.

After establishing an account, run the IoTaWatt configuration application and select "Setup Web Server".

![Config Web Server](http://iotawatt.com/Images/Config_emoncms_1.png)

Currently there are two choices, "none" and "emoncms".  Choose emoncms. 

![Config emoncms](http://iotawatt.com/Images/Config_emoncms_2.png)

Here you will specify how IoTaWatt is to upload its data to emoncms. 

**Node** is the grouping that you want to assign to all data upload from this IoTaWatt to distinguish it from data uploaded from any other devices that you may have.  It is somewhat arbitrary.

**post interval** is the number of seconds that each data point will represent. The tradeoff is between higher resolution (small interval) and storage requirement of the overall data over time (larger interval). IoTaWatt accepts any value from 5 seconds to 3600 seconds (1 hour), in 5 second increments.

**bulk send** is the number of interval postings to aggregate into a single posting request. Specifying 1 will send a data packet to emoncms at each interval.  If your interval is 5 or 10, it will send a packet every 5 or 10 seconds.  That's fairly inefficient and can be problematic when there are internet connectivity issues. By specifying a larger bulk send, IoTaWatt will aggregate the posting data for that many intervals and send the data in one packet. For instance if your interval is 10 seconds, specifying bulk send = 3 will cause data to be sent every 30 seconds. Large bulk send values will cause any real-time dashboards in emoncms to update less frequently.

IoTaWatt has all the data in local storage, so there is no risk of losing data by using this feature. Should there be any failure to deliver, IoTaWatt will pick up with the last successful posting when the problem resolves itself.

**server URL** This is the URL of the emoncms.org server to upload to.  It defaults to the emoncms.org website, but the software is open, so you may maintain your own server (software on GitHub) or you may buy one of the OpenEnergy.org products that run a version of the software on a raspberry-pi.

**api key** emoncms requires a 32 character hexadecimal key to authorize posting to an account.  Once you establish your account, locate the read-write api key and copy/paste of type it in to this field.

Now click "Save" and IoTaWatt should begin sending data to your emoncms account.  To discontinue logging, deconfigure emoncms by selecting "none" in Web Service Type.

IoTaWatt uploads the current voltage or power corresponding to all of the input channels in each post. You will configure emoncms (follow their instructions on the emoncms website) to save only what you want to keep in "feeds".  Setting up and configuring the emoncms account is well documented on the emoncms.org site.


