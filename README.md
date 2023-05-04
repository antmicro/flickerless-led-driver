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

## Licensing

This project is published under the [Apache-2.0](LICENSE) license.
