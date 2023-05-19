# OSRAM LZ1 LuxiGen LED driver

Copyright (c) 2023 [Antmicro](https://www.antmicro.com) 


## Overview 

This project contains open hardware design files for a PCB supporting a pair of LEDs in LZ1 LuxiGen package from OSRAM.
The PCB includes a flickerless LED driver allowing to adjust LED brightness with a potentiometer.
This design can be easily adopted to other LEDs and eventually can become a custom LED driver providing precise lighting for machine vision applications.

The design files were prepared in KiCad 6.x.

# Key features 

* LED current driver implemented with MPS/MP2483DQ-LF-P
* Designed for a pair of LZ1-00R802-0000
* Can be daisy-chained with multiple LEDs driven with a single driver

## Project structure

The main directory contains KiCad PCB project files, a LICENSE, and a README.
The remaining files are stored in the following directories:

* `lib` - contains the component libraries
* `img` - contains graphics for this README

## Usage

The project contains one PCB that can be configured as a primary or a secondary. 
It is designed to be powered with 12V DC using a barrel jack. It was tested on the highest britgness settings in a chain of 3 boards with a digital microscope as load on USB-C, the current in a circuit was around 1A. 

**Primary board** 

It's the board that contains the LED driver, all the connectors and a potentiometer. 

There are 3 connectors on the primary board: 
* USB-C - outputs 5V without data transfer, only to power some additional device, i.e. a microscope or a camera
* A barrel jack to power the whole circuit wih 12V
* A 2-pin JST connector - to daisy chain boards with diodes in serial connection 

A rotary potentiometer is the element that provides control of diode brightness using the LED driver. 

**Secondary board** 

It only contains the LZ1 diodes, 2-pin connectors and resistors marked as secondary DP (R10 and R7). It is powered and controlled by the primary board through JST connectors. 


> **Single board circuit** 
> To configure the primary board as a standalone, mount the R7 Debug jumper in addition to R11. 

> **Multiboard circuit** 
> To daisy chain the boards R7 CAN NOT be populated on primary board and must be populated on secondary boards. C_out of one board must be connected to A_in of another one. The design was made for 3 boards in a chain. To connect more boards higher voltage and possibly changing some passives will be required. 



## Licensing

This project is published under the [Apache-2.0](LICENSE) license.
