---
title: Schematic
---

## Overview

This schematic is design to support a water-quality monitoring system. This subsystem functions as a user interface, supporting up to 4 sensor boards to be added to it. It features a speaker to alert the user of dangerous levels, as well as a screen and button interface. 

**Figure 1:** Controller subsystem schematic.

![schematic](IndividualSubsystemImage.png)

## Requirements Compliance
The schematic as shown fully satisfies user needs and product requirements as following:
* The user need of an easy-to-use interface is satisfied by the 4-button interface. Many users will be familiar with this kind of interface, as it is found on many devices such as smart appliances, cars, computers, and ATMs. 
* The large LCD screen offers an easily readable way of displaying the sensor values to an untrained user, showing both the current value and the expected safe thresholds on the screen at once.
* The RC filters connected to each button satisfy project requirements of debouncing all buttons. The pull-up configuration of the buttons serves the purpose of working with the PIC18F's requirement to not leave connected I/O pins floating.
* The speaker and drive circuit fulfills the project goals of having an actuator, as well as performing a digital-to-analog signal conversion with the PIC18F microcontroller.
* The headers conform to the standard shared by all of our team boards, and faciliate inter-device communication, a project requirement.
* The two power supplies fulfill the project requirements of the subsystem being operatable off a 9V unregulated power supply.
* The LEDS on the headers fulfill the project requirements of having debugging LEDs.
* The extra button circuit fulfills the project requirement of having a dedicated debugging button.
* The test points placed throughout the circuit fulfill the project requirement of having test points built in.

## Design Process

| Element | Design Process |
| :---- | :---- |
| MCU pin assignments | Allocated by datasheet |
| 8-pin header pin assignments | Project specification |
| Switch pull-up resistors | From my research, the pull-up size can be within an  acceptable range and min and max size can be calculated with the current and capacitance of the MCU pins. If the MCU is not especially sensitive, 10k is a generally accepted standard for 5V microcontrollers. |
| Debouncing low-pass filter (RC) | Using the relationship debouncetime \= 5RC, and an arbitrary debounce of 10 ms (assumed to be a reasonable time for a human to make a confident input without becoming annoying), and a capacitor value of 0.1 uF to keep physical size down, I calculated a 20kOhm resistor would be suitable. |
| LCD header pin assignments | Pins allocated by datasheet. A level shifter is used to translate the 5V logic from the PIC to the 3.3V logic required by the LCD controller daughterboard. |
| Speaker design | Design from in-class lab updated with datasheet for specific speaker used. A voltage divider was added to better suit the speaker's frequency-voltage chart. |
| Power supplies | Basic design from datasheets. A second 5V input with a diode and fuse was added to the 3.3V regulator to allow functioning when being powered by another subsystem. The diodes and fuse are to prevent the 9V supply from being connected to the 5V rail. |

## Resouces

The schematic as a PDF download is available [*here*](IndividualSubsystemPDF.pdf), and the Zip folder of the project [*here*](IndividualSubsystem.zip).

