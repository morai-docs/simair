# About MORAI SIM: Air
This section explains the concept and features of **MORAI SIM: Air** and the configuration environment.

---

## Concept and Key Features
MORAI SIM: Air is a simulation platform that can verify autonomous flight systems used in various industries such as Urban Air Mobility (UAM), unmanned aerial vehicles (Drones), and light aircraft in a virtual environment.
<br>

MORAI SIM: Air provides a variety of real flight environments as virtual simulations using Digital Twin technology, so the safety of the aircraft can be verified more efficiently and accurately.
And it reporduces actual flight facilities such as vertical take-off and landing facilities (vertiport) and airports for vehicle verification as a digital twin environment, and simulates the actual measurement data provided to the aircraft from each facility as it is. <br>
MORAI SIM: Air virtualizes various sensors and flight dynamics model (FDM) specialized for the aviation industry, and can transmit and receive data in real-time by applying communication such as [ROS2](https://docs.ros.org/en/rolling/index.html) and [UDP](https://en.wikipedia.org/wiki/User_Datagram_Protocol). <Br>

The main features of **MORAI SIM: Air** are as follows.
>  - Provides a simulation environment based on [Unreal Engine](https://en.wikipedia.org/wiki/Unreal_Engine), a physics engine 
  - Supports realistic flight dynamics model (FDM) for [Cirrus SR22](https://sketchfab.com/3d-models/cirrus-sr-22-f0f1089f374f4d398f0483403fe6af7a) and 6 degrees of freedom (DOF) data
  - Supports realistic flight dynamics model (FDM) developed with [JSBSim](https://jsbsim.sourceforge.net/JSBSim/index.html), and 6 degrees of freedom (DOF) data
  - Reproduces weather and time variation with dynamic environment
  - Integration with external sensors and systems: Cameras, GNSS, IMU, RADAR, 3D LiDAR
>  - Supports real-time transmission of flight status messages and sensor data through ROS2 and UDP communication

### Simulation environment based on Unreal Engine
**MORAI SIM: Air** utilizes the physics engine, Unreal Engine to provide a high-fidelity simulation environment for autonomous aerial vehicles, and it can reproduce object movement, physical conditions such as collision and penetration, as well as color and texture realistically.
<br>

The Unreal engine allows for the creation of highly detailed 3D environments and provides a sophisticated physics engine that can simulate the behavior of objects in a realistic manner. This means that the movement of the aerial vehicles, as well as other objects in the simulation environment, are accurately represented.
<br>

Moreover, the Unreal engine can render textures and colors realistically, which helps to create a more immersive simulation experience for users. This allows users to visualize and interact with the simulation environment in a way that closely mirrors the real-world environment, and enables them to test and validate the performance of their autonomous flight systems under realistic conditions.

<figure>
    <img src="../../img/into-duluth.png" alt="sensor">
    <figcaption style="padding-top: 10px;"><b> Figure 1. 3D Simulation environment for Duluth airport provided by MORAI SIM: Air</b></figcaption>
</figure>

### Supports realistic flight dynamics model and 6 DOF
MORAI SIM: Air supports realistic flight dynamics models (FDM) based on [JSBsim](https://jsbsim.sourceforge.net/JSBSim/index.html) for simulation modeling of the behavior of aircraft engines and other systems.<br> 
Additionally, MORAI SIM: Air implements the [Cirrus SR22](https://sketchfab.com/3d-models/cirrus-sr-22-f0f1089f374f4d398f0483403fe6af7a) aircraft model and 6 degrees of freedom (DOF) data, providing a realistic simulation experience.

<video controls>
  <source src="https://user-images.githubusercontent.com/120563672/226307319-c5462e1a-758f-4082-8b03-10d1062bda64.mp4">
</video>
<p style="font-size:16px;"><b> Figure 2. SR22 model with joystick implemented in MORAI SIM: Air</b></p>

### Reproduces weather and time variation with dynamic environment
MORAI SIM: Air also includes a simulation of the environment and weather conditions, which affect the flight behavior and performance of the aerial vehicles. This allows users to test their autonomous flight systems under different conditions and scenarios.

<video controls>
  <source src="https://user-images.githubusercontent.com/120563672/226257559-697af30d-e705-49d4-b930-f26dd60c848d.mp4">
</video>
<p style="font-size:16px;"><b> Figure 3. Reproduced video of weather and time condition changes in MORAI SIM: Air </b></p>

### Integration with external sensors and real-time communication
MORAI SIM: Air supports integration with a variety of external sensors commonly used in autonomous flight systems, including Camera, GNSS, IMU, and RADAR sensors. This enables users to test and validate the integration and performance of their sensors and systems in a virtual environment. <br>

<figure>
    <img src="../../img/Default_Layout_Sensor.png" alt="sensor" title="Click to Enlage" onclick="window.open(this.src)">
    <figcaption style="padding-top: 10px;"><b> Figure 4. Sensor models provided by MORAI SIM: Air</b></figcaption>
</figure>

Also, MORAI SIM: Air supports real-time communication for flight status messages and sensor data using the ROS2 and UDP communication protocols. This enables users to monitor and analyze the performance of their autonomous flight systems during the simulation in real-time.

<figure>
    <img src="../../img/Default_NetworkSettings.png" alt="network" title="Click to Enlage" onclick="window.open(this.src)">
    <figcaption style="padding-top: 10px;"><b> Figure 5. Network settings provided by MORAI SIM: Air </b></figcaption>
</figure>



