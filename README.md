# Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED
Introducing  NCD’s Long Range IoT Industrial wireless vibration and temperature sensor, boasting up to a 2-mile range the use of a wi-fi mesh networking structure. Incorporating a precision 16-bit vibration and temperature sensor, this device transmits incredibly accurate vibration and temperature records at consumer-described durations.

![alt tag](https://github.com/rjrajbir/Node-red-with-Temperature-and-Vibration-Sensor/blob/master/Vibration-Sensor-Zigmo.png)

 For the duration of Power-Up, this vibration sensor learns “normal” base-line vibration from the monitored device. This base-line vibration is subtracted from regular sampled vibration readings to improve applicable vibration data. Preferably, the monitored device must be off even as the sensor is mastering. Once the sensor stabilizes and starts sending information, the device/equipment being monitored can be powered on. This business IoT wireless vibration sensor samples 3-axis of vibration data for 100ms after which calculate RMS, maximum, and minimal vibration readings. This sensor combines these records with temperature data in a data packet and transmits the result to modems and gateways in the wi-fi variety. Once the transmission is complete, the vibration sensor is going lower back to sleep, therefore minimizing power consumption. 

Powered by using just 2 AA batteries and operational life of 500,000 wireless transmissions, a ten years battery life can be expected relying on environmental conditions and the data transmission interval. Optionally, this sensor may be externally powered, making it a perfect choice for wireless vibration monitoring device for industrial equipment. With an open communication protocol, this sensor transmits hardware-encrypted data that may be included with just about any control system or gateway. Data can be transmitted to a laptop, a raspberry pi, to Losant IoT cloud, microsoft® azure® IoT, and an embedded gadget all at the equal time. Sensor parameters and wireless transmission settings can be modified using labview® tracking software on a computer pc.

![alt tag](https://github.com/rjrajbir/Node-red-with-Temperature-and-Vibration-Sensor/blob/master/Vibration-Temp-Sensor.png)

# Long Range Wireless Mesh Modem with USB Interface
![alt tag](https://github.com/rjrajbir/Node-red-with-Temperature-and-Vibration-Sensor/blob/master/Zigmo.png)

**Resources Required**
- [IoT Long Range Wireless Vibration and Temperature Sensor](https://store.ncd.io/product/iot-long-range-wireless-vibration-and-temperature-sensor/) with power source Battery Or External DC.
- [Zigmo/Router for PC](https://store.ncd.io/product/900hp-s3b-long-range-wireless-mesh-modem-with-usb-interface/)
- PC/Laptop with an OS installed or Any IoT Embedded Device

# Setting up XAMPP

XAMPP is most prevailing, free an open source cross-platform which is one solution to run your web services. XAMPP is developed by ApacheFriends which released in May 2002. XAMPP Stands for Cross Platform(X), Apache(A), MySQL(M) also Sometimes (M) refers to MariaDB, PHP(P) and Pearl(P).

xampp allows you to work on a local server and test a local copies of websites using PHP code and MySQL databases. Once xampp is active, you can access your local copy with a browser using an url like 
http://localhost/ or http://127.0.0.1/

**Downloading and Installing XAMPP**

Go to [XAMPP](https://www.apachefriends.org/download.html) web site and download the installer based on your operating system. Installation should be similar to a normal software installation you do in your operating system.

When installing, there would be an option to select whether you want to run Apache and MySQL as services. If you chose it, Apache and MySQL will start at system boot-up which may not need if your computer is tight with memory resources or if you are not doing PHP development frequently. You can change these settings after installation.

**Starting Apache and MySQL**

- **Go to the location where you installed XAMPP (usually C:\Program Files\xampp) and double click on XAMPP Control Panel (xampp-control.exe). This will bring you following screen. Click on Start buttons next to Apache and MySQL for starting them.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xammp_start.JPG)

- **Now open up your browser and type http://localhost/ or http://127.0.0.1/**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/google_local_host.JPG)

- **This will open up a following page. Click on the phpMyAdmin.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step1.JPG)

- **This will bring you following screen. Now click on the "New" button as shown in the picture below to create a new database.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step2.JPG)

- **Now create new database as shown in the picture below.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step3.JPG)

- **Now create a table to visualize data as shown in the picture below.**

![alt tag](https://github.com/rjrajbir/Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED/blob/master/xampp_step4.JPG)

- **Now name the first column as "id".**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step5.JPG)

- **Now scroll to the right side of the screen you will see "A_I Comments" i.e. Auto Increments and it is used setting primary key which uniquely identifies each record within table. Click on the checkbox below it.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step6.JPG)

- **This will bring you following screen. Now click on the "Go" button.**

![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/xampp_step7.JPG)

- **Now enter the values of other columns Name = rms_x, Type = DECIMAL, Length/Values = 10,2(i.e upto 2 decimal points) and simillarly for all other values and in the last column you can show created time and click on the save button as shown in the picture below.**

![alt tag](https://github.com/rjrajbir/Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED/blob/master/xampp_step8.JPG)

- **Now click on your database name to expand it and it will show your table name, then click on it to view how data is shown, as shown in the picture below.**

![alt tag](https://github.com/rjrajbir/Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED/blob/master/xampp_step9.JPG)

![alt tag](https://github.com/rjrajbir/Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED/blob/master/xampp_step10.JPG)

That's all with the setting up of XAMPP.

# Setting up Node-Red.
The sensor and Zigmo/Router come pre-programmed and work out of the box. In this section we will setup a sensor and Zigmo link and start receiving data on our PC
# Steps to install NODE-RED
Now that you have sensors running, we need a way to do something useful with that data.
- First of all you'll have to install [Node-RED](https://nodered.org/docs/getting-started/installation). 
- Once that’s done, you’ll need to enter your command line, or Power Shell for Windows users, navigate to the directory Node-RED is installed in.
- Now type **“npm i ncd-red-wireless node-red-dashboard“**. This will install the nodes required to receive data from your wireless sensors and you can start Node-RED once this is done.
- To start node server write **node-red** in the command prompt or terminal and press enter.

# Setting up the nodes
Assuming at this point you’ve started up Node-RED, you should be able to open a browser and navigate to http://localhost:1880, this will open up the flow builder that is the heart of the Node-RED experience.

**Steps to build the flow**

- **At this point you’ll be viewing a large blank flow with a long list of nodes on the left hand side, this sidebar is called the palette.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/blankpage.JPG)

- **Go ahead and drag a Wireless Gateway node over to your flow canvas to get started.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step1.JPG)

- **ncd-red-wireless**
Provides the nodes that manage the serial connection, parse incoming sensor data, filter it by specific parameters, and allow you to configure the wireless sensors.

# Finding your wireless sensors
Once you’ve added the node you’ll be able to view the info tab, which contains information about the node’s functionality, this tab is well populated for most node-red packages and contains valuable information, many times you will not need to view any other documentation outside of the info tab, so keep it in mind while you are building your flows if you have a question about how a node works. The next thing we need to do is configure the node, when you first add it you’ll notice that there is a small triangle on the top right corner next to a blue dot, the triangle indicates that the node needs additional configuration, the blue dot indicates that the node has not yet been deployed as part of the flow.

- **Double click on the node to open up the configuration options.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step2.JPG)

- **Click on the pencil icon next to the Serial Device field to configure your USB router, this will open a second configuration panel that only has a few options.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step3.JPG)

