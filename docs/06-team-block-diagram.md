---
title: Team Block Diagram
---

## Introduction
### The block diagram represents Team 207’s Dorm Room Relaxing Light, a system designed to create a comfortable lighting environment by combining user controls with environmental sensing. Although each subsystem performs a different task, they all use a Microchip PIC18F57Q43 Curiosity Nano microcontroller and communicate through connectors to operate as one complete system. 
### The first subsystem focuses on user interaction and system control. It includes an OLED screen, several buttons, and LEDs. The OLED screen provides information to the user while the buttons allow the user to change or control system settings. The microcontroller uses PWM to control the LEDs, allowing their brightness or lighting behavior to be adjusted.
### The second subsystem focuses on temperature sensing. A temperature sensor measures the surrounding temperature and sends its signal through an operational amplifier before reaching the microcontroller's analog-to-digital converter (ADC). The microcontroller can then interpret the temperature data and use it as part of the lighting system's control.
### The third subsystem focuses on ambient light sensing. A light sensor detects the amount of light in the room and sends the signal through an operational amplifier to the ADC. This allows the system to determine the surrounding light level and potentially adjust the LEDs accordingly.
### Overall, the three subsystems have distinct purposes: user control, temperature measurement, and light measurement. Working together, they allow the relaxing light to respond to both the user's inputs and the surrounding environment, creating a more adaptable and personalized lighting system

## Images

**Figure 1:** Team 207 Block Diagram 
![Team 207 Block Diagram](team207-block-diagram.png)  
[Drawio.com](https://app.diagrams.net/#G1_G6MJIzGkZMXay39FLlBgE4gDPBz6y6s#%7B%22pageId%22%3A%22D7A3hRXi8sjnXgM3Vncy%22%7D)


