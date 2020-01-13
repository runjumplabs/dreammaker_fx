---
layout: extra_naked
title: Docs
---


# Installing the Arduino tools
------

The DreamMaker FX hardware currently supports Windows 10, OS X, and probably Linux.  If you're running Windows 7, there are a few additional steps that are required to get the UF2 USB device drivers installed.  

First order of business, let's go download some free software and get rolling.  

 1. Install the Arduino IDE: https://www.arduino.cc/en/main/software and open up the Arduino application.  If you already have Arduino installed, you'll want to upgrade to at least 1.8.10.  
 1. Navigate to either File->Preferences on a PC, or Arduino->Preferences on a Mac.  This will open the preferences pane.  Towards the bottom, there is a text field called *Additional Boards Manager URLs*.  Add the following to this text box `https://runjumplabs.github.io/arduino-board-index/package_dreammaker_fx_index.json`.  Click okay to close the preferences window.
 1. Open up the Arduino board manager from  Tools->Board->Board Manager...
 1. Scroll down and you should see a link to DreamMaker FX by Run Jump Labs (or just search for Dreammaker).  Click Install and then close the board manager.
 1. Select the DreamMakerFX hardware by going to Tools->Board - at the very bottom of the list you should see `DreamMaker FX (SAMD51/ARM Cortex M4`.  Select it.
 1. You are now ready to rock!

The setup process is very similar to Adafruit boards which use the same Arduino processor (Atmel SAMD51 family).  This page may offer some additional help [https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup](https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup). 

# Getting the Hardware Connected
------

The DreamMaker FX hardware is not USB powered so you'll need to plug it into the wall using the included wall-wart.

Plug the DreamMaker FX hardware into the USB port on your computer.  Make sure the USB cable you are using is not a charging cable.  There are lots of microUSB charging cables out there that just have wires for power and ground and no data!  

You should see a new drive show on your machine called DM_FX.  If the DreamMaker FX hardare doesn't show up when you plug it into your PC or Mac, you need to put it back into bootloader mode.  See below on the process for putting the pedal into bootloader mode.  If this doesn't work, double-check your USB cable as it may be a charging cable.

In Arduino IDE, go to Tools->Board.  You should see lots of options.  At the end of the list, you should see DreamMaker FX (SAMD51/ARM Cortex M4 Core).  Select this and you're ready to download effects!

Last thing and this is important: the input and output guitar jacks are actually backwards :/ The guitar plugs in next to the brass antenna connector hanging off the back of the board.  And the amp plugs into the other side (P2).


# Placing the DreamMaker FX Hardware into Bootloader mode
------
It is practically impossible to "brick" the DreamMaker FX hardware.  If the DM_FX volume does not show up on your computer when you plug in the USB port, you need to put the hardware into "bootloader" mode.

The first method is shown below.

![Placing DreamMaker FX into bootloader mode](https://runjumplabs.github.io/dreammaker_fx/assets/images/bootloader-1.gif)

If the LEDs don't do the little dance as shown in the video, then follow this simple procedure:
 1. Unscrew the backplate of the pedal
 1. Locate the reset push button
 1. While the pedal is powered, press the reset button twice in quick succession.  There is a small green LED near the USB jack - this should start to  fade in / out. 

 The pedal is now in bootloader mode.