- **Click on the magnifying glass next to the Serial Port field and select the port that corresponds with your router, then click the “Add” button on top. The Serial Device field will now be populated based on that selection, and you can click “Done”, you now have direct access to your wireless sensors! To view the data coming in.**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/gateway%20step4.JPG)

- **Now go back to your palette and type “debug” into the search field at the top, grab one of these nodes and drag it to the right of your Wireless Gateway**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug%20step1.JPG)

- **Double click on it and change “msg.” to “complete msg object” click done**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug%20step2.JPG)

- **Now draw a line between the two nodes, and click “Deploy” on the top right of the window..**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/deploy.JPG)

# Working with the data
Now out of your wireless sensors data is gathered and it is output to the “debug” tab, this "debug tab" is placed within the right sidebar subsequent to the information tab. To see the information are available in to hit the reset button. In node-red records is surpassed among nodes in a json packet. When the msg object comes into the debug tab you may make bigger it to view the overall list of information that comes with it. This is extraordinarily useful in case you need to quickly see which sensors are checking in. The other issue this node gives is a easy way to interchange your router to the network identity that devices in configuration mode document on, simply hit the button on the left of the node and the tool will switch to the configuration network, hit it once more to return it to listening mode. Once we get the wi-fi tool nodes set up, they may be set to routinely configure a sensor whilst it enters configuration mode, so it’s always available to maintain such a gateway nodes present at the flow for speedy configuring a device.

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/GatewayJson.png)

