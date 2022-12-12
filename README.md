# Antmicro's open source MPW tester Arty

Copyright (c) 2022 [Antmicro](https://www.antmicro.com)

![MPW tester Arty](/img/arty-mpw-tester.png)

### Overview

This repository contains open hardware design files for a Arty extension created for testing [Caravel](https://github.com/efabless/caravel_board) breakout board.

This development board routes the interfaces from the Caravel and provides the necessary power buses.
The design files were prepared in KiCad 6.

## Repository structure

The main repository directory contains KiCad PCB project files, a [LICENSE](LICENSE), and a README.
The remaining files are stored in the following directories:

* `lib` - contains the KiCad 6 component libraries,
* `doc` - contains generated schematics and other documentation,
* `img` - contains graphics for this README

## Key Features

* Caravel-breakout connector with optional FlexyPins
* Arty A7 chipKIT compatible
* USB for MPRJ SPI/UART debug
* SPI Flash connected to Caravel and Arty
* Dedicated 10MHz oscillator
* Dual LDO with fixed and I2C controlled feedback (selectable)
* 37 MPRJ_IO, clock input, GPIO and reset connected to chipKIT header
* Pin headers for all power rails, reset, clock, UART and SPI Flash

## License

[Apache-2.0](LICENSE)