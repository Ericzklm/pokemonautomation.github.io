# Raspberry Pi: Pico W and Pico 2 W (Advanced Setup)

This is the advanced setup guide for the Pico and Pico 2 family. It is functionally the same as [UART mode](Controller-PicoW-UART.md), but it will not glitch or reset when docking/undocking the Nintendo Switch.

Glitching/resetting is a problem that affects all the external UART setups that are powered by the Switch:

- Pico W (UART mode)
- Arduino Uno R3
- Arduino Leonardo
- Pro Micro
- Teensy 2 / Teensy++ 2

Each time you dock/undock the Switch, the dock momentarily cuts the power to its USB ports. This causes the board to either completely lose power and reset, or worse, it glitches the board into a bad state that can only be cleared via reset or power cycle.

This article will demonstrate a setup that fixes this problem for the Pico W. This setup has also been tested working on the Pro Micro. We assume it will work for the others as well, but you should consult their respective circuit diagrams to make sure they have backflow protection into the USB port.

This is the most difficult to do serial setup that we've ever done and is reserved for readers with extensive experience in circuits. Incorrect connections can lead to damage to the hardware components involved:

- The Pico W board.
- The UART cable/board.
- Your computer's USB port.
- Your Switch's dock.

| **Mode** | **Connections** | **Controller Support** | **Setup Difficulty** |
| --- | --- | --- | --- |
| [USB Mode](Controller-PicoW-USB.md) | 1. Pico W's USB port -> Computer | Wireless controllers only:<br>- Switch 1: Wireless Pro Controller<br>- Switch 1: Left Joycon<br>- Switch 1: Right Joycon | Very Easy |
| [UART Mode (simple)](Controller-PicoW-UART.md) | 1. Pico W's USB port -> Switch<br>2. Pico W's pins 6/7/8 -> External UART<br>3. External UART -> Computer | Both wireless and wired:<br>- HID: Keyboard<br>- Switch 1: Wired Controller<br>- Switch 2: Wired Controller<br>- Switch 1: Wireless Pro Controller<br>- Switch 1: Left Joycon<br>- Switch 1: Right Joycon | More Difficult |
| **UART Mode (advanced) (this guide)** | 1. Pico W's USB port -> Switch<br>2. Pico W's pins 6/7/8 -> External UART<br>3. External UART -> Computer | Both wireless and wired:<br>- HID: Keyboard<br>- Switch 1: Wired Controller<br>- Switch 2: Wired Controller<br>- Switch 1: Wireless Pro Controller<br>- Switch 1: Left Joycon<br>- Switch 1: Right Joycon | Most Difficult |

If you are here, we assume that you already have a working Pico W (UART mode) setup. So this wiki will only cover the differences from the basic UART setup. Furthermore, the parts list that we will choose will be geared toward making the following (boxed) easy-to-use product with no exposed circuitry. You are free to do whatever you want.

<img src="../Images/PicoW/ControllerSetup-PicoW-Advanced.jpg" width="45%">

## Hardware Setup:

**Required Hardware:**

1. A Raspberry Pi Pico W, or Pico 2 W microcontroller. (without pins)
2. [A micro-USB to USB-A cable or adapter.](https://www.amazon.com/gp/product/B09FXJD61Z)
3. [USB to Serial TTL (UART)](https://www.amazon.com/dp/B07T1XR9FT)
4. [1N5817 Schottky Diode](https://www.amazon.com/dp/B07Q5H1SLY)
5. [Press-fit Headers.](https://www.adafruit.com/product/5938) (or soldering)
6. [Dupont connector kit.](https://www.amazon.com/dp/B096DC1J3X) (or soldering)
7. [Pico enclosure.](https://www.adafruit.com/product/6252)

Building just one of these will be expensive since many of these parts only be bought in volume. But the volume per-unit cost in parts comes down to about $12 USD.

### Hardware Assembly:

Make the following connections:

| **UART pin** | **Pico W pin** |
| --- | --- |
| RX | TX -> GP4 (pin 6) |
| TX | RX <- GP5 (pin 7) |
| GND | GND (pin 8, or any other GND pin) |
| VCC (+5V) | VSYS (pin 39) via diode |

The difference from the regular UART mode guide is that here we do connect the UART's +5V VCC line. This allows the Pico to be powered by both the USB or the UART - thus allowing it to stay powered and not glitch or reset when the USB power is momentarily lost when docking/undocking the Switch.

It is important that the VCC <-> VSYS connection be done through a diode which only allows current in the direction of VCC -> VSYS. This is needed to prevent backflow through the UART when both UART and USB are connected and the USB side has a higher voltage!

Further Reading:

- https://www.penguintutor.com/electronics/pico-power
- https://electronics.stackexchange.com/questions/548990/which-shottky-diode-do-i-need-for-redundant-power-to-a-raspberry-pi-pico
- [Pinout and Circuit Diagrams](https://deepbluembedded.com/raspberry-pi-pico-w-pinout-diagram-gpio-guide/)



Here are some various pictures of a working setup:

**Breadboard:**

<img src="../Images/PicoW/ControllerSetup-PicoW-Advanced-Breadboard0-Small.jpg" width="39%"> <img src="../Images/PicoW/ControllerSetup-PicoW-Advanced-Breadboard1-Small.jpg" width="51%">

**Raw Connection:**

<img src="../Images/PicoW/ControllerSetup-PicoW-Advanced-Raw0-Small.jpg" width="45%"> <img src="../Images/PicoW/ControllerSetup-PicoW-Advanced-Raw1-Small.jpg" width="45%">


## Software Setup

Everything is the same as the [Pico W UART mode guide](Controller-PicoW-UART.md#software-setup).







<hr>

**Credits:**

- Kuroneko/Mysticial

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)