# Adding the wireless sensors
we need to separate wireless sensor records domestically in order that we are able to display it, we could use a switch node to split out the messages from the gateway based totally on the mac address with or sensor type, but as i referred to, the wireless nodes truly incorporate extra functionality for configuring the sensors, so we’ll start with them to give you a extra entire image of how those structures can work. In case you haven’t already seen packets coming in from both of your sensors, cross in advance and hit the reset button on the only that hasn’t stated. While a sensor assessments in thru any serial device configuration node, the mac address and kind of sensor is cached in a pool so we are able to quick find it for the duration of this next step.

- **Grab a Wireless Node from the palette and drag it onto the flow, double click on it to get it configured**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/wirelessdevice%20step1.JPG)

- **select the serial device from the drop down that you used for the Wireless Gateway, now click the magnifying glass next to “Mac Address” and select one of the available options.**

- ![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/wirelessdevice%20step2.JPG)

- ![alt tag](https://github.com/rjrajbir/Wireless-Vibration-and-Temperature-data-to-MySQL-using-Node-RED/blob/master/wirelessdevice%20step3.JPG)

You’ll notice this automatically sets the sensor type for you, you can also give it a name to make it easier to identify. As noted in the info tab, the Serial Device for Config field is optional, and we won’t worry about it right now. The node you have just added effectively works as a filter on incoming sensor data, only passing through data for the mac address, or sensor type if no mac address is present.

- **Now go back to your palette and type “debug” into the search field at the top, grab one of these nodes and drag it to the right of your Wireless Gateway**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug_wirelessdevice_step1.JPG)

- **Double click on it and click done**

![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/debug_wirelessdevice_step2.JPG)

# Adding Function Nodes
The function node is used to run JavaScript code against the msg object. The function node accepts a msg object as input and can return 0 or more message objects as output. This message object must have a payload property (msg.payload), and usually has other properties depending on the proceeding nodes.

- **Now grab a “function” node from the palette, and place it to the right of the Temp/Hum node.**

- ![alt tag](https://github.com/rjrajbir/Creating-Email-Alerts-With-Node-Red-Of-NCD-Wireless-Temperature-and-Humidity-sensor/blob/master/temperature_function_node_step1.JPG)

- **Double click on the node to open up the configuration options.**

Here you have to write little javacript code to create a condition,so the data is sent to the MySQL database. 

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/function_node_step2.JPG)

- **Now you have add "mysql" node to store data, check your palette if it is present there or you can click  on the three bars present right side of deploy button as shown in the picture below**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/Manage_pallette_step1.JPG)

- **Now click on the "Manage palette" button.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/Manage_pallette_step2.JPG)

- **Now search for mysql and click on the 'install' button as shown in the picture.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/Manage_pallette_step3.JPG)

Once its done, you'll see "mysql" node is present in the palette. 

- **Now grab the "mysql" node from the palette and double click on it to open up configuration options.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/MySQL_node_step1.JPG)

- **Write your database name as you created earlier and give a name to it, then click on the pencil icon next to the Database to edit sqldatabase node.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/MySQL_node_step2.JPG)

- **Now add User = root i.e by default in the xampp and password is blank.You can also create user and password enter that here, then enter your database name and time zone(otional) and then click update and done**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/MySQL_node_step3.JPG)

- **Now you'll see your database node shows connected**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/MySQL_node_step4.JPG)

- **Now connect all the wires as shown in the picture.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/Final_wire_Connection.JPG)

- **Now hit the deploy button and you'll database node shows "ok", its means data is sending**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-of-Wireless-Temperature-and-Humidity-Sensor-to-MySQL/blob/master/final_flow.JPG)

# OUTPUT

**Here you can visualize the data coming in.**

- ![alt tag](https://github.com/rjrajbir/Sending-Data-o
