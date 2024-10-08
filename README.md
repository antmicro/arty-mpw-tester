# Arty MPW Tester

Copyright (c) 2022-2024 [Antmicro](https://www.antmicro.com)

![MPW tester Arty](/img/arty-mpw-tester.png)

### Overview

This repository contains open hardware design files for a simple expansion board compatible with [Digilent Arty A7](https://digilent.com/shop/arty-a7-artix-7-fpga-development-board/) development kit.
This board connects IO signals from the Xilinx Artix FPGA located on the Arty board to an open hardware [Caravel](https://github.com/efabless/caravel_board) breakout board.
The Caravel breakout board allows testing ASIC designs prepared for Multi Project Wafer (MPW) shuttles and fabricated with one of the available open Process Design Kits (PDKs).

You can learn more about Open Shuttle Program by visiting this [link](https://efabless.com/open_shuttle_program).

The Arty MPW Tester board routes the interfaces from Caravel and provides the necessary power buses.
The design files were prepared in KiCad 7.

## Repository structure

The main repository directory contains KiCad PCB project files, a [LICENSE](LICENSE), and a README.
The remaining files are stored in the following directories:

* `assets` - contains visual assets for showcasing this design on [Open Hardware Portal](https://openhardware.antmicro.com/boards/arty-mpw-tester).
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
