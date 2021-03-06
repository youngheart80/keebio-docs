# Frequently Asked Questions


## Flashing

- Do I need to have the TRRS cable plugged in while trying to flash both halves?
    - Having the TRRS cable plugged in while flashing has zero effect on flashing. Having it plugged in will not flash both halves at the same time.
Flashing does not occur over the TRRS cable, so it does not matter if the TRRS cable is plugged in or not while flashing. Each half needs to be plugged in individually to the USB port to be flashed.
- When I flash the right side by itself, I get the left side, but mirrored. Is something wrong?
    - Nope, this is perfectly normal!
    - Here's the explanation why:  
        - Unless you explicitly do `#define EE_HANDS` in your keymap \(this is not the default\), QMK automatically assumes that whatever half the USB cable is plugged into is the left hand board. Even flashing the .eep files in this case does nothing, as it's ignored unless `EE_HANDS` is explicitly set.
        - So when you plug in the right board itself, it thinks it's the left one. The reason it's flipped is because the PCB has been physically flipped compared to the actual left board.
        - When you plug the TRRS cable in, the right side now auto detects correctly as the right side, and the firmware also knows to flip the board.

## Building

- What's the pinout of the ICSP header on some of the PCBs?

    ![](/assets/ICSP_header.png)

- Which way do I orient the diodes?
    - For all of the boards made by Keebio, the band on the diode (the cathode) is always associated with the square pad. On most boards, the square pad is pointing towards the bottom. For some PCBs that support Kailh Low-Profile switches, the square pad may be pointing towards the top.
    - **Simple rule to remember:** Band = Square Pad
- Which way do I orient the resistors?
    - Resistors have no polarity, so the direction they are installed does not matter
- Do any of the PCBs have individually addressable LEDs?
    - No, the PCBs that do have LED support can only be controlled as a group
    - One option around this is to use a switch with clear housing like a Zealio or Alias switch and point RGB LEDs upwards through the switch
- Which in-switch LEDs are compatible?
    - Compatible sizes: 1.8mm, 2x3x4mm, or 3mm, note that sometimes the 3mm LEDs can interfere with the keycaps
- Which RGB LED strips are compatible?
    - WS2811 and variants (WS2812, WS2812B, WS2812C, etc.)
    - SK6812

## Miscellaneous

- Will you be making the PCB files available for download?
    - No, the PCB files will not be made available except for the Rorschach
- How do I contribute to the documentation here?
    - The repository for this website can be found here: [Keebio Docs on GitHub](https://github.com/keebio/keebio-docs/), we welcome any pull requests
