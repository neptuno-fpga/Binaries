# VIC-20(*)
--------------------------------------------------
### Core ported by @Neurorulez

####Source: https://github.com/neurorulez/VIC20_MiST/tree/updated

#### Features:
------------------------------------------------------
Based on The Replay Board code
3k RAM Expansion at $0400
8k/16k/24k RAM packs from $2000
Read-only or writeable CART memory at $a000
Joystick support
PAL/NTSC Display (with optional scandoubler for VGA monitors and YPbPr component output)
PRG/CART loading
1541 Disk Drive support
CART/PRG loading
CRT and PRG files usually has the load address in the first two bytes. If a particular file doesn't contain this address, you can load it to the default $a000 via choosing 'CRT with load address: No' option in the OSD menu. Loading a cart to the $a000 location will auto-reset the core, so it'll start automatically. If you have a multi-part cartridge, then first load the part which doesn't load to $a000. Also don't forget to enable 8k ROM option for cartrdiges!

RAM expansions
The core supports from the orginal unexpanded (5k RAM) machine to a fully extended one (total of 40k RAM). Unfortunately not all games supports all expansion modes, so you have to figure out what a particular game requires.

RAM map:
3k Extension: $0400
8k+ Extensions: $2000, $4000, $6000
8k ROM/RAM: $a000
ROM file:
A VIC20.ROM file is mandatory at the root of the SD Card. The file format is: 1541 (16k) + Kernal PAL (8k) + Kernal NTSC (8k) + Basic (8k) + Char (4k).

#### Keys:
-------------------------------------------------------------------

F9 - Tape start/stop
F10 - Reset
RShift + F10 - Reset with cart unload
F11 - Restore

Download pre-built binaries:
https://github.com/mist-devel/mist-binaries/tree/master/cores/vic20

Source code:
https://github.com/gyurco/VIC20_MiST

-------------------------------------------------- -
### License


This program is free software: you can redistribute it and / or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.