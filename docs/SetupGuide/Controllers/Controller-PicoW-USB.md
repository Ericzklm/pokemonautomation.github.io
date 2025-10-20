# Raspberry Pi: Pico W and Pico 2 W (USB Mode)

The Raspberry Pi Pico W (and Pico 2 W) is the easiest setup to get up and running (even easier than the ESP32). Thus, it is ideal for new users who just want to try out this project without getting too deep.

There are two operating modes of the Pico W family:

| **Mode** | **Connections** | **Controller Support** | **Setup Difficulty** |
| --- | --- | --- | --- |
| **USB Mode (this guide)** | 1. Pico W's USB port -> Computer | Wireless controllers only:<br>- Switch 1: Wireless Pro Controller<br>- Switch 1: Left Joycon<br>- Switch 1: Right Joycon | Very Easy |
| [UART Mode](Controller-PicoW-UART.md) | 1. Pico W's USB port -> Switch<br>2. Pico W's pins 6/7/8 -> External UART<br>3. External UART -> Computer | Both wireless and wired:<br>- HID: Keyboard<br>- Switch 1: Wired Controller<br>- Switch 2: Wired Controller<br>- Switch 1: Wireless Pro Controller<br>- Switch 1: Left Joycon<br>- Switch 1: Right Joycon | More Difficult |

<img src="../Images/PicoW/ControllerSetup-PicoW-USB.jpg" width="45%"> <img src="../Images/PicoW/ControllerSetup-PicoW-USB-Setup-Small.jpg" width="45%">

## Hardware Setup:

**Required Hardware (Full List):**

