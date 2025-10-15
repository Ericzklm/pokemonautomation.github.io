# Pro Micro (using mini-grabber cables)

**This setup is deprecated, though still supported. New users should pick something from the [recommended list](../../ControllerList.md).**

<hr>

The wired controller setup is the most difficult of the setups. Most of you who joined us prior to 2025 will be familiar with this setup.

The Pro Micro is the recommended microcontroller to use for experimenced users. It is harder to setup than the Arduino Leonardo, but is smaller in space and cheaper in quantity for automating multiple Switches.

This tutorial will use mini-grabber cables to connect the UART to the Pro Micro. While it is ugly and bulky, it is the easiest option for users who prefer not to do any soldering.

<img src="../Images/ProMicro/ControllerSetup-ProMicro-MiniGrabbers.jpg" width="45%"> <img src="../Images/Teensy2/ControllerSetup-Teensy-Setup.jpg" width="45%">

## Hardware Setup:

**Required Hardware (Full List):**

1. A regular [Nintendo Switch](../index.md#the-nintendo-switch) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../index.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../index.md#video-capture-card-the-computers-eyes).
4. A Pro Micro microcontroller.
5. USB A to mini USB cable
6. USB to Serial TTL (UART)
7. Mini-Grabbers to Male Jumper Wires

**Estimated Total Cost (USD):** (not including computer, Nintendo Switch, and household tools)

- **Single Setup:** $40 - $50
- **Bulk Purchase:** $24 per setup (in quantities of 4+)

### Recommended Purchase Links:

**Capture Card:**

- [See previous section.](../index.md#video-capture-card-the-computers-eyes)

**Pro Micro:** [https://www.amazon.com/gp/product/B08BJNV1J3](https://www.amazon.com/gp/product/B08BJNV1J3)

**USB A to micro USB cable:**

- [https://www.amazon.com/Android-Compatible-Smartphones-Charging-Stations/dp/B095JZSHXQ](https://www.amazon.com/Android-Compatible-Smartphones-Charging-Stations/dp/B095JZSHXQ)

**USB to Serial TTL (UART):**

There are many options here. The one we recommend (for ease of use) is the Adafruit model:

  - [https://www.adafruit.com/product/954](https://www.adafruit.com/product/954)
  - [https://www.digikey.com/en/products/detail/adafruit-industries-llc/954/7064488](https://www.digikey.com/en/products/detail/adafruit-industries-llc/954/7064488)
  - [https://www.amazon.com/dp/B00DJUHGHI/](https://www.amazon.com/dp/B00DJUHGHI/)

<img src="../Images/UART/ControllerSetup-UART-Adafruit.jpg" width="30%">

Or you can search for "CP2102" and you'll get tons of hits from various brands/sellers that look like these:

<img src="../Images/UART/ControllerSetup-UART-CP210x-Blue.png" width="22%"> <img src="../Images/UART/ControllerSetup-UART-CP210x-Red.jpg" width="34.5%">

**Mini-Grabbers to Male Jumper Wires**

- [https://www.amazon.com/gp/product/B08M5GNY47](https://www.amazon.com/gp/product/B08M5GNY47)

If you choose a different UART make sure that the wire-end of the mini-grabber can plug into the UART. So if you picked the red CP2102 UART, you will want the female mini-grabber.

<img src="../Images/UART/ControllerSetup-UART-MiniGrabber.jpg" width="40%">



### Hardware Assembly:

**Step 1: Connect UART to the Pro Micro**

Once you have your hardware, you need to make some connections between your UART cables and the Pro Micro. Use the mini-grabber cables to connect them.

Make the following connections:

| **UART pin** | **Microcontroller pin** |
| --- | --- |
| TX | RX1 |
| RX | TX0 |
| GND | GND (any one is fine) |
| VCC | Leave unconnected |

Note that the mini grabber clips may not fit through the holes on the Pro Micro. This is fine.

<img src="../Images/ProMicro/ControllerSetup-ProMicro-MiniGrabbers-0.jpg" width="45%"> <img src="../Images/ProMicro/ControllerSetup-ProMicro-MiniGrabbers-1.jpg" width="45%">

**Step 2: Download QMK Toolbox**

A few QMK versions are known to work. e.g. 0.1.1, 0.2.2, and 0.3.1. Other versions may not work (e.g. 0.3.2 does not work).

Download [QMK Toolbox](https://github.com/qmk/qmk_toolbox/releases). Ensure you download a version known to work. e.g. 0.3.1.

You want the file `qmk_toolbox.exe`. You'll find it under `Assets`, under the version number that you choose (e.g. 0.3.1).

**Step 3: Flash PABotBase into your Device.**

The root folder of the SerialPrograms package should have a set of .hex files for each of the different devices.

<img src="../Images/GeneralSetup-CCFolder.png" width="88%">

1. Run the QMK Toolbox program that you downloaded in PART 2.
2. Open the .hex named `NintendoSwitch-PABotBase-xxxxxxxxx-ProMicro.hex`.
3. Change the MCU to `atmega32u4`.
4. Check the "Auto-Flash" box.

<img src="../Images/ProMicro/ControllerSetup-ProMicro-Flash-0.png" width="75%">

5. Plug the Pro Micro into your computer.
6. Short the RST and GND pins.

<img src="../Images/ProMicro/ControllerSetup-ProMicro-Flash-1.jpg" width="30%">

The QMK program will now flash the program to the Pro Micro and show a bunch of logging.
Afterwards, the 2 LEDs on the Pro Micro should flash in unison for 5 seconds before turning off.

<img src="../Images/ProMicro/ControllerSetup-ProMicro-Flash-2.png" width="75%">

7. Unplug the Leonardo from your computer.

**Step 4:**

1. Turn on your Switch and dock it.
2. Connect your Pro Micro to the Switch's dock.
3. Connect the UART to your computer.

At this point, your final setup should look like this:

<img src="../Images/Teensy2/ControllerSetup-Teensy-Setup.jpg">


## Software Setup:

Continue to: [Wired Controller (AVR8) Software Setup](Controller-Software-AVR8.md).


<hr>

**Credits:**

- Kuroneko/Mysticial
- jw

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)




