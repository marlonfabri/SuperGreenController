![SuperGreenLab](assets/sgl.png?raw=true "SuperGreenLab")

[![SuperGreenLab](assets/reddit-button.png?raw=true "SuperGreenLab")](https://www.reddit.com/r/SuperGreenLab)

# Table of Contents

   * [SuperGreenDriver](#supergreendriver)
   * [Board Overview](#board-overview)
   * [Outputs](#outputs)
      * [Light and AC](#light-and-ac)
      * [Motors](#motors)
      * [Sensors](#sensors)
      * [Power considerations](#power-considerations)
   * [License](#license)
   * [Creative Commons Warranties Disclaimer](#creative-commons-warranties-disclaimer)

# SuperGreenDriver

![SuperGreenLed](assets/pcb-side.png?raw=true "SuperGreenLed")
V1.0 Prototype

Connected grow box controller with 6 light/AC control output (10V analog), 3 Motors output (24V/1A) and 3 sensors ports (I2C) from supergreenlab (https://supergreenlab.com/). This open hardware design is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.

Pull requests of relevant issues are warmly welcomed.

# Board Overview

* **MCU** : [ESP32-WROOM-32](https://www.espressif.com/en/products/hardware/esp-wroom-32/overview), wifi , bluetooth and BLE microcontroller. Fimrware : [SuperGreenOS](https://github.com/supergreenlab/SuperGreenOS) app : [SuperGreenApp](https://github.com/supergreenlab/SuperGreenApp)
* **Light/AC OUTPUTS** : 6x 0-10V Analog output (3.3V->10V done using [LM358](https://www.diodes.com/assets/Datasheets/LM358.pdf) op amp). Connector : [S3B-XH-SM4-TB](http://www.jst-mfg.com/product/detail_e.php?series=277)
* **MOTOR OUTPUTS** : 3x 24V output controlled by mosfet. Connector : [S2B-XH-SM4-TB](http://www.jst-mfg.com/product/detail_e.php?series=277)
* **SENSORS** : 1x I2C shared with embedded temperature sensor, 1x I2C shared on 2 connectors. Connector : [S4B-XH-SM4-TB](http://www.jst-mfg.com/product/detail_e.php?series=277)
* **ONBOARD SENSORS** : [SHT30](https://www.sensirion.com/en/environmental-sensors/humidity-sensors/digital-humidity-sensors-for-various-applications/) for temperature and humidity and a current sensor ([ZXCT1110W5-7](https://www.diodes.com/assets/Datasheets/ZXCT1107_10.pdf), more on this one later)
* **POWER IN** : 24VDC/5A standard 5x2.5mm barrel/Jack input (Power supply : https://amzn.to/2DNSty4)
* **DCDC** : [TS30041](https://www.semtech.com/uploads/documents/ts3004x.pdf) 3.3V buck stepdown, up to 1A
* **ADDITIONAL** : 2.54 mm solderable header (additional pins and flash) JTAG and flash TAG connect interface
* **STACKUP** : standard 4 layers 1.6mm FR4 (Signal-GND-POWER-Signal)

# OUTPUTS

## Light and AC

* **L1->L4** : Provide both power (24V) and control (0-10V). These outputs can be used to power SuperGreenBoards 36.301B (20W) and 72.301B (40W) for a max power consumption of 80W.
* **L5 & L6** : Power pin is not connected, only provide control (0-10V).

The 0-10V Analog output the Light/AC output can :
* Control any of the SGB 36.301B, 72.301B, 144.301B 
* Control a MeanWell type B or AB power supply (eg for the SGB 288.301B)
* Control any AC equipement through a [SSR relay](https://amzn.to/2DSlBoa)
* Control any device that can be driven by a 0-10V voltage

## Motors

**M1->M3** connectors are standard 2 pins JST connectors. It can be used to power 24V fans, blowers, pumps ect...

Example of compatible devices : [120mm blower](https://amzn.to/2GQcyqW) [97mm blower](https://amzn.to/2XcGl2I) [120mm fan](https://amzn.to/2GyCE26) [80mm fan](https://amzn.to/2IyqqZ4) 

## Sensors

* **S1** : 3V3 I2C port shared with embedded temperature/humidity sensor
* **S2 & S2bis** : shared 3V3 I2C bus

# POWER CONSIDERATIONS

The SuperGreenController is meant to be powered by a 24VDC/5A power supply for a total of 120W maximum.

A **10W** margin should be kept to ensure proper functionnement of the controller (this includes wifi, onboard sensors, onboard energy conversions ect.. and a large safety margin).
No more than **80W** of leds should be powered by the controller itself (2x 72.301B, 4x 36.301B or 1x 72.301B and 2x36.301B)
The rest of the energy can be used to power fans blowers and pumps.

An onboard current sensor will be used to monitor the power consumption of each device attached to the controller and determine is the power demand of the system is too high.

# License

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

# Creative Commons Warranties Disclaimer

UNLESS OTHERWISE MUTUALLY AGREED TO BY THE PARTIES IN WRITING, LICENSOR OFFERS THE WORK AS-IS AND MAKES NO REPRESENTATIONS OR WARRANTIES OF ANY KIND CONCERNING THE WORK, EXPRESS, IMPLIED, STATUTORY OR OTHERWISE, INCLUDING, WITHOUT LIMITATION, WARRANTIES OF TITLE, MERCHANTIBILITY, FITNESS FOR A PARTICULAR PURPOSE, NONINFRINGEMENT, OR THE ABSENCE OF LATENT OR OTHER DEFECTS, ACCURACY, OR THE PRESENCE OF ABSENCE OF ERRORS, WHETHER OR NOT DISCOVERABLE. SOME JURISDICTIONS DO NOT ALLOW THE EXCLUSION OF IMPLIED WARRANTIES, SO SUCH EXCLUSION MAY NOT APPLY TO YOU.
