# MQTT-Robot-Comm
An MQTT based communication system between mobile robots and a central processing system using an MQTT broker.

## Description
A communication system is put in place for mobile robots to be able to communicate data such as sensor information or actuator information to and from an central processing system.
Message Queuing Telemetry Transport, or MQTT is a popular publish and subscribe type of messaging protocol designed mainly for IoT.

## Project
In this case, the mobile robot running a client node in the MQTT network, senses its environment and has collected some information. Specifically let us assume the robot was running an Object Detection algorithm and had to communicate its findings to the central system. This central system, on receiving the sensor information from the robot, would designate certain trajectories for the robot and communicate the motor and actuator control commands back to the robot.

In doing so, a remote communication network needs to be in place and this is where we implement our project.

The LiDAR data parameters on the robot such as azimuthal angle, distance, sensor info and object detection data is published on a dedicated topic to a MQTT Broker server. The central processing system has subscribed to this very same topic.

Consequently, the central processing system server now publishes motor and actuator control commands on another dedicated topic back to the MQTT Broker, and the robot subscribes to it to receive those control commands.
