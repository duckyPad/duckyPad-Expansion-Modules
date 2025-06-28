# duckyPad Expansion Module

[Get duckyPad Pro](https://www.tindie.com/products/37399/) | [Official Discord](https://discord.gg/4sJCBx5) | [Project Page](https://github.com/dekuNukem/duckyPad-Pro) | [Table of Contents](#table-of-contents)

--------------

duckyPad Expansion Module lets you wire up external **switches / buttons / foot pedals** to your duckyPad Pro.

* **8 Channels** Per Module

* **Daisy-Chain** up to 32 Channels

* USB-C Connector

![alt_text](resources/photos/expdpp.jpeg)

![alt_text](resources/photos/exp.gif)

## Table of Contents

- [Kit Assembly](#kit-assembly)
- [Connection Overview](#connection-overview)
	- [Terminal Block](#connection-terminal-block)
	- [3.5mm Audio Jack](#connection-35mm-audio-jack)
	- [Pin Headers](#connection-pin-headers)
- [Key Test](#key-test)
- [Configurator](#configurator)

## Kit Assembly

* **Wash your hands first** to discharge static electricity

You should have the following parts:

![alt_text](resources/photos/items.png)

Insert the `8mm Screws` in `Bottom Plate`:

![alt_text](resources/photos/bottom.jpeg)

Place **something rigid** against the back, and flip over.

The screws should stay in place.

Put on **2.5mm Nylon Spacers**.

![alt_text](resources/photos/nylon.jpeg)

Insert the `Circuit Board`.

Then the `8mm Metal Spacer`

* **Moderately tighten** with a socket bit if available

* Avoid scratching the PCB or nearby components.

![alt_text](resources/photos/spacer.jpeg)

Leave the `Top Plate` off for now.

You can install it after everything is wired up.

## Back to duckyPad!

If you're just starting, **set up your duckyPad first by [following the User Guide](https://dekunukem.github.io/duckyPad-Pro/doc/getting_started.html)**

Play with scripts on built-in switches and encoders, continue here once familiarised.

## Connection Overview

**8 Channels** are available per module.

* Numbered 1 to 8
* A channel is **considered active** when it is **shorted to ground (GND)**.

Therefore, to wire up a switch, you just need to:

* Connect **one side** to **GND**
* And the **other side** to the **desired channel**

---------

You can make connections via:

* Terminal Block
* 3.5mm Jack
* Pin Headers

## Connection: Terminal Block

Take a look at the `terminal block`:

![alt_text](resources/photos/block.jpeg)

Contains **Channel 1 to 7** and **GND**

To wire up a switch, connect it between a channel and GND.

-------

As an example, here's a simple button with two wires:

![alt_text](resources/photos/push.jpeg)

* When not pushed, the wires are isolated.
* When pushed, they are **connected together**.

Therefore, we just need to attach one wire to GND, and the other to a channel.

* Flip up the lever for GND and the desired channel

![alt_text](resources/photos/flip.jpeg)

* Strip around half inch / 1.2cm of conductor
* Insert into the hole
* Flip lever back down

![alt_text](resources/photos/inserted.jpeg)

## Connection: 3.5mm Audio Jack

Two 3.5mm TRS (Tip, Ring, Sleeve) connectors are available.

Sleeve is connected to GND.

Tip and Ring are connected to channels shown below.

![alt_text](resources/photos/jack.png)

## Connection: Pin Headers

All channels are also available on pin headers.

You can install a header or solder wires directly to them.

![alt_text](resources/photos/header.png)

## Key Test

Use a USB-C cable and connect the module as shown.

* Make sure the `Towards duckyPad` marking faces duckyPad

* The other end is used for daisy-chaining

![alt_text](resources/photos/usbc.png)

Press the `Key Test` script in `Welcome` profile

![alt_text](resources/photos/home.png)

Press a built-in switch, the screen should respond.

Then activate a channel on the expansion module.

The corresponding LED should light up:

![alt_text](resources/photos/led.png)

The screen should show too:

![alt_text](resources/photos/test.jpeg)

If so, congrats! Your wiring is correct.

## Configurator

You can assign actions to expansion channels just like any other key.

Module 1 is closest to duckyPad, up to 4 can be daisy-chained.

![alt_text](resources/photos/config.png)

Some notes:

* If using a flip switch, select `Disable Auto-Repeat`.
* So the script doesn't repeat after changing state.

![alt_text](resources/photos/repeat.png)

* Each channel can have different scripts for `onPress` and `onRelease`.
	* `onPress` is when a channel goes from inactive to active
	* `onRelase` is the opposite

![alt_text](resources/photos/on.png)

## Communication Protocol

[See this page](tech_notes.md)

## Questions or Comments?

Please feel free to [open an issue](https://github.com/dekuNukem/duckypad-pro/issues), ask in the [official duckyPad discord](https://discord.gg/4sJCBx5), or email `dekuNukem`@`gmail`.`com`!
