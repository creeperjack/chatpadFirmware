# XBOX chatpad alternative Firmware
Firmware for XBOX360 chatpad, it's a small keypad normally mounted on XBOX360 game controllers for chat. It features quite complete keyboard and has backlight.<br>
It can be used 'as is' but keys not correspond to letters and it should be used with a complex library to get around the limitations. There's also some limitations about backlight and serial speed.<br>
This firmware mod will allow:<br>

<b>ATTENTION:</b> This works >ONLY< with the original 'Microsoft' chatpad, NOT the chinese clone!!!! In ebay there's a lot of chinese clone, you have to be sure it's Microsoft or you'll get a piece of junk1<br>

- Backlight selectable from serial, autofade with timer also available.
- Correct char map, no need of conversion and library, work 'as is'.
- works with any processor with TTL (3V3) level serial, initial at 9600baud.

Chatpad uses PIC16F883 with internal xtal at 4Mhz, I have used MPLAB to rewrote firmware, PICkit3 programmer(clone) and some wire soldered, I will provide exact where and how, eventually I can provide the chatpad already programmed (black version), I have several unit here from an ebay auction brand new.<br>

commands recognized by chatpad (preliminary):<br>
- 0: turns OFF chatpad backlight
- 1: turns ON  chatpad backlight DIMMED 80%
- 2: turns ON  chatpad backlight DIMMED 50%
- 3: turns ON  chatpad backlight DIMMED 30%
- 4: turns ON  chatpad backlight full
- 5: turns AUTOFADE on
- char 0x9E: enable keypad config
- char 0x9F: disable keypad config
- 6: return * (for testing)<br>

currently features planned for version 1.0:<br>
- Debounce to prevent multiple outs. (DONE)
- Standard ASCII plus extended one, no need of any library.(DONE)
- 4800 baud to 115200 baud communication. (DONE)
- Uses only 2 wires (plus supply), 1 wire if you don't need control backlight. (DONE)
- Backlight with Fade Out and other modes controlled by serial, autofade on at startup. (DONE)
- Automatic Sleep function with serial wakeup. (DONE)
- Special chars for <- ->, for easy use in microcontrollers. (TODO)
- Configuration mode from keypad (disable dy default) enabled by serial, will be saved in EEPROM. (DONE)
- Any special button will not trasmitted to output as the original. (DONE)
- 8Mhz instead of 4Mhz. (DONE)
- Very low sleep mode, Sleep mode already in but this will allow tiny consume. (TODO)
- Written almost entirely in assembler.<br>

 What you need:<br>
 Of course an XBOX 360 chatpad, it's easy to find on ebay for very low price. Tou need also a PIC programmer, I have used 
 a USB PICKIT3 chinese clone very cheap, you will need also the Atmel Programming Environment v.3.26 that it's free downloadable from Microchip. First you have to disassemble the chatpad (figure will coming) and solder some wires to connect the programmer and set for PICF883, set the programmer VDD (by entering in advanced mode, pass 'microchip') at 3.25V, press 'connect', select my firmware and press 'program'.<br>If everithing goes right and no errors, you have to disconnect programmer and connect the 4 wires of the original cable as follow:<br>
 
  - RED(+3V3),
  - TRASPARENT(GROUND),
  - BLACK(to RX of your microcontroller), 
  - MAROON(to TX of your microcontroller),
 
 create a simple sketch where you can confirm that chatpad it's working correctly (press 1 should be 1 on your microcontroller and so on).<br><br>

To be continued...
