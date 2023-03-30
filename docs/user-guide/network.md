# Network Settings
This section describes how to set up the network for communication supported by MORAI SIM: Air.

---

## Supported communication method
MORAI SIM: Air supports UDP and ROS2 for network communication between the simulator and external systems.

[UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol) is a widely used network protocol for transmitting data over the internet, while [ROS2 (Robot Operating System 2)](https://docs.ros.org/en/rolling/index.html) is a popular middleware for robotics and automation applications. <br>
The MORAI SIM: Air simulator allows for sending sensor data and receiving aircraft control messages using either UDP or ROS2 communication methods. 

To communicate with MORAI SIM: Air, <br>
Depending on the simulator's message transmission/reception method, the following network settings are required.

<figure>
    <img src="../../img/network-configure.png" style="width: 1000px; height: auto;" alt="sensor" title="Click to Enlage" onclick="window.open(this.src)">
    <figcaption style="padding-top: 10px;"><b> Figure 1. Network communication method supported by MORAI SIM: Air</b></figcaption>
</figure>

- MORAI SIM: Air sends sensor data to an external system
    1. **UDP Network Settings** in each sensor model in the simulator
    2. Receive UDP messages and publish to ROS2 using **UDP to ROS2 Bridge**

- MORAI SIM: Air receives aircraft control messages from an external system
    1. **UDP Network Settings** provided by the simulator (Subscriber IP/Port setting)
    2. Subscribe to ROS2 messages and them over UDP using **UDP to ROS2 Bridge**

The UDP to ROS2 Bridge serves to connect data between the UDP-based simulator and the ROS2 system by receiving and transmitting UDP signals and issuing and subscribing to ROS2 as shown below.

<figure>
    <img src="../../img/network-ros2bridge.png" style="width: 1000px; height: auto;" alt="sensor" title="Click to Enlage" onclick="window.open(this.src)">
    <figcaption style="padding-top: 10px;"><b> Figure 2. Role of 'UDP to ROS2 Bridge'</b></figcaption>
</figure>

<div markdown="span" class="bs-callout bs-callout-danger">
⚠️  <span class = "dan-calloutTitle"> WARNING </span> <br>
The current simulator does not provide direct support for transmitting/receiving ROS2 messages. Therefore, <b>UDP to ROS2 Bridge</b> should be used for ROS2 communication with an external system.
</div>

## Receiving Aircraft Control Messages
When the simulator receives control messages by ROS2 communication, <br>
Configure the ROS2 to UDP communication environment and set the network of the simulator in the order below.

### Step 1: Subscribe to ROS2 messages

For this step, you need to install and run **UDP to ROS2 Bridge**.

<div markdown="span" class="bs-callout bs-callout-success">
✅ <span class = "suc-calloutTitle"> TIPS </span> <br>See the <a href="https://morai.atlassian.net/wiki/external/1372881223/NzI2NTk2NWU0ODBjNDJmYTkwOGRjZDBiMWEwMmZhMzI">guide</a> provided separately.
</div>

### Step 2: UDP network setting in the simulator
#### 1) Activate the network menu
Click **Network** in the top left menu as shown below.
<img src="../../img/network-setting.png" style="width: 1000px; height: auto;" alt="sensor" title="Click to Enlage" onclick="window.open(this.src)">

#### 2) Configure Host IP/Port
The method of receiving aircraft control messages in the simulator consists of Ghost Mode and External Ctrl protocol.

<div markdown="span" class="bs-callout bs-callout-success">
✅ <span class = "suc-calloutTitle"> TIPS </span> <br>
For the message type and detailed structure received in each Ghost Mode and External Ctrl, see here <a href="https://morai.atlassian.net/wiki/external/1372881223/NzI2NTk2NWU0ODBjNDJmYTkwOGRjZDBiMWEwMmZhMzI">guide</a>
</div>
<br>
Configure the Host IP/Port as below to operate the aircraft in ghost mode by receiving external control messages.

- Host IP: Enter the IP of the host PC running the simulator
- Host Port: Enter the Port of Host PC

Host IP/Port configuration method for External Ctrl protocol is the same as above.

#### 3) Network connection
Click **Connect** at the bottom of each **PROTOCOL_SUB_GHOSTMODE** and **PROTOCOL_SUB_EXTERNALCTRL**. <br>
Then, it enters into a standby state in which a control message can be received.

## Sending Sensor Messages

### Step 1: Senosr network setting in the simulator

#### 1) Place sensors on the aircraft
<div markdown="span" class="bs-callout bs-callout-success">
✅ <span class = "suc-calloutTitle"> TIPS </span> <br>
For details on how to place the sensor, see the sensor setting <a href="https://morai.atlassian.net/wiki/external/1372881223/NzI2NTk2NWU0ODBjNDJmYTkwOGRjZDBiMWEwMmZhMzI">guide</a> part.
</div>

#### 2) Configure Destination IP/Port
Configure Destination IP/Port for UDP network in **Network Settings** at the bottom of the sensor setting window.

<img src="../../img/network-sensor.png" style="width: 500px; height: auto;" alt="sensor" title="Click to Enlage" onclick="window.open(this.src)">

- **Destination IP** and **Port**: 
    - Enter the IP and port of the target server that transmits sensor data in the simulator.
    - In case of ROS2 communication in the server, enter the IP and Port of the server where UDP to ROS2 Bridge is installed.

#### 3) Network connection
Click **Connect** at the bottom of **Network Settings**. <Br>
Then, it enters into a standby state in which sensor messages can be transmitted.

### Step 2: Publishing to ROS2

For this step, you need to install and run **UDP to ROS2 Bridge**.

<div markdown="span" class="bs-callout bs-callout-success">
✅ <span class = "suc-calloutTitle"> TIPS </span> <br>See the <a href="https://morai.atlassian.net/wiki/external/1372881223/NzI2NTk2NWU0ODBjNDJmYTkwOGRjZDBiMWEwMmZhMzI">guide</a> provided separately.
</div>

