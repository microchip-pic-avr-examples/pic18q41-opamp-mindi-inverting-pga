# Getting started with Mindi® simulation and PIC18-Q41 microcontrollers
This guide will get you up and running with simulating the analog OPAMP module in PIC18-Q41 family devices using the Mindi simulation tool.  **For more information about getting started with and using the MPLAB Mindi Analog Simulator please refer to the following resources:**
- [Microchip Developer - Introduction to MPLAB Mindi Analog Simulator](https://microchipdeveloper.com/mindi:mindi-analog-simulator-introduction)
- [Getting Started with the MPLAB Mindi Analog Simulator Document](http://ww1.microchip.com/downloads/en/DeviceDoc/Getting-Started-MPLAB-Mindi-Analog-Simulator-DS50002564B.pdf)

## Configuration: Inverting Programmable Gain Amplifier (PGA)
The Inverting Programmable Gain Amplifier is a configuration with run-time selectable gain.

![Inverting PGA](images/configuration.png)

![Non-Inverting PGA Equation](images/inverting-gain.PNG)

### Mindi Simulation
![Mindi](images/mplab-mindi-analog-simulator.png)

Download and open the follower **Mindi schematic [here](schematics/Inverting_PGA.wxsch)**. Press the _play_ button to simulate with an example stimulus source.

### Adjustment Options
The amplification of the Inverting Programmable Gain Amplifier can be adjusted using any of 8 internal resistor ladder ratio levels by changing the GSEL value in the appropriate OPAxCON register. The table below shows the different gain settings in this mode of operation, and the corresponding GSEL values. This information can also be found in the device datasheet.

|GSEL[2:0]  | R1   | R2   | Inverting (R2/R1)|
|-----------|:----:|:----:|:----------------:|
|111        | 1R   | 15R  |  15              |
|110        | 2R   | 14R  |  7               |
|101        | 4R   | 12R  |  3               |
|100    	  | 6R   | 10R  |  5/3             |
|011     	  | 8R   | 8R   |  1               |
|010        | 12R  | 4R   |  1/3             |
|001        | 14R  | 2R   |  1/7             |
|000        | 15R  | 1R   |  1/15            |

### Updating composer fields
Once the desired result has been verified with Mindi simulation, the corrected values should be moved back into MCC by copying resistor configurations across to the composer of your preference.

### Don't have Mindi?
Download and install [Mindi simulation tool](https://www.microchip.com/mplab/mplab-mindi) here.
