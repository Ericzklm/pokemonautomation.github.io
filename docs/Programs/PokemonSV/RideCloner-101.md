# Ride Cloner (v1.0.1)

***This program relies on a glitch that was patched out in 1.1.0. It can only be used on versions 1.0.0 and 1.0.1.***

<img src="images/RideCloner-0.png">

## Program Description

If you're just cloning items, you can use this program to set it up. But there is a [faster program](CloneItems-101.md) for that.

This program automates the legendary cloning part of this video: [https://www.youtube.com/watch?v=3XHD_Cqw9Rk](https://www.youtube.com/watch?v=3XHD_Cqw9Rk)

So this program will clone your ride legendary into your boxes. You will need to run [Mass Release](MassRelease.md) to clean them up (which also automatically detaches the items from them).

This program catches Pokémon the same way as the [Tera Farmer](TeraSelfFarmer.md). It day skips in front of the Tera crystal until one spawns, then it beats the raid, catches the Pokémon and inserts it in your party replaying your ride legendary. This program will also check shininess of the raid Pokémon and thus can be used to simultaneously shiny-hunt for hostable shiny raids.


---

### Setup of Settings

**Switch Settings:**

1. Screen size: Must be 100% within the Switch settings
2. [Switch 2: The profile you are using must be the 1st (left-most) profile.](/Wiki/Programs/NintendoSwitch/Switch2Notes.md#resetting-a-game-moves-the-cursor-to-the-1st-user-profile)
3. System Time: Unsynced

**Program Settings:**

1. Video Resolution: 1080p or higher

**Game Settings:**

1. Text Speed: Fast
2. Give Nicknames: Off
3. Send to Boxes: Manual

### Instructions

1. You are standing exactly* on the north side of a Tera crystal.
2. You are facing directly south looking at the Tera crystal.
3. You are safe from being attacked by wild Pokémon.
4. Your lead Pokémon should be able to reliably beat raids by spamming its first move. Pick a move that is strong and has few types resistant to it.
5. Your ride legendary is already holding the item you wish to clone.
6. Your ride legendary** is not in the party.
7. Your party has 5 or 6 Pokémon.
8. Start the program in game.

*This is a more extreme case of the Tera Farmer. After completing a raid, your character will rotate to face south. Thus if you aren't already facing south, the crystal spawns may no longer be in front of you. As an extra complication of the Ride Cloner, each time you mount and dismount your ride legendary, you move forward slightly. After about a dozen raids, you will have moved "through" the entire crystal such that you are no longer facing the crystal. To counter-act that, the program will periodically move backwards and forward to keep you on the north end of the crystal. But for this to work correctly, you need to be well aligned to the north end of the crystal.

**If you move your ride legendary to your party and give it an item, it will not retain the item. You first need to mount it (move it out of your party) before it actually "saves" the item. So for simplicity, we require that your ride legendary is holding the item and is not in your party. Internally, your ride legendary is stored in a separate memory location from your party members. When it's moved to your party, it is *copied* out. Thus if you attach the item, the "main" copy still does not hold it until you mount your legendary again. After performing the glitch so that your ride legendary is neither mounted nor in your party, mounting it will spawn a new one from the separate memory location. The item needs to be attached in that separate memory location for it to be cloned.



## Options

Some of these options are the same as the Tera Farmer since this is essentially just a modified version of that Tera Farmer.


### Mode:

- Mode 1: Clone only. Don't catch or shiny-check anything.
- Mode 2: Shiny Hunt: Save before each raid and catch. Stop if shiny.


### Rides to Clone:

Stop the program after cloning this many times. Make sure you have enough box space for twice this amount.

### Max Stars:

Skip raids with more than this many stars to save time since you're likely to lose. 4 star raids seem to be the limit of what can be beaten with this program.


### Ball Select:

What ball to use to catch each raid Pokémon. The program will automatically stop if it cannot find this ball. (which will happen if you run out)


### Fix Clock on Catch:

Fix the time when catching so the caught date will be correct.


### A-to-B Delay:

This is the delay between the A and B presses that activate the glitch.


## Credits

- **Author:** Kuroneko/Mysticial

<hr>

**Discord Server:** 

[<img src="https://canary.discordapp.com/api/guilds/695809740428673034/widget.png?style=banner2">](https://discord.gg/cQ4gWxN)





