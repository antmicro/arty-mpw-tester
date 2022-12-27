# Arty MPW tester

```{image} ../img/arty-mpw-tester.png
```
&nbsp;

The Arty MPW tester is simple expansion board compatible with Digilent Arty A7 development kit. This board connects IO signals from the Xilinx Artix FPGA located on the Arty board to an open hardware Caravel breakout board. The Caravel breakout board allows testing ASIC designs prepared for Multi Project Wafer (MPW) shuttles and fabricated with one of the available open Process Design Kits (PDKs).

The hardware is open and can be found on GitHub:
<https://github.com/antmicro/arty-mpw-tester/>

The following instructions explain how to set up the board for MPW testing.

## Arty MPW tester configuration

Arty MPW tester was designed to give user flexibility in configuration of the tester.\
User can independently configure:

- Power
- FTDI to MPRJ UART connection (enable/disable)
- Source for Caravel-breakout XCLK (internal oscillator / Arty IO42 pin)
- Internal XCLK source (enable/disable)

### Power

The Arty MPW tester can be supplied either from Arty or USB connector.

```{note}
Both power sources are always connected to the dual LDO via protection diodes.
```

The Arty MPW tester features dual LDO supplying 1.8V and 3.3V rails.
Each rail can be set to either:

- fixed, supplying fixed 1.8V or 3.3V depending on rail
- dynamic, allowing user set LDO voltage using I2C digipot

#### Fixed/dynamic LDO selection

I2C digipot (`MCP4661-103E/ML`) is used to dynamically adjust 1.8V and 3.3V rail voltages.\
Placing jumper on position `FIXED` on either 1.8V and/or 3.3V rail bypasses digipot and forces LDO into fixed voltage regulation on given rail.

```{image} ../img/arty-mpw-tester-ldo-mode.png
```

#### Rail EN control

`LDO CTRL` switch connects either FTDI or Arty to the `EN1/EN2` pins of the dual LDO allowing for independent control over 1.8V and 3.3V rails.

```{image} ../img/arty-mpw-tester-power-ctrl-selector.png
```

#### Individual rail connections

Each of the power rails routed on Caravel breakout is exposed on `1x2 2.54mm` pin header allowing for selecting which rails are enabled.\
Using this header it is also possible to manually inject voltage into separate rails

 ```{image} ../img/arty-mpw-tester-power-rails.png
```

#### Arty / USB rail connection
```{warning}
This feature should be used only to supply Arty from Arty MPW tester.
```
User can decide to connect USB 5V and Arty 5V rails. 
This allows to supply Arty MPW tester and Arty from single USB-C connector.

```{image} ../img/arty-mpw-tester-arty-usb-rail-switch.png
```

### USB UART

FTDI used in design (FT230H) can be used in UART and MPSSE mode. For MPSSE mode `UART BUFFER` slide switch should be set to `DIS`.\
In `DIS` position FTDI retains control over buffers. Setting this switch to `EN` forces buffer to be enabled.

```{image} ../img/arty-mpw-tester-uart-buffer-switch.png
```


### XCLK

Clock supplied to the Caravel breakout can be sourced from two inputs:

- Arty MPW tester builtin 10MHz clock (internal)
- Arty IO42 pin (external)

`XCLK` source selection can be done using `XCLK SEL` header:

```{image} ../img/arty-mpw-tester-xclk-source-selection.png
```

When internal `XCLK` source is selected user can enable and disable clock using `INT XCLK EN` header:

```{image} ../img/arty-mpw-tester-internal-oscillator-ctrl.png
```

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
| Arty 5V - USB 5V  | OPEN          |           |

Picture below presents default configuration for slide switches and jumpers

```{image} ../img/arty-mpw-tester-default-configuration.png