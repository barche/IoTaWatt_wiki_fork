As a standalone unit, IoTaWatt is a very capable data logger with an integrated web server/API interface that can provide real-time as well as historical data to any web connected client. That said, there are limitations in that queries can take up to 4 seconds and the web server currently only works with locally connected clients on the same WiFi network. There is also a chance that the local datalogs can be lost along with all of the accumulated history.

There are services available that will store uploaded data logger information and present that data to client applications across the internet. IoTaWatt has the capability to upload its data to those servers while still maintaining all of its own local logging and reporting capabilities.

As of this writing, IotaWatt supports two such web based services: Emoncms and influxDB.  They are described in more detail on their respective pages that follow.  Additionally, support for reporting data via MQTT, is anticipated in the near future.  MQTT can be used to report data to a variety of different subscribers, individually or collectively.

To initiate configuration of any web server, select the Setup Web Server tab and select the particular server you would like to use from the dropdown list. If you previously configured a web service and wish to discontinue reporting there, select NONE from the list.
