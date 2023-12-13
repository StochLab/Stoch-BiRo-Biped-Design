## Brushless DC Motor

T-Motor Antigravity MN5006 KV300 brushless DC motor is used for each actuation module; therefore in total six motors (3 for each leg). Brushless DC motors provide more torque
per watt of power drawn than brushed motors, thus making them more efficient. Controlling such motors are more efficient as they have better speed vs. torque characteristics and faster
dynamic response. KV300 here indicates the motor performs 300 revolutions per minute (RPM) per Volt that is given as input. 

<div class="tg-wrap" align="center"><table><thead><tr><th colspan="2">Motor Specifications</th></tr></thead><tbody><tr align = "center"><td>Motor Size</td><td>55.6mm * 30mm (OD * Width)</td></tr><tr align = "center"><td>Shaft Diameter</td><td>6mm</td></tr><tr align = "center"><td>KV</td><td>300</td></tr><tr align = "center"><td>Motor Weight</td><td>108g</td></tr><tr align = "center"><td>Peak Current (180s)</td><td>20A</td></tr><tr align = "center"><td>Maximum Power (180s)</td><td>500W</td></tr><tr align = "center"><td>Maximum Torque</td><td>0.5 N-m</td></tr></tbody></table></div>

|<img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/Motor.jpg" width="330"/> |  <img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/Motor2.jpg" width="330"/>  | 
|:------:|:------:|
|Front View|Rear View|

## Motor Driver

Mjbots' Moteus r4.11 driver controls the motor inputs. The Moteus controller is intended to drive 3-phase brushless motors using field-oriented control (FOC). It contains
three half-H bridges to switch power to each of the three phases, a built-in magnetic encoder to measure the rotor position, and current sensing capabilities on each of the three phases.
A magnet is attached to the shaft, part of the motor coupling. As the magnet rotates, the absolute magnetic encoder in the moteus driver records rotation by measuring the magnetic flux
density using the Hall Effect principle. The magnetic encoder provides essential feedback for maintaining precise control over the motor’s position, speed, and torque. By leveraging this
data, the Moteus driver ensures smooth and efficient operation of the brushless motor, enabling optimal performance in various applications. The magnetic encoder is seen as a black chip in
the center of the driver’s rearview. 

<div class="tg-wrap" align="center"><table><thead><tr><th colspan="2">Moteus r4.11 Driver Specifications</th></tr></thead><tbody><tr align="center"><td>Peak Phase Current</td><td>100A</td></tr><tr align="center"><td>Voltage Input</td><td>10-44V</td></tr><tr align="center"><td>KV</td><td>300</td></tr><tr align="center"><td>Temperature</td><td>-40 to 85 deg C</td></tr><tr align="center"><td>Peak Electrical Power</td><td>500W</td></tr><tr align="center"><td>Control Rate</td><td>15 - 30 kHz</td></tr></tbody></table></div>

|<img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/moteus.jpg" width="330"/> |  <img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/moteus2.jpg" width="330"/>  | 
|:------:|:------:|
|Front View|Rear View|

## Inertial Measurement Unit (IMU)

An inertial measurement unit (IMU) collects and outputs accelerometer, gyroscope, and magnetometer data, fully synchronized and calibrated. The IMU used in the biped is Xsens MTi-610 IMU. It is mounted on the torso plate to estimate the robot's position and orientation, or in other words, motion tracking. To facilitate seamless communication between the IMU and the robot's control systems, a Raspberry Pi serves as the intermediary, connecting the IMU via the Controller Area Network (CAN) protocol. This protocol ensures reliable and efficient data transmission, enabling real-time updates and integration of the IMU data into the robot's overall control framework.

|<img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/imu.png" width="330"/> |  <img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/pdb.jpg" width="330"/>  | 
|:------:|:------:|
|Xsens MTi-610 IMU|PDB|

## Power Distribution Board (PDB)

A power distribution board (PDB) is an important part of an electricity supply system. Its job is to split an incoming electrical power feed into multiple secondary or subsidiary circuits. When the motors start running, it draws a large amount of current from the battery, resulting in a large voltage drop across the connecting wires (wires are low ohmage resistors). This will cause the other electronics to face a large current drop. Here is where the power distribution board plays its role. 

The biped uses the MJBOTS r4.3b version of PDB. It incorporates pre-charging capabilities, energy monitoring functionality, and over-current protection mechanisms. These features contribute to a smoother power transition and prevent excessive current from negatively affecting other electronics. Furthermore, the PDB is equipped with a soft power switch, enabling convenient control over the power supply to the biped. It also facilitates power connector fanout, allowing for efficient power distribution to various subsystems and components. To enhance monitoring and control capabilities, the PDB integrates a CAN-FD port. This enables the host software to continuously monitor the state of the switch, input voltage, power, and energy levels. Additionally, it allows the software to request a "soft power down" to initiate a delayed shutdown, ensuring a controlled and orderly power-off process. Overall, the MJBOTS r4.3b PDB offers comprehensive functionality and protection measures, ensuring reliable power distribution and efficient management of the biped's electrical system.

## RPi \+ Pi3Hat

### Raspberry Pi

Raspberry Pi microcontroller is a type of single-board computer (SBC), meaning that its entire hardware set is placed on a single electronics board. It is unable to replace or add components because there are no CPU sockets, memory slots, or expansion buses like PCIe. A Raspberry Pi's board includes a CPU, RAM, LAN, USB, and micro HDMI connectors, as well as a micro SD card slot. Raspberry Pi is used to receive the data from the IMU in the biped and accordingly provide the motor inputs to the motor drivers.  

By acting as an interface between the IMU and the motor drivers, the Raspberry Pi enables the biped to effectively process the IMU data and translate it into appropriate motor commands. This facilitates precise control over the robot's movements and helps maintain stability and balance during operation. The compact size, versatile connectivity options, and ability to run various software platforms make the Raspberry Pi an ideal choice for integrating into the biped robot system. Its capability to handle data from the IMU and drive the motor drivers plays a crucial role in ensuring the biped's motion control and overall functionality.

### Pi3Hat

MJBOTS Pi3hat is a daughterboard for a Raspberry Pi, which provides a power input ranging from 8-44V, 5V for Raspberry Pi, and independent 5Mbps CAN-FD buses. Attaching the Pi3hat to the Raspberry Pi GPIO header will provide power input capabilities and facilitate communication interfaces (CAN-FD protocol is used for the biped) to make the robot control easier. It attaches to the Raspberry Pi's GPIO header and presents as a registered hat.

One of the notable features of the Pi3hat is its inclusion of independent 5Mbps CAN-FD buses. These CAN-FD buses serve as communication channels, utilizing the CAN-FD protocol, specifically employed for the biped application. This allows for seamless data exchange and control between the Raspberry Pi and other components or modules within the robot system. By connecting the Pi3hat to the Raspberry Pi, the Pi3hat effectively becomes a registered hat, tightly integrated with the Raspberry Pi's hardware and software ecosystem. This integration streamlines the overall robot control process, enabling efficient communication and power management, and simplifying the overall system architecture.

|<img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/rpi.jpg" width="330"/> |  <img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/pi3hat.jpg" width="330"/>  | <img src="https://github.com/StochLab/Stoch-BiRo-Biped-Design/blob/main/Images/Electrical%20Components/rpi%2Bpi3hat.jpg" width="330"/> |
|:------:|:------:|:------:|
|Raspberry Pi (RPi)|Pi3Hat|RPi + Pi3Hat|
