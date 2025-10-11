# Video Fast Code Entry (V-FCE)

**Related Programs:**
- [Fast Code Entry (FCE)](FastCodeEntry.md)
- [Clipboard Fast Code Entry (C-FCE)](ClipboardFastCodeEntry.md)
- [Video Fast Code Entry (V-FCE)](VideoFastCodeEntry.md) (this program)

<img src="../images/VideoFastCodeEntry-0.png">

## Program Description

Yet another improved version of the [Fast Code Entry](/Wiki/Programs/PokemonSwSh/FastCodeEntry.md).

This FCE uses text recognition to read the link code from a part of your screen. Thus this program no longer requires a copy-pasteable code.

This program is useful for fighting your way into extremely busy hosting streams (like on Twitch or Discord) where there are hundreds of other people competing to enter a raid.

Be aware that Video FCE is not for everyone. It is annoying to setup and will likely require a fast computer with two high resolution monitors. But once setup and calibrated, Video FCE is faster than the Clipboard FCE since you no longer need to double-click + CTRL-C. A single click is all that's needed for V-FCE to enter a raid.

As with all FCE programs, the usual disclaimer applies:

***By using this program, you agree that you are an asshole. Furthermore, you will be required to embrace your asshole status by flaunting it in front of all the people you've blocked out of raids.***


### Setup of Settings

None

### Instructions

- The code entry pad must be up.
- The cursor must be over the "1" digit.
- The code must be clearly visible and large. If you are watching a stream, full screen it. If you are watching a Discord channel, open it in a browser and set the magnification to maximize the size of the screenshot containing the code.
- The box coordinates are properly setup and include only the raid code. (must be clearly visible with black text on light background)
- Start the program.


## Options

### Capture Box

- **Monitor Index:** For multi-monitor setups, this lets you choose which monitor to watch.
- **X Coordinate:** The left edge of the box to watch. 0.0 is the left edge of the monitor. 1.0 is the right edge of the monitor.
- **Y Coordinate:** The top edge of the box to watch. 0.0 is the top edge of the monitor. 1.0 is the bottom edge of the monitor.
- **Width:** The width of the box to watch. The number is between 0 and 1 and is the proportion of the full width of the monitor.
- **Height:** The height of the box to watch. The number is between 0 and 1 and is the proportion of the full height of the monitor.


### Mode

- **Manual** - Enter code when you start the program.
- **Automatic** - Monitor the region. Automatically enter code when it appears.

The default mode is "Manual" which will read the code and enter it when you start the program.

In "Automatic" mode, you start the program first and it will then monitor the capture box. As soon as it sees a valid code, it will enter it. Thus it automates entering a raid with no human interaction. On a fast computer, the reaction time is about ~2ms which is much faster than the 200ms+ reflex time of a human seeing the code and clicking "Start Program".

***Warning: Using automatic mode on a live-hosting channel is risky because it is easy to accidentally join the wrong raid. On servers (like PA and SHA) that enforce catch limits, you can easily get yourself banned if you accidentally go over.***

### Skip Initial Code (new to v0.41.8)

If there is already code visible when you start the program, ignore it until the capture box changes.

This lets you skip an existing code that is already on the screen because it is probably old and expired. This is useful for live hosting channels on Discord where the codes remain static until replaced by a new post with a new code.

## Credits

- **Author:** Kuroneko/Mysticial
- **Concept:** SakuraKim (from the original Sword/Shield FCE)

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)


