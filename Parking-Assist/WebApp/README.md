# Web Application

For all of the different ESP32 projects I have built so far, it has been helpful to provide a user interface whereby various operating parameters could be set, 
and adjusted over time as needed. A general approach was developed, involving:

*	A browser-based user interface written in (of course) Javascript and HTML/CSS.

*	Use of Websockets to communicate between the project and the browser.

*	The ESP32 discovers and connects to the home network in station mode, sets up an mDNS identifier for TCP/IP, and then opens a WebSocket interface.

*	Parameters are represented by an array of up to 30 unsigned 32-bit integers.

*	The web application uses the mDNS ID to establish a WebSocket connection, then queries the project to retrieve the values of all parameters.

*	The ESP32 saves all parameters in nonvolatile storage (NVS).

*	Changes to any parameter are delivered immediately via the Websocket interface and saved in the ESP32 in NVS.

*	The set of parameters and definitions for the project are defined in a JSON document opened by the web application.

Note: because it loads a local JSON file, the web application must be served from a web server on your network rather than being executed as a file on 
the local computer (that is, unless you run the browser with “same origin policy” disabled). 
Otherwise you might see this kind of error in the JavaScript console: 

```Access to XMLHttpRequest at 'file:///C:/Users/ … /projectName.json' from origin 'null' has been blocked by CORS policy: Cross origin requests are only supported for protocol schemes: http, data, chrome, chrome-extension, chrome-untrusted, https.```

