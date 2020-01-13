---
layout: extra_naked
title: Docs
---

# First time installation 
------

## Install the Arduino tools
------

The DreamMaker FX hardware currently supports Windows 10, OS X, and probably Linux.  If you're running Windows 7, there are a few additional steps that are required to get the UF2 USB device drivers installed.  

First order of business, let's go download some free software and get rolling.  

 * Download and install the Arduino IDE: https://www.arduino.cc/en/main/software
    * Accept the defaults
    * You may be prompted to install several additional drivers; install them.
    * If you're running OS X Catalina, make sure you're using Arduino v1.8.10 or later.
    * Click `Finish` when the installs are complete.

 * Plug the Dream Lemur into an outlet, and connect to a USB port on your computer with a MicroUSB cable.  Make sure the USB cable you are using is not a charging cable.  There are lots of microUSB charging cables out there that just have wires for power and ground and no data!  If you don't see the `DM_FX` drive/volume show up on your computer, you may need to put your pedal into bootloader mode.  See the [Troubleshooting section](https://www.dreammakerfx.com/troubleshooting)

 * Install the DreamMaker FX Arduino board package In the Arduino IDE:
    * Navigate to either `File` -> `Preferences` on Windows, or `Arduino` -> `Preferences` on Mac. If you're using Linux, we assume you're enough of a bad ass to figure out what to do.
    * In the preferences window, find the text field toward the bottom called `Additional Boards Manager URLs`.
    * Insert this URL: https://runjumplabs.github.io/arduino-board-index/package_dreammaker_fx_index.json
    * Click OK to close the preferences window.

    * Navigate to `Tools` -> `Board` -> `Board Manager`.
    * Either type `dream` in the search box, or scroll down until you find `DreamMaker FX by Run Jump Labs`.
    * Click `Install`. This will take a few minutes; then hit `Close`.
 
 * Select teh DreamMaker FX hardeare
    * Navigate to `Tools` -> `Board `.  At the very bottom of the list you should see `DreamMaker FX (SAMD51/ARM Cortex M4`.  Select it.

 * Make some bitchin' effects and play some rock and/or roll very loudly.

The setup process is very similar to Adafruit boards which use the same Arduino processor (Atmel SAMD51 family).  This page may offer some additional help [https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup](https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup). 

## Connect the hardwaer
------

You should see a new drive show on your machine called DM_FX.  If the DreamMaker FX hardare doesn't show up when you plug it into your PC or Mac, you need to put it back into bootloader mode.  See below on the process for putting the pedal into bootloader mode.  If this doesn't work, double-check your USB cable as it may be a charging cable.


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
