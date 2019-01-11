![SuperGreenLab](assets/sgl.png?raw=true "SuperGreenLab")

[![SuperGreenLab](assets/reddit-button.png?raw=true "SuperGreenLab")](https://www.reddit.com/r/SuperGreenLab)

# SuperGreenDriver

![SuperGreenLed](assets/pcb-side.png?raw=true "SuperGreenLed")

Connected led driver from supergreenlab (https://supergreenlab.com/)

supergreenDriver is an open hardware led driving solution (6 outputs up to 24V - 1.5A) powered by a esp32 WROOM. This design is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License.

Pull requests of relevant issues are warmly welcomed.

# Board Overview

* **MCU** : ESP32-WROOM-32, wifi , bluetooth and BLE microcontroller (https://www.espressif.com/en/products/hardware/esp-wroom-32/overview)
* **LED drivers** : 6xAL8860MP buck step-down, up to 1.5A led driver (https://www.diodes.com/assets/Datasheets/AL8860.pdf)
* **DCDC** : TS30042 5V buck stepdown, up to 2A (https://www.semtech.com/uploads/documents/ts3004x.pdf)
* **LDO** : AZ1117CH-3.3TRG1 3.3V 800mA LDO (https://www.diodes.com/assets/Datasheets/AZ1117C.pdf)
* **POWER IN** : 24V standard 5mm barrel input (should be ok up to 40V)
* **OUTPUTS** : standard JST-XH series connectors (6xLEDS, 2xfans, 1x blower, 1x sensor)
* **ADDITIONAL** : 2.54 mm solderable header (additional pins and flash) JTAG and flash TAG connect interface

# Board Stackup

standard 4 layers 1.6mm FR4 (Signal-GND-POWER-Signal)

# License

This work is licensed under the Creative Commons Attribution-ShareAlike 3.0 Unported License. To view a copy of this license, visit http://creativecommons.org/licenses/by-sa/3.0/ or send a letter to Creative Commons, PO Box 1866, Mountain View, CA 94042, USA.

# Creative Commons Warranties Disclaimer

UNLESS OTHERWISE MUTUALLY AGREED TO BY THE PARTIES IN WRITING, LICENSOR OFFERS THE WORK AS-IS AND MAKES NO REPRESENTATIONS OR WARRANTIES OF ANY KIND CONCERNING THE WORK, EXPRESS, IMPLIED, STATUTORY OR OTHERWISE, INCLUDING, WITHOUT LIMITATION, WARRANTIES OF TITLE, MERCHANTIBILITY, FITNESS FOR A PARTICULAR PURPOSE, NONINFRINGEMENT, OR THE ABSENCE OF LATENT OR OTHER DEFECTS, ACCURACY, OR THE PRESENCE OF ABSENCE OF ERRORS, WHETHER OR NOT DISCOVERABLE. SOME JURISDICTIONS DO NOT ALLOW THE EXCLUSION OF IMPLIED WARRANTIES, SO SUCH EXCLUSION MAY NOT APPLY TO YOU.
