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
- To accomplish the functionality of a backup control system, a simple control panel is used, featuring an 8-button 'subsystem select' panel and a 4-button 'operation' panel that allows an operator to manually select and operate any onboard subsystem in the event of wireless failure/debugging.
- In order to facilitate remote control, the ESP32's bluetooth classic module is used to communicate bidirectionally with subsystem A1 to send sensor data and recieve user input data.

## Example Block Diagram 

![A2 block diagram](block-diagram-v1.png)
