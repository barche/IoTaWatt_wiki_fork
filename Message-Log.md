The message log is the IoTaWatt's Diary.  It makes notes about various events that occur, both ordinary and unusual.  These messages can be helpful in understanding what is happening with the device, or to provide insight into why something doesn't appear to be working as it should.

The primary method of accessed the message log is by hovering over the Tools main menu button and clicking the Message Log button.  The config utility will cause your browser to download and display the most recent 10000 characters in the log. You can access the entire log by using the [File Manager](https://github.com/boblemaire/IoTaWatt/wiki/File-Manager-and-Editor) app to download the file /iotawatt/iotamsgs.txt and viewing with a text file editor.

With the exception of the first messages after startup, all of the messages in the log will have a data and time stamp.  Messages issued by one of the IoTaWatt Services will begin with the name of the service followed by a colon, as in this message issued from the datalog Service indicating it has successfully started.

`12/23/17 21:57:06 dataLog: service started.`

While it would be impossible to maintain a list of all of the possible messages, the messages issued at startup are pretty straightforward and provide a lot of information.

** Restart **  

No clock yet: SD initialized.  
12/24/17 02:51:16 Real Time Clock is running. Unix time: 1514083876  
12/24/17 02:51:16 Version: 02_02_27  
12/24/17 02:51:16 Reset reason: External System  
12/24/17 02:51:16 Trace:   130,131,132,133,134,135,136,137,138,139,91,84,30,16,13,14,15,30,16,11,90,91,84,86,88,93,94,95,99,12,13,14  
12/24/17 02:51:16 ESP8266 ChipID:428068   
12/23/17 21:51:16 device name: IotaWatt, version: 3
12/23/17 21:51:16 Local time zone: -5  
12/23/17 21:51:18 MDNS responder started  
12/23/17 21:51:18 You can now connect to http://IotaWatt.local  
12/23/17 21:51:18 HTTP server started  
12/23/17 21:51:18 dataLog: service started.  
12/23/17 21:51:19 dataLog: Last log entry:1514083860  
12/23/17 21:51:19 statService: started.  
12/23/17 21:51:19 timeSync: service started.  
12/23/17 21:51:19 WiFi connected. SSID: flyaway, IP: 192.168.1.141  
12/23/17 21:51:19 historyLog: service started.  
12/23/17 21:51:19 historyLog: Last log entry:1514083860  
12/23/17 21:51:23 EmonService: started.url: emoncms.org:80, node: IotaWatt, post interval: 10, not encrypted  
12/23/17 21:51:23 EmonService: Start posting at 1514083700  

## What does it all mean?

`** Restart ** `  Just what you think (JWYT)    
`No clock yet: SD initialized. ` SDcard access has been successfully initialized.  There is no timestamp because the clock is not yet available.  
`12/24/17 02:51:16 Real Time Clock is running. Unix time: 1514083876  ` The real time clock has been detected and the current time is displayed in Unixtime.  
`12/24/17 02:51:16 Version: 02_02_27` JWYT   
`12/24/17 02:51:16 Reset reason: External System` - The reason for the restart. Typically power failure.  
`12/24/17 02:51:16 Trace:   130,131,132,133,134,135,136,137,138,139,91,84,30,16,13,14,15,30,16,11,90,91,84,86,88,93,94,95,99,12,13,14`  
The trace is a diagnostic tool used to narrow down where the firmware was executing at the time of the restart.  Users intent on modifying the firmware for their purposes would do well to understand how this works and how to use it.  
`12/24/17 02:51:16 ESP8266 ChipID:428068` JWYT     
`12/23/17 21:51:16 device name: IotaWatt, version: 3` The device name from the config.txt file.  This is how your IoTaWatt is identified on the network and what you would need to use as a password to change WiFi network.  
`12/23/17 21:51:16 Local time zone: -5` JWYT.   
`12/23/17 21:51:18 MDNS responder started` IoTaWatt uses the multicast DNS protocol on the local LAN (bonjour).    
`12/23/17 21:51:18 You can now connect to http://IotaWatt.local`  This is the name that IoTaWatt uses for mDNS.  
`12/23/17 21:51:18 HTTP server started` The Web Server is initialized.  
`12/23/17 21:51:18 dataLog: service started.` The datalog service makes the 5 second current log entries.  
`12/23/17 21:51:19 dataLog: Last log entry:1514083860` The most recent current log entry prior to the restart.  
`12/23/17 21:51:19 statService: started.` statService maintains the current statistics available via the /status API and used by the Status display in the app.  
`12/23/17 21:51:19 timeSync: service started.` TimeSync periodically checks NTP time and corrects RTC when neccessary.  
`12/23/17 21:51:19 WiFi connected. SSID: flyaway, IP: 192.168.1.141` Informative message, usually delayed slightly.  
`12/23/17 21:51:19 historyLog: service started.` The historyLog service creates and maintains the lower resolution history log.  
`12/23/17 21:51:19 historyLog: Last log entry:1514083860` The most recent entry in the history log prior to restart.  
`12/23/17 21:51:23 EmonService: started.url: emoncms.org:80, node: IotaWatt, post interval: 10, not encrypted` EmonService processes the current log and posts data to Emoncms.   
`12/23/17 21:51:23 EmonService: Start posting at 1514083700` When EmonService starts, the inputs for the specified node are queried and this time of the most recent posting is used as a starting point for sending updates.  


