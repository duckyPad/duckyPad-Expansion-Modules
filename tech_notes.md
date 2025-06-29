# duckyPad Expansion Module (DPEM) Communication Protocols

[Get duckyPad Pro](https://www.tindie.com/products/37399/) | [Official Discord](https://discord.gg/4sJCBx5) | [Project Page](https://github.com/dekuNukem/duckyPad-Pro)

-----------

## Hardware Description

Each DPEM has **two USB-C ports** for daisy-chaining:

* One for **Towards-duckyPad (TD)** communication.

* The other for **Away-from-duckyPad (AFD)** communication.

DPEM talks to each other using standard **TTL serial**:

* 115200 8N1

* The D+ and D- lines carry TX and RX signals

Microcontroller is STM32F042F6P6:

* Monitors 8 input channels

* Negotiates with neighbouring devices

* UART1 for TD, UART2 for AFD.

## Global Channel ID (GCID)

A DPEM has 8 channels, each of which has a unique GCID.

The GCID of a DPEM's **first channel** is its **Start ID**.

* The DPEM closest to duckyPad has a Start ID of 0, with GCID from 0 to 7.
* The next DPEM has Start ID of 8, with GCID from 8 to 15.
* And so on, up to 32 channels total.

## Packet Format

DPEM uses simple **1-byte** data packets to communicate.

* Top 2 bits: **Command Type**.

* Lower 6 bits: **Payload**.

```
 7 6 5 4 3 2 1 0
+---------------+
|CMD|  PAYLOAD  |
+---------------+
```

| CMD | Description                  | Direction             |Payload|
| ------- | ------------------------ | --------------------- | ------ |
| 00  | `Ask Start ID`       | TD | Firmware Version|
| 01  | `Assign Start ID`    | AFD | Start ID|
| 10  | `SW Pressed`   | TD        | GCID|
| 11  | `SW Released` | TD        | GCID|

## ID Assignment

DPEM powers up in **uninitialized** state.

* It periodically sends `Ask Start ID` to TD.

* TD replies with `Assign Start ID`.

* Now this DPEM has a start ID and is **initialized**.

## Event Handling

Once initialized, DPEM monitors the **channel status** and **AFD activity**.

* When **one of its own channels** changes state, it sends `SW Pressed` / `SW Released` to TD.

* When `SW Pressed` / `SW Released` is received from AFD, it is passed as-is to TD.

* When `Ask Start ID` is received from AFD, it replies with `Assign Start ID`, which is its `last_channel_ID + 1`.

## Questions or Comments?

Please feel free to [open an issue](https://github.com/dekuNukem/duckypad-pro/issues), ask in the [official duckyPad discord](https://discord.gg/4sJCBx5), or email `dekuNukem`@`gmail`.`com`!
