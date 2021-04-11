# Videopac G7000 / Odyssey2 for FPGA. 

## Ramon Martínez @rampa069 ported for Neptuno and Unamiga Reloaded by Neuro.

Thanks to:
René van den Enden Videopac guru. helped us via email and posted lots of information on videopac.nl
Mejias3D Support on videopac internals and 8048 assembler programming.
avlixa For the ZXDOS port.
Antonio Sanchez For the LX16 port.
Wilco2009 For the SD-cart for the real console and for helping with hardware internals and tricks his sd cartridge for the real console is a must!.
Neuro For the Neptuno and Unamiga reloaded Ports.
Benitoss for the ZX Next port (soon)

Fuentes:  https://github.com/RW-FPGA-devel-Team/Videopac-G7000

![Magnavox-Odyssey-2-Console-Set](https://user-images.githubusercontent.com/31018768/106388338-4ff0c200-63de-11eb-9ed3-aa8d39326e83.jpg)

This is an FPGA implementation of the Magnavox Oddysey2/Videopac G700 based on FPGA videopac by Arnim Laeuger and ported to MiSTer (With additional work from wsoltys) by Jamie Dickson.
Features
Switch between Odyssey2 and Videopac mode.
Switch between two palettes (composite RF emulation and RGB for more vivid colours)
Fully working keyboard.
Joystick buttons for keys 0-9.
loadable VDC ROM charset for some custom roms. For information, how-to prepare them and examples read the manual. Also have some ready to use custom roms.
Correct Sound, timings and better collision detection.
"The Voice" peripheral.
available on:
MiSTer
MiST
SiDi
Neptuno
Unamiga Reloaded
ZxDOS
ZX Next (Soon)
Installation
Copy the *.rbf file to your SD card. Create an Videopac folder on the card, and place Odyssey2/Videopac roms (*.BIN) inside this folder. XROM dumps (at the moment only known Musician and 4 in a row) must be renamed to *.rom.

When loading a ROM, most games will prompt the user with "SELECT GAME". Press 0-9 on the keyboard or mapped controller button to play the game. Unfortunately, there is no on-screen display of the game options, so looking at the instruction manuals may be helpful in selecting a game. Note that the system did not have a well defined player 1 or player 2 controller, they would alternate on a game-to-game basis. You may need to swap controllers to use the input.

Known Issues
Still a few graphic glitches.

License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.


