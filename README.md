# Raspberry Pi Pico SDK Examples

## Getting started

See [Getting Started with the Raspberry Pi Pico](https://rptl.io/pico-get-started) and the README in the [pico-sdk](https://github.com/raspberrypi/pico-sdk) for information
on getting up and running.

### First  Examples

[blink](blink) | Blink an LED on and off. | https://rptl.io/pico-blink

### Flash

App|Description
---|---
[nuke](flash/nuke) | Obliterate the contents of flash. An example of a NO_FLASH binary (UF2 loaded directly into SRAM and runs in-place there). A useful utility to drag and drop onto your Pico if the need arises.

### Pico Board

App|Description
---|---
[blinky](picoboard/blinky) | Blink "hello, world" in Morse code on Pico's LED
[button](picoboard/button) | Use Pico's BOOTSEL button as a regular button input, by temporarily suspending flash access.
