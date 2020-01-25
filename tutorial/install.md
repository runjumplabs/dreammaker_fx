---
layout: extra_naked
title: Docs
---

# First time installation 
------

The DreamMaker FX hardware currently supports Windows 10, OS X, and probably Linux.  If you're running Windows 7, there are a few additional steps that are required to get the UF2 USB device drivers installed.  

First order of business, let's go download some free software and get rolling.  

 * Download and install the Arduino IDE: https://www.arduino.cc/en/main/software
    * Accept the defaults
    * You may be prompted to install several additional drivers; install them.
    * If you're running OS X Catalina, make sure you're using Arduino v1.8.10 or later.
    * Click `Finish` when the installs are complete.

 * Plug the Dream Lemur into an outlet, and connect to a USB port on your computer with a MicroUSB cable.  Make sure the USB cable you are using is not a charging cable.  There are lots of microUSB charging cables out there that just have wires for power and ground and no data!  If you don't see the `DM_FX` drive/volume show up on your computer, you may need to put your pedal into bootloader mode.  See the [Troubleshooting section](https://www.dreammakerfx.com/troubleshooting).

 * Install the DreamMaker FX Arduino board package In the Arduino IDE:
    * Navigate to either `File` -> `Preferences` on Windows, or `Arduino` -> `Preferences` on Mac. If you're using Linux, we assume you're enough of a bad ass to figure out what to do.
    * In the preferences window, find the text field toward the bottom called `Additional Boards Manager URLs`.
    * Insert this URL: `https://runjumplabs.github.io/arduino-board-index/package_dreammaker_fx_index.json`
    * Click OK to close the preferences window.

    * Navigate to `Tools` -> `Board` -> `Board Manager`.
    * Either type `dream` in the search box, or scroll down until you find `DreamMaker FX by Run Jump Labs`.
    * Click `Install`. This will take a few minutes; then hit `Close`.

    ![DreamMaker FX package](https://runjumplabs.github.io/dreammaker_fx/assets/images/dmfx-package.png)
 
 * Select the DreamMaker FX hardeare
    * Navigate to `Tools` -> `Board `.  At the very bottom of the list you should see `DreamMaker FX (SAMD51/ARM Cortex M4`.  Select it.

    ![DreamMaker FX package](https://runjumplabs.github.io/dreammaker_fx/assets/images/select-board.png)

 * Make some bitchin' effects and play some rock and/or roll very loudly.

The setup process is very similar to Adafruit boards which use the same Arduino processor (Atmel SAMD51 family).  This page may offer some additional help [https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup](https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup). 

# Updating the DreamMaker FX Arduino package
------

There are always updates happening with new effects, bug fixes and improvements!  When you do a first time install, you'll have the latest and greatest.  However, it's always good to check back to see if there are updates.

 * In the Arduino program:
    * Navigate to `Tools` -> `Board` -> `Board Manager`.
    * Either type `dream` in the search box, or scroll down until you find `DreamMaker FX by Run Jump Labs`.
    * Select the latest version from the pull-down menu; then hit `Update`
