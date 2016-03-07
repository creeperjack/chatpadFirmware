# -chatpadFirmware
Firmware for XBOX360 chatpad, it's a small keypad normally mounted on XBOX360 game controllers for chat. It features quite complete keyboard and has backlight.<br>
It can be used 'as is' but keys not correspond to letters and it should be used with a complex library to get around the limitations. There's also some limitations about backlight and serial speed.<br>
This firmware mod will allow:<br>

- Backlight selectable from serial, autofade with timer also available.
- Correct char map, no need of conversion and library, work 'as is'.
- works with any processor with TTL (3V3) level serial, initial at 9600baud.

Chatpad uses PIC16F883 with internal xtal at 4Mhz, I have used MPLAB to rewrote firmware, PICkit3 programmer(clone) and some wire soldered, I will provide exact where and how, eventually I can provide the chatpad already programmed (black version), I have several unit here from an ebay auction brand new.<br>

commands recognized by chatpad (preliminary):<br>
- 0: turns OFF chatpad backlight
- 1: turns ON chatpad backlight DIMMED 80%
- 2: turns ON chatpad backlight DIMMED 50%
- 3: turns ON chatpad backlight DIMMED 30%
- 4: turns ON chatpad backlight full
- 5: turns AUTOFADE on
- 6: return * (for testing)
To be continued...