1. A regular [Nintendo Switch](../index.md#the-nintendo-switch) and its accessories (dock, power cable, HDMI cable). (You cannot use a Switch Lite.)
2. A [computer](../index.md#the-computer-the-player) running x64 Windows. (or another OS if you are able to set it up.)
3. A [video capture card](../index.md#video-capture-card-the-computers-eyes).
4. A Raspberry Pi Pico W, Pico WH, Pico 2 W, or Pico 2 WH microcontroller.
5. A micro-USB to USB-A cable or adapter.

\#1-3 are part of the initial setup so you should have all of these already.

**Estimated Total Cost (USD):** (not including computer and Nintendo Switch)

- **Single Setup:** $18 - $29
    - Capture Card: $10 - $20
    - Pico W: $6 - $7
    - USB Cable/Adapter: $2
- **Bulk Purchase:** ~$17 per setup
    - Capture Card: $10
    - Pico W: $6 each from Micro Center
    - USB Cable/Adapter: < $1 each from AliExpress

<img src="../Images/PicoW/ControllerSetup-PicoW-USB-SetupCloseup-Annotated-Small.jpg" width="800">


### Recommended Purchase Links:

**Capture Card:** [See previous section.](../index.md#video-capture-card-the-computers-eyes)

**Pico W Microcontroller:**

| **Model** | **Quantity** | **Price / Unit** | **Shopping Link** |
| --- | --- | --- | --- |
| Pico WH | 1 (with pins) | $7 / unit | [Micro Center](https://www.microcenter.com/product/650109/raspberry-pi-pico-wh-pico-wireless-with-headers-soldered) |
| Pico WH | 1 (with pins) | $7 / unit | [Adafruit](https://www.adafruit.com/product/5544) |
| Pico 2 WH | 1 (with pins) | $8 / unit | [Micro Center](https://www.microcenter.com/product/692334/raspberry-pi-pico-2w-with-header) |
| Pico 2 WH | 1 (with pins) | $8 / unit | [Adafruit](https://www.adafruit.com/product/6315) |
| Pico WH | 1 (with pins) | $12 / unit | [https://www.amazon.com/gp/product/B0BHM95WCM](https://www.amazon.com/gp/product/B0BHM95WCM) |
| Pico WH | 2 (with pins) | $11 / unit | [https://www.amazon.com/gp/product/B0BHM7TH1C](https://www.amazon.com/gp/product/B0BHM7TH1C) |
| Pico 2 WH | 1 (with pins + cable) | $15 / unit | [https://www.amazon.com/gp/product/B0F4W9J5CC](https://www.amazon.com/gp/product/B0F4W9J5CC) |
| Pico 2 WH | 1 (with pins) | $14 / unit | [https://www.amazon.com/gp/product/B0FGVQPZP6](https://www.amazon.com/gp/product/B0FGVQPZP6) |
| Pico W | 1 (no pins) | $6 / unit | [Micro Center](https://www.microcenter.com/product/650108/raspberry-pi-pico-w) |
| Pico W | 1 (no pins) | $6 / unit | [Adafruit](https://www.adafruit.com/product/5526) |
| Pico 2 W | 1 (no pins) | $7 / unit | [Micro Center](https://www.microcenter.com/product/687384/raspberry-pi-pico-2-w) |
| Pico 2 W | 1 (no pins) | $7 / unit | [Adafruit](https://www.adafruit.com/product/6087) |
| Pico W | 1 (no pins) | $12 / unit | [https://www.amazon.com/gp/product/B0FJFLM9DW](https://www.amazon.com/gp/product/B0FJFLM9DW) |
| Pico W | 2 (no pins) | $10 / unit | [https://www.amazon.com/gp/product/B0B72GV3K3/](https://www.amazon.com/gp/product/B0B72GV3K3/) |
| Pico 2 W | 1 (no pins) | $13 / unit | [https://www.amazon.com/gp/product/B0DPF9N1MN](https://www.amazon.com/gp/product/B0DPF9N1MN) |

Notes:

- You must get a Pico with "W" in its name. The "W" stands for "wireless". The Picos without the "W" lack the wireless module needed for the wireless connection! The "H" doesn't matter, though most of the boards with pins are also "H".
- There is no difference between the Pico W and the Pico 2 W. Both work identically for this project. The Pico 2 is newer and $1 more expensive. This project is unaffected by Pico 2 errata RP2350-E9.

Unlike other controllers, we ***strongly*** recommend the ones with pins for the sole reason that it becomes much easier to do [UART Mode](Controller-PicoW-UART.md) in the future. We only recommend the pinless boards if you either never intend to do UART mode, or if you have another way to connect to the holes (such as soldering, mini-grabbers, hammer headers, etc...)

**A micro-USB  cable:**

- Micro-USB -> USB-A Adapter: [https://www.amazon.com/gp/product/B09FXJD61Z](https://www.amazon.com/gp/product/B09FXJD61Z)
- Micro-USB -> USB-A Cable: [https://www.amazon.com/Android-Compatible-Smartphones-Charging-Stations/dp/B095JZSHXQ](https://www.amazon.com/Android-Compatible-Smartphones-Charging-Stations/dp/B095JZSHXQ)

### Hardware Assembly:

Should be pretty self-explanatory:

1. Connect the Pico W to your computer using the USB cable.
2. Place the Pico W near your Switch. (within 3ft line-of-sight for maximum stability)

And that's it!


## Software Setup

### Step 0: Getting Ready

Make sure you have everything else setup so that it looks like this:

<img src="../Images/GeneralSetup-CC.png">

If not, you should go back to the [general setup guide](../index.md) and start over.

### Step 1: Flash the firmware to the Pico W.

1. Unplug the Pico W from your computer.
2. Press and hold the white `Bootsel` button.
3. Plug the Pico W back into your computer while holding the `Bootsel` button. You can now release the button.
4. Go to "This PC" and look for a storage device:

     - On the Pico W(H), it will be named `RPI-RP2`.
     - On the Pico 2 W(H), it will be named `RP2350`.

5. Drag and drop one of the following files into that storage device. Once the copy is done, the device will disappear.

     - Pico W(H): `PABotBase-Pico1W-2025092300.uf2` (version number may vary)
     - Pico 2 W(H): `PABotBase-Pico2W-2025092300.uf2` (version number may vary)

<img src="../Images/PicoW/ControllerSetup-PicoW-Flash1.png">

### Step 2: Navigate to the Grip Menu

The Grip menu is the only place where a controller can wirelessly pair with the Switch.

To get there from the Switch Home screen: `Controllers` (button next to the Settings gear) -> `Change Grip/Order`

<img src="../Images/GripMenu3.png">

### Step 3: Connect the Pico W to the Computer Control program

1. At the top for the "Controller" option, click the dropdown and select `Serial: PABotBase` (should be on this since this is the default)
2. In the next dropdown, select your serial device. On Windows it will be something like `COM3`.

If you don't see the device in the dropdown, you probably need to refresh it (especially if you kept the program open since Step 0). You can refresh the list by clicking "Reset Ctrl".

If everything worked correctly, it will look like this:

<img src="../Images/PicoW/ControllerSetup-PicoW-USB-Connected-Cropped.png">

### Step 4: Connect the Pico W to the Switch

In the 3rd dropdown, choose "NS1: Wireless Pro Controller".

After a few seconds, you should see a controller pop-up in the Grip menu on the Switch. If not, try rebooting the Pico W by pressing the `Bootsel` button or be unplugging and replugging it.

The controller colors are randomized and should match the color icons in the status indicator. This helps to distinguish controllers if you have multiple of them. You can change the colors in the `Nintendo Switch -> Framework Settings` menu.

<img src="../Images/PicoW/ControllerSetup-PicoW-USB-Ready-Annotated.png">


### Step 5: Test the connection

You can control your Switch from the keyboard. Click on the video display to activate the keyboard controls. Then try pressing some buttons. You can view the keyboard -> controller mapping by clicking on the "keyboard layout" at the bottom left corner of the program.

The default keyboard layout is the English QWERTY layout. If you have a different layout, you can change the mappings in `Nintendo Switch -> Framework Settings` and scroll down to the controller mapping tables.

We recommend familiarizing yourself with the keyboard controls as this is the preferred way to control your Switch while setting up to run a program. Each controller type has a different keyboard mapping. By default, the joystick (left joystick for Pro Controller) is mapped to the usual WASD setup that's used in FPS games. For joycons, there are two sets of mappings (using different keys) that will serve both vertical and sideways orientations.

Overall, the idea here is that you can play your Switch from your computer. While it's not as nice as using a native controller, it is good enough to easily setup programs - especially if you're doing this remotely where you do not have physical access to the Switch.

<img src="../Images/PicoW/ControllerSetup-PicoW-USB-Controls.png">

**Controller Types:**

You will notice that there are 4 controller options:

- None
- Pro Controller
- Left Joycon
- Right Joycon

"None" simply idles the Pico W and turns off its antenna so it isn't trying to connect to a Switch. The others tell the Pico W to act as that controller respectively. 

Every time you press "Reset Ctrl" or change the controller type, it will disconnect from your Switch and try to reconnect using the new controller type. If the new controller has not been previously paired with the Switch, you will need to be in the Grip menu for the new controller to pair. See [Pairing Behavior](#pairing-behavior).

Changing programs (or even closing the application entirely) will not disconnect the Pico W from the Switch. When you load a program and connect to the Pico W, it will automatically continue its previous connection to the Switch (and change the controller dropdown accordingly).

**Connecting as a Joycon:**

When you connect as a joycon, it will behave like a normal joycon. It doesn't immediately connect and wants you to either pair with a 2nd joycon or press SL+SR to put it into horizontal mode.

For the right joycon, you can press the Home button to immediately leave the grip menu. This will let you easily start LGPE programs which use the right joycon. The left joycon doesn't have this option and will require you to either pair with a right joycon or to enter horizontal mode. There are currently no programs that use the left joycon.

To enter horizontal mode, you can press SL+SR on the keyboard controls by pressing F1 and F3 at the same time. This will let you exit the grip menu and enter a game like LGPE that requires a joycon. But keep in mind that this will also rotate the controls by 90 degrees (IOW, confusing). Check the keyboard mapping for both vertical and horizontal joycon orientations.

*You cannot easily pair two Pico W joycons anyway since you need to press L+R on them simultaneously and the keyboard controls don't allow you simultaneously press buttons on different controllers. However, you can easily pair a Pico W joycon with a real joycon.

### Step 6: You are done!

If keyboard commands are working (along with video and audio), you are done!

Try clicking on other programs on the sidebar. You will find that all of them are "virtual consoles" that will accept keyboard commands. At the top of every program is a link to the wiki that explains how to setup and use that program.

Continue on to [Finishing Up](../index.md#step-4-finishing-up)!


## Pairing Behavior:

Once you connect the Pico to the Switch, it will remember its pairing state with that Switch. Each wireless controller has a separate pairing state. So pairing one will not automatically pair the others.

Keep in mind the following behaviors:

- When you switch from a different controller to a wireless controller that was previous paired, it will reconnect to the same console it is paired with.
- When you click "Reset Ctrl", it will disconnect and try to reconnect to the console that it was paired with.
- When you SHIFT + click "Reset Ctrl", not only does it reset, it will clear the pairing state and try to pair with a new console.
- The Pico will forget its pairing state when it loses power. So unlike a real controller, it is not stored in non-volatile memory.

Once a Pico controller is paired with a console, it will be able to reconnect outside of the grip menu.


## Troubleshooting:

### Wireless Interference with Multiple wireless devices.

This is the same with all the wireless controllers (ESP32, Pico W, etc...)
If you have multiple of them, spread them out to reduce wireless interference.

As tempting as it may be, do not do this:

<img src="../Images/ESP32/ControllerSetup-ESP32-WROOM-WirelessInterference-0.jpg" width="450"> <img src="../Images/ESP32/ControllerSetup-ESP32-WROOM-WirelessInterference-1.jpg" width="450">

It is as cute as it is stupid, and it will give you problems. We tried it so you don't have to!





<hr>

**Credits:**

- Kuroneko/Mysticial

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)
















