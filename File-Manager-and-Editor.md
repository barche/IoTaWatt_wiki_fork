IoTaWatt maintains a file system on the SDcard and also has an integrated web server that can be used to access and manage the files.  The web server is based on the generic [ESPWebserver](https://github.com/esp8266/ESPWebServer) developed by the folks at the ESP8266/Arduino project.  The file manager application is the unmodified application that they distribute.
The major functions are:
* Display file system
* Delete files
* Upload files to the IoTaWatt
* Download files from the IoTaWatt
* Edit files
The File Manager is accessed from the dropdown buttons in the Tools main menu.
![File Manager](https://screenshots.firefoxusercontent.com/images/254d3e23-c8fe-41ae-899c-3d32569ed644.png)
The left column is the file list.  Directories are not expanded but can be by clicking the + sign as in the typical paradigm.
Action can be taken on individual files by right clicking and selecting from the options:
* Edit
* Download
* Delete
Proceed cautiously.  There is no confirmation popup.  Delete is delete now!

Files can be uploaded to the IoTaWatt by clicking the Browse button at the top and selecting a file in the manner provided by your browser.  Once selected, click Upload to transfer the file to the IoTaWatt file system. You can edit the pathname before uploading.  Additional buttons are provided to create a new directory or file.

One of the most powerful features of this app is the editor. It's a version of the open[Ace Editor](https://ace.c9.io/) and is very fast and capable.  It's not particularly useful on mobile devices, but does very well on a keyboard equipped browser.  You will need to learn the keyboard shortcuts, but even with just a few of the usual suspects, you can be very productive (ctrl-S save, ctrl-Z undo, ctrl-F find, etc.)

The IoTaWatt configuration app was developed exclusively using this editor and the IoTaWatt firmware file manager. In fact, that's the file that appears in the editor window when you start the file manager app.
 