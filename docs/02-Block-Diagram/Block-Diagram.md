---
title: Module's Block Diagram
tags:
- tag1
- tag2
---

## Overview
Featured on this page is a block diagram for subsystem A2. This subsystem is responsible for being the onboard bluetooth relay, as well as serving as a backup onboard control panel. 
- Power is handled by the shared onboard 9V batteries and the power sharing pins of the 8-pin UART bus connectors.
- Data transmission within the robot is handled through 8-pin UART bus connectors.
- Programming is done via the microUSB interface on the ESP32 microcontroller.
- In order to facilitate remote control, the ESP32's bluetooth low-energy (BLE) module is used to communicate bidirectionally with subsystem A2 to send sensor data and recieve user input data.

## Example Block Diagram 

![A2 block diagram](block-diagram-v2.png)
