# Design of Stoch BiRo Biped

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Master%20Assembly%20(Rear%20View).png" width="350"><br>
  <strong>Stoch BiRo</strong>
</div>

## Torso

The torso consists of two L-shaped aluminum plates bolted together. These plates have provisions to mount electronics such as the Power Distribution Board, Raspberry Pi + Pi3Hat, and Xsens MTi-610 IMU. 

## 3 DOF Biped Leg

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Master%20Assembly.jpg" width="350">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Master%20Assembly%20(Exploded%20View).jpg" width="350">  
</div>

The hip actuator modules for both legs are mirrored versions of each other. 

Internal components of the actuator modules are described here: 

* [Mechanical Components](https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Mechanical%20components.md)
* [Electrical Components](https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Electrical%20Components.md)

**NOTE:** *The components in the actuation modules are denoted in the images below as follows:*

<div class="tg-wrap" align="center"><table align="center" style="margin: 0px auto;"><tbody><tr align="center"><td><strong>A.</strong></td><td><strong>B.</strong></td><td><strong>C.</strong></td><td><strong>D.</strong></td><td><strong>E.</strong></td><td><strong>F.</strong></td></tr><tr align = "center"><td>T-Motor Antigravity MN5006 BLDC Motor</td><td>Motor coupling</td><td>Stage-I HTD Pulley (13 Teeth)</td><td>MJBOTS Moteus r4.11 driver</td><td>HTD Timing Belts</td><td>Stage-II HTD Pulley (13 Teeth)</td></tr><tr align="center"><td><strong>G.</strong></td><td><strong>H.</strong></td><td><strong>I.</strong></td><td><strong>J.</strong></td><td><strong>K.</strong></td></tr><tr align = "center"><td>Stage-I HTD Pulley (39 Teeth)</td><td>Roller Tensioners</td><td>Stage-II HTD Pulley (39 Teeth)</td><td>Joint coupling</td><td> Hip-to-hip attachment</td></tr></tbody></table></div>


### Abduction Module

The abduction module is the topmost module of a leg in the biped. It is responsible for the abduction and adduction movement of the robot's hip, similar to that of humans. The module is attached to the torso plate and the motor drives the belts and pulleys with the output pulley attached to the abduction-flexion coupling. This coupling is a part of the abduction joint, which connects the abduction and the flexion modules. Tensioners are provided to prevent any slack in the timing belts while running.

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Abduction%20(White).jpg" width="350"><br>
  <strong>Abduction Module</strong>
</div>

### Hip Flexion Module

The hip flexion module is placed between the hip abduction and thigh modules. This module is similar to that of the abduction module with few changes. It performs the flexion-extension motion. The motion of this module is controlled by the abduction motor and the motor in the flexion module controls the flexion joint, which connects the flexion and thigh modules. This module consists of a hip-to-hip attachment and the abduction-flexion coupling in the abduction module is fastened to it during assembly for transmitting the motion. The output pulley is connected to a flexion-thigh coupling. This coupling forms the flexion joint, which connects the flexion and thigh modules.

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Hip.jpg" width="350"><br>
  <strong>Hip Flexion Module</strong>
</div>

### Thigh Module

The thigh module is responsible for the knee motion of the biped, similar to the primary movement of human knees. The flexion joint controls the movement of this module. The motor of the thigh module, together with the dual-stage reduction using belts and pulleys, controls the knee joint. The thigh joint comprises a thigh-shank coupling, which is the same as that of the flexion-thigh coupling. The output pulley is attached to this coupling and the motion is transmitted to the shank module. Unlike the previous two modules which had a triangular configuration, the belts of this module are arranged linearly.

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Thigh.jpg" width="350"><br>
  <strong>Thigh Module</strong>
</div>

### Shank

As the name suggests, the shank is the lowest part of the biped leg, which runs from the knee to the foot. The motor of the thigh controls its movement at the knee joint. A single-point contact foot made of polyurethane (PU) is attached to the end of the shank for better grip of the biped when in contact with a surface. This module is similar to the structure of the thigh but without any of the actuating components (motors, belts, pulleys, etc.) and with a provision for foot attachment at its bottom end.

<div align="center">
  <img src="https://github.com/Karthik-Rajgopal/Stoch-BiRo-Biped-Design/blob/main/Images/Assembly%20files/Shank.png" width="150"><br>
  <strong>Shank</strong>
</div>


