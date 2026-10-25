---
title: Software Proposal
---

## Introduction

The software for this project is developed using **MPLAB X IDE**, **MCC Melody**, and the **XC8 compiler** for the PIC18F57Q43 Curiosity Nano. MCC Melody is used to configure the microcontroller peripherals, including PWM, UART, timers, and GPIO. The main controller uses **two independent full-duplex asynchronous UART serial communication links**, configured for **9600 baud, 8 data bits, no parity, and 1 stop bit (8-N-1)**. The temperature-controller interface uses **UART3**, with **RA3 as TX and RA4 as RX**, while the ambient-light-controller interface uses **UART1**, with **RC2 as TX and RC3 as RX**. Each remote board has its own power supply, but all boards must share a **common ground** for the UART signals to operate correctly.

The **temperature board** is expected to measure and process the ambient temperature and transmit the resulting temperature in degrees Fahrenheit to the main board using the message format `T,###`, terminated with carriage-return/line-feed characters. For example, `T,72\r\n` represents 72°F. The main board interprets this value to control two temperature indicator LEDs: both LEDs are off below 32°F, LED 1 is on from 32°F through 99°F, and both LEDs are on at 100°F or above.

The **ambient-light board** is expected to measure the room's light level, convert it to a digital scale from **1 to 100**, and transmit it to the main board using the format `L,###`, also terminated with carriage-return/line-feed characters. For example, `L,37\r\n` represents an ambient-light level of 37. When the received light level is below 50, the main controller permits operation of the RGB LED array. At a light level of 50 or greater, the RGB array is disabled.

The main controller uses hardware **PWM outputs** to control five MOSFET-driven LED banks, allowing adjustment of brightness, color mixing, gradual color transitions, and preset lighting patterns. Three push buttons provide user control of brightness, static color, and preset operating mode. A standalone software test mode is also included so simulated temperature and ambient-light values can be used to test the main controller independently before the two remote sensor boards are connected.
