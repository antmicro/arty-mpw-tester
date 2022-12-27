# Arty MPW tester

```{image} ../img/arty-mpw-tester.png
```
&nbsp;

The Arty MPW tester is simple expansion board compatible with Digilent Arty A7 development kit. This board connects IO signals from the Xilinx Artix FPGA located on the Arty board to an open hardware Caravel breakout board. The Caravel breakout board allows testing ASIC designs prepared for Multi Project Wafer (MPW) shuttles and fabricated with one of the available open Process Design Kits (PDKs).

The hardware is open and can be found on GitHub:
<https://github.com/antmicro/arty-mpw-tester/>

The following instructions explain how to set up the board.

## Arty MPW tester configuration

Arty MPW tester was designed to give user flexibility in configuration of the tester.

User can independently configure:

- Power
- FTDI to MPRJ UART connection (enable/disable)
- Source for Caravel-breakout XCLK (internal oscillator / Arty IO42 pin)
- Internal XCLK source (enable/disable)

### Power

The Arty MPW tester can be supplied either from Arty or USB connector. 

Both power sources are always connected to the dual LDO via protection diodes. 

User can decide to short USB 5V and Arty 5V rails. This allows to supply Arty and Arty MPW tester from single USB-C connector.

```{note}
This should be done only to supply Arty from Arty MPW tester.

When slide switch connecting Arty 5V rail to USB 5V rail is enabled only one USB should be connected: USB on Arty or USB on Arty MPW tester.
```

The Arty MPW tester features dual LDO supplying 1.8V and 3.3V rails.
Each rail can be set to either:

- fixed, supplying fixed 1.8V or 3.3V depending on rail
- dynamic, allowing user set LDO voltage using I2C digipot

Power can be configured using following jumpers and slide switches.

It allows for switching between fixed 1.8V and 3.3V power supplies

### UART

### XCLK

Clock supplied to the Caravel breakout can be sourced from two inputs:

- Arty MPW tester builtin 10MHz clock (internal)doc/conf.pyon the Arty MPW tester.

## Default configuration

Before plugging USB to Arty MPW Tester or Arty board make sure that configuration jumpers and switches are set correctly.

Default configuration for the Arty MPW tester is as follows:

| Setting           | Slide switch  | Jumper    |
|-------------------|---------------|-----------|
| 1.8V LDO    	    |        	    | Fixed     |
| 3.3V LDO    	    |       	    | Fixed     |
| LDO CTRL    	    | ARTY  	    |           |
| VCC 1.8V D  	    |    	        |   YES     |
| VCC 1.8V D1 	    |    	        |   YES     |
| VCC 1.8V D2 	    |    	        |   YES     |
| VDD 3.3V A  	    |    	        |   YES     |
| VDD 3.3V A1 	    |    	        |   YES     |
| VDD 3.3V A2 	    |    	        |   YES     |
| VDD 3.3V IO 	    |    	        |   YES     |
| IN XCLK EN  	    |       	    |   NO      |
| XCLK SEL    	    |          	    |   EXT     |
| UART BUFFER 	    | DIS   	    |           |
| Arty 5V - USB 5V  | DISCONNECT 

Picture below presents default configuration for slide switches and jumpers

```{image} ../img/arty-mpw-tester-default-configuration.png