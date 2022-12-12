# Arty MPW Tester

Copyright (c) 2022 [Antmicro](https://www.antmicro.com)

![MPW tester Arty](/img/arty-mpw-tester.png)

### Overview

This repository contains open hardware design files for a simple expansion board compatible with [Digilent Arty A7](https://digilent.com/shop/arty-a7-artix-7-fpga-development-board/) development kit.
This board connects IO signals from the Xilinx Artix FPGA located on the Arty board to an open hardware [Caravel](https://github.com/efabless/caravel_board) breakout board.
The Caravel breakout board allows testing ASIC designs fabricated in Multi Project Wafer (MPW) shuttles and fabricated with one of the available open Process Design Kits (PDKs).

You can learn more about Open Shuttle Program by visiting this [link](https://efabless.com/open_shuttle_program).

The Arty MPW Tester board routes the interfaces from Caravel and provides the necessary power buses.
The design files were prepared in KiCad 6. This design is currently a Work in Progress (WiP).

## Repository structure

The main repository directory contains KiCad PCB project files, a [LICENSE](LICENSE), and a README.
The remaining files are stored in the following directories:

* `lib` - contains the KiCad 6 component libraries
* `doc` - contains generated schematics and other documentation
* `img` - contains graphics for this README

## Key features

* Caravel-breakout testbed slot with optional FlexyPins
* Arty A7 chipKIT compatible
* USB for MPRJ SPI/UART debug
* SPI Flash connected to Caravel and Arty
* Dedicated 10MHz oscillator
* Dual LDO with fixed and I2C controlled feedback (selectable)
* 37 MPRJ_IO, clock input, GPIO and reset connected to chipKIT header
* Pin headers for all power rails, reset, clock, UART and SPI Flash

## Licensing

This project is published under the [Apache-2.0](LICENSE) License.
