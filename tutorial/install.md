---
layout: extra_naked
title: Docs
---


# Installing the Arduino tools
======

The DreamMaker FX hardware currently supports Windows 10, OS X, and probably Linux.  If you're running Windows 7, there are a few additional steps that are required to get the UF2 USB device drivers installed.  

First order of business, let's go download some free software and get rolling.  

 - Install the Arduino IDE: https://www.arduino.cc/en/main/software and open up the Arduino application
 - Navigate to either File->Preferences on a PC, or Arduino->Preferences on a Mac.  This will open the preferences pane.  Towards the bottom, there is a text field called *Additional Boards Manager URLs*.  Add the following to this text box `https://runjumplabs.github.io/arduino-board-index/package_dreammaker_fx_index.json`.  Click okay to close the preferences window.
 - Open up the Arduino board manager from  Tools->Board->Board Manager...
 - Scroll down and you should see a link to DreamMaker FX by Run Jump Labs.  Click Install!  
 - You are now ready to rock!

The setup process is very similar to Adafruit boards which use the same Arduino processor (Atmel SAMD51 family).  This page may offer some additional help [https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup](https://learn.adafruit.com/adafruit-metro-m4-express-featuring-atsamd51/setup). 


# Getting the Hardware Connected
======


The DreamMaker FX hardware is not USB powered so you'll need to plug it into the wall using the included wall-wart.

Plug the DreamMaker FX hardware into the USB port on your computer.  Make sure the USB cable you are using is not a charging cable.  There are lots of microUSB charging cables out there that just have wires for power and ground and no data!  

You should see a new drive show on your machine called DM_FX.  If the DreamMaker FX hardare doesn't show up when you plug it into your PC or Mac, press the reset button twice in quick succession.  The little LED near the USB jack should fade in and fade out rapidly.  

In Arduino IDE, go to Tools->Board.  You should see lots of options.  At the end of the list, you should see DreamMaker FX (SAMD51/ARM Cortex M4 Core).  Select this and you're ready to download effects!

Last thing and this is important: due to a massive brain fart, the input and output guitar jacks are actually backwards :/ The guitar plugs in next to the brass antenna connector hanging off the back of the board.  And the amp plugs into the other side (P2).

Before you upload a new effect from the Arduino application, quickly press the reset button twice.  This puts it back into bootloader mode.  If you don't do this, you may find that subsequent program downloads fail.  

There are four other LEDs on the hardware that dance around together once the DSP is running.  If you download an effect and these stop dancing, something has gone catastrophically wrong.  Let me (Dan) know if this happens!
