# README - OHDSP DSP-ADAU1452-StandAlone Release 1.0 #

## Disclaimer ##

Copyright Paul Janicki 2015

Licensed under the TAPR Open Hardware License (www.tapr.org/OHL)

This documentation is distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE.

This is part of my Open Hardware DSP Platform.

### Known issues ###
R308 is shown as 0R - this should be not fitted (otherwise you will sort the supply rail!). This resistor was provided incase the adjustable version of U302 was used (TPS7A4501). 


### What is this repository for? ###

**Quick summary**

This is a simple self-bootable ADAU1450, ADAU1451, or ADAU1452 based DSP board with 4 I2S (TDM/left and right justified and more) input and 4 output connectors. When used with the ADAU1451 and ADAU1452 parts there are also optical and coaxial SPDIF input and output connectors. There is an I2C connector for connection to a host microcontoller or the Analog Devices SigmaStudio USBi to EZ-Board Adapter (ADZS-USBI2EZB) or anything that will do the same job (eg freeUSBi). The board has space for a self-boot EEPROM and so with the ADZS-USBI2EZB or compatible device the board can be programmed as you wish and will selfboot the last program written when enabled. 

This board forms the core of the open hardware DSP platform which is designed to be a highly customisable and flexible DSP platform. 

This repository contains the KiCad design files (KiCad 4.0.1-stable), manufacturing Gerber/drill files and PDF outputs for this board.


### How do I get set up? ###
(Note this is for KiCad releases up to and including 4.0.1-stable)

**Summary of set up**

1. Set your self up a directory on a local disk, something simple will make life easier (eg C:\Electronics on Windows as used here), but anywhere will do just fine.
2. Download the Kicad-Libs from [https://github.com/ohdsp/KiCad-Libs](https://github.com/ohdsp/KiCad-Libs) and place in C:\Electronics\Kicad-Libs (or your chosen folder) 
3. Create a OHDSP subdirectory in C:\Electronics (so C:\Electronics\OHDSP)
3. Download this project to C:\Electronics\OHDSP\DSP-ADAU1452-StandAlone
4. Fire up Kicad
5. Open the main project file C:\Electronics\OHDSP\DSP-ADAU1452-StandAlone\Schematics\DSP-ADAU1452-StandAlone.pro
6. (Optional) Setup Pcbnew component library as below.
7. Do as you wish with the project, just keep it under TAPR Open Hardware License

Make sure your git setup doesn't exclude files used in the project (like .LIB files) or things may go wrong down the line.

**KiCad Library Configuration**

Note that you need to setup a Pcbnew library, but the eeschema libraries should work without any changes if you followed the instructions above.

To setup Pcbnew libraries:

In Pcbnew go to Preferences -> Footprint Libraries Manager. Under Global Libraries tab in the top list check if there is a nickname "MyKiCadLibs-Footprints" (usually at the end of the list). If there is but it points to the wrong place then change the Library Path to point to MyKiCadLibs-Footprints (eg C:\Electronics\KiCad-Libs\MyKiCadLibs-Footprints.pretty) folder for your setup. If this is missing you can use "Append with Wizard", choose "Files on my computer", click next, browse to library location (eg C:\Electronics\KiCad-Libs\MyKiCadLibs-Footprints.pretty) and select the folder MyKiCadLibs-Footprints.pretty, click next, check the Status column states OK and the Format is KiCad (if not re-download the library) and click next, then select "To global library configuration..." and click Finish.


To setup eeschema component libraries:
Either from KiCad project window go to Tools -> Run Library Editor OR under eeschema, go to Tools -> Library Editor. Then Preferences -> Component Libraries.

The top section "Component Library Files" should ideally contain only two libraries, the "power" library that ships with KiCad and "MyKiCadLibs-Lib" available from above. To setup MyKiCadLibs-Lib as a relative path under the "User defined search path" click add. Browse to the location of KiCad-Libs you download above (eg C:\Electronics\KiCad-Libs) and click "Select Folder". Say yes to add a relative path. Under component library files click add, browse to the KiCad-libs again (eg C:\Electronics\KiCad-Libs), select file "MyKiCadLibs-Lib.lib" and click open. MyKiCadLibs-lib should appear in the component library list with no path as it will be using the user defined search path set in the box below. 
