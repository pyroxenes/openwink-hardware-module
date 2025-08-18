<div align="center">
  
# Open Wink Hardware Module
  
Hardware Module for the openwink project, an open sourced alternative to the MX-5 [Wink/Sleepy Eye Mod](https://mx5tech.co.uk/wink-sleepy-eye-mod)
  
### Technologies

[![KiCad](https://img.shields.io/badge/%20-%23314CB0.svg?style=for-the-badge&logo=kicad&logoColor=%23ffffff&logoSize=auto)](https://www.kicad.org/) 
[![Espressif](https://img.shields.io/badge/espressif-E7352C.svg?style=for-the-badge&logo=espressif&logoColor=white)](https://www.espressif.com/)

[![BLE](https://img.shields.io/badge/Bluetooth_Low_Energy-0082FC.svg?style=for-the-badge&logo=Bluetooth&logoColor=white)](https://www.bluetooth.com/learn-about-bluetooth/tech-overview/)

</div>

# Table of Contents
- [About the Project](#about-the-project)
- [Version History](#version-history)
- [Project Features](#project-features)
- [Purchasing](#purchasing)
  - [Support the Project](#support-the-project)
- [Acknowledgements](#acknowledgements)
- [Contact](#contact-me)

## About the Project

This project began as a continuation of seasaltsaige's [pop up wink mod](https://github.com/seasaltsaige/popup-wink-mod), with the goal of creating custom hardware to streamline and minaturize the existing project built from off the shelf components

This project serves as an open source (though purchasable) alternative to the popular [MX-5 Tech Wink Mod](https://mx5tech.co.uk/wink-sleepy-eye-mod). This repository contains the design information for the hardware module component of this project.
- Hardware development Version History
  - Discusses changes throughout all three revisions
  - Documents why we made certain design choices
- Board Features
- Current Hardware Version Design

## Version History

### Revision 1

Although the initial off the shelf project this module was based around utilized an Arduino Nano, we ended up choosing an Espressif ESP32-S3 due to easier access to coded PHY functionality required for useable ranges.

<div align="center">
  
  <img src="./media/rev1unpopnanner4scale.png" alt="rev 1 unpopulated with a banana (overripe) for scale" width="50%"></img>
  #### Unpopulated first revision board
  
</div>

Two signals wires providing a potential of atleast 12v are required to drive a NA Miata headlight motor at a resonable speed. One wire must be sent high and the other kept low to open the healight, and this must be inverted to lower the headlight. If both wires are sent high, the headlight will continue to open and close until one wire goes low. In order to provide these 12v+ signals from a 3.3v logic level micro controller, we decided to utilize optocouplers to switch the headlight supply power. For this revision we utilized TLP5701 optocouplers. On this revision we also used these same optocouplers, with a series resistor, to measure the two status wires for each of the headlights. This approach proved to be overkill on further investigation into the motor. 

<div align="center">
  
  <img src="./media/rev1assembled.png" alt="rev 1 unpopulated with a banana (overripe) for scale" width="40%"></img>
  #### Assembled first revision board during testing
  
</div>

The voltage range provided to the headlights by the miata ranges between 12-15v, but the ESP32 requires a much smaller supply voltage of 3.3v. We ended up selecting a KF33BD-TR LDO to generate the 3.3v required to run the ESP32. Due to heat generated from this large voltage step down, we utilized a two stage power supply in the second revision. 
The connectors we chose were two five position AUH series wire-to-board connectors from JST. These connectors ended up being too small for our crimping tools so this revision was tested by soldering wire to the board. Additionally, we implemented status LEDs on all of the outputs to aid in diagnostics.


<div align="center">
  
  <img src="./media/rev1pcb.png" alt="rev 1 unpopulated with a banana (overripe) for scale" width="20%"></img>
  <img src="./media/rev1schem.png" alt="rev 1 unpopulated with a banana (overripe) for scale" width="50%"></img>

  #### Revision 1 PCB and schematic
  
</div>

### Revision 2

<div align="center">
  
  <img src="./media/rev2unpop.png" alt="rev 1 unpopulated with a banana (overripe) for scale" width="50%"></img>
  #### unpopulated second revision board
    
</div>

### Revision 3

## Project Features

## Purchasing
For more information about purchasing a pre-made module, please visit [miatawink.tech](https://miatawink.tech/).

### Support the Project 
[![BuyMeACoffee](https://img.shields.io/badge/Buy%20Me%20a%20Coffee-ffdd00?style=for-the-badge&logo=buy-me-a-coffee&logoColor=black)](todo:☕)

If you would rather support the open source initiative for the project, feel free to [donate](todo:☕) to keep the project alive.

## Acknowledgements
The Open Wink Hardware Module was created and is maintained by [pyroxenes](https://github.com/pyroxenes).

- Special thanks to [seasaltsaige](https://github.com/seasaltsaige) for creating and iterating on the mobile app and website. 
  - See related - [openwink](https://github.com/seasaltsaige/openwink/tree/master)


## Contact Me
You can reach me through my contact email at [todo:📧](todo:📧)
