# H01R00 Module #

**H01R00 is a smart RGB LED module** based on Cree CLVBA-FKA-CC1F1L1BB7R3R3 RGB LED and STM32F0 MCU. It is part of the upcoming Hexabitz modular prototyping system.

- Use as a stand-alone smart RGB LED and easily control via a Command Line Interface (CLI).
- Firmware has embedded on / off / toggle, PWM, dimming and color sweep functionality.
- Program advanced C code with our easy-to-use APIs.
- Connect many H01R00 modules together and build interesting flat and curved boards with any configuration you imagine!
- Send commands to a single LED, a group of LEDs or broadcast to all of them at the same time.
- Connect to external hardware or combine with other Hexabitz modules!

===============================================

## About Hexabitz ##

Hexabitz is a new kind of electronic prototyping platforms with game-changing modularity and a hint of biomimicry. Hexabitz modules connect with each other using a novel edge-soldering system and allow you to build tidy, compact and completely re-configurable electronic boards. **Learn more about Hexabitz [here](https://www.hexabitz.com/)**.

===============================================

## Useful Links ##

- Buy H01R00 module on [Tindie Store](https://www.tindie.com/products/Hexabitz/rgb-led-module-h01r00/)
- Introdcution to Hexabitz modular prototyping platform on [Hackaday.io](https://hackaday.io/project/76446-hexabitz-modular-electronics-for-real)
- Overview of hexabitz software [architecture](https://hackaday.io/project/76446-hexabitz-modular-electronics-for-real/log/117213-hexabitz-software-architecture)
- Hexabitz demo [projects](https://hackaday.io/list/87488-hexabitz-projects)

## Documentation ##
We developed a new form of documentation we call it the Factsheet: it's a mix between a hardware datasheet listing electrical properties and a software cheat-sheet showing you quickly the most important software functions and commands. Factsheets are color-coded and designed to be printed double-sided. We think they will come in handy for your Hexabitz projects. Let us know if you like them! 

- [Module factsheet](https://d3s5r33r268y59.cloudfront.net/datasheets/11566/2018-03-01-06-19-35/H01R00%20Factsheet.pdf)

## Design Files ##
- Module schematics [[PDF](https://www.dropbox.com/s/ouq9ytm361xokm2/H01R00%20Schematics.pdf?dl=0)]

===============================================

## How do I get set up? ##

### If you want to compile the code: ###

1- If you didn't already, download Keil uVision MDK toolchain from [here](http://www2.keil.com/mdk5/uvision/). Get your free [license](http://www.keil.com/) for STM32F0 MCUs!

2- Download or clone this repository source code and open the uVion projext in MDK-ARM folder (it has .uvprojx extension).

3- If you are loading a single module, simple compile the code and load it to module MCU via one of the firmware update methods explaind [here]().

4- If you are loading multiple modules of the same type (connected in an array), then manually modify the module ID in Options for Target >> C/C++ >> Preprocessor Symbols >> Define >> _module=x (where x the module ID) and in Output >> Name of Executable. Recompile the project and load each module according to its ID. You can also create multiple targets as explained in the firmware update [guide]().

### If you want to load a precompiled HEX file ###

1- Navigate to MDK-ARM/Objects and load the *Module 1.hex* HEX file using any firmware update method described [here]().

### How do I test? ###

1- If code is loaded correctly, you should see one or few indicator LED blinks when you power-cycle.

2- Use [RealTerm](https://sourceforge.net/projects/realterm/) or any other terminal emulator with a USB-to-USRT cable to access the module CLI. Learn about using the CLI [here]().

3- Check available CLI commands by typing *help* or use the module [factsheet](https://d3s5r33r268y59.cloudfront.net/datasheets/11566/2018-03-01-06-19-35/H01R00%20Factsheet.pdf). Make sure the factsheet BOS version number (at the footer) matches the source code version you have.

### How do I update the source code for an old project? ###

1- If your project follows portability guidelines, then just keep all files in the *User* folder and replace all other folders with the newer source code.

### Where should I add my code? ###

To preseve maximum code portability between projects, we advise you to:

1- Keep all you custom source and header files in the *User* folder.

2- Add your code to the *FrontEndTask()* in *main.c* and add other custom function there including custom interrupt callbacks.

3- Add any external header files you want to include to the *project.h* file.

4- Add any topology header files to *User* folder and include them in *project.h*.

===============================================

## Software FAQ ##

### Q: ###
A:

## Hardware FAQ ##

### Q: Isn't a 32-bit MCU an overkill for a smart LED module? ###
A: Yes! But all Hexabitz modules -whether it's a complex Ethernet or IMU or a simple LED- share same backend hardware and software. This what gives the platform its unmatched modularity and scalability. Cortex-M0 MCUs are small, cheap, power-efficient, yet capable of really wonderful things. Having an embedded MCU provides a cheaper and more compact alternative to connecting an LED breakout with an external controller.

### Q: What level of soldering experience is required? ###
A: Hexabitz are designed for the absolute soldering beginners! The edge pads are large and easy to reach and anyone with basic knowledge of soldering can assemble a flat array. Curved and spherical arrays require more training but can be made easier with 3d-printed fixtures.

Check our [website](https://www.hexabitz.com/faq/) for more information or contact us about any questions or feedback!

===============================================

## See also these repositories ##

- [H05R00]() - Micro-SD Memory Card Module

- [H09R00]() - 600VAC / 1.2A Solid State Relay Module

===============================================

## Who do I talk to? ##

* Email as at info@hexabitz.com for any inquiries
* Or connect with us on [Hackaday.io](https://hackaday.io/Hexabitz)

## How do I contribute? ##

* We welcome any and all help you can provide with testing, bug fixing and adding new features! Feel free to contact us and share what's going on in your mind.
* Please send us a pull request if you have some useful code to add!
