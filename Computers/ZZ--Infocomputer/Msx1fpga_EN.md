# Msx1Fpga + I2S (*)

### Core ported by Jose Manuel @delgrom | https://github.com/fbelavenuto/msx1fpga

### (*) An extra Addon is necessary, you can purchase it here [Antonio Villena Store] (https://www.antoniovillena.es/store/)

![MSX-Hit_Bit_HB-75P] (https://user-images.githubusercontent.com/31018768/71131502-2b934f80-21f5-11ea-99fc-b63d1a5d30c3.jpg)

MSX1 cloned in FPGA

This project is an MSx1 cloned to FPGA, with some parts of the OCM project

### Changelog
12/19/2020 I2S support for addon UDA1334A

##### Characteristics:

Multiple plates

MSX1 50Hz or 60Hz

Configurable RAM Mapper size

128K Nextor (MSX-DOS2 evolution) ROM with SD driver

Megaram SCC / SCC + of the OCM project (configurable size)

Configurable keyboard map

15 / 31KHz selectable

Selectable scanlines

There is a loader (IPL) to boot and load the ROMs and configurations from the SD.


##### Instructions for use:

Format an SD in FAT16 format (maximum 4gb), unzip the file 'msx1_sd_files.zip' in the root of the SD.

Function keys:

Print Screen: VGA // 15KHZ

Scroll Lock: Scanlines modes

Pause / Break: 50/60 Hz Vertical Frequency

F11: Turbo mode

CTRL + ALT + DEL: Soft Reset

CTRL + ALT + F12: Hard Reset

CTRL + ALT + BACKSPACE: For ZX-Uno only: FPGA reload;

Left ALT: MSX GRAPH Key;

Right ALT: MSX CODE Key;

Page Up: MSX SELECT Key;

END: MSX STOP Key.

The joystick port is mapped as JooyMega, and configured to use a SEGA Genesis / Megadrive joypad.

To go to BASIC from MSX-DOS you have to execute the BASIC command

To go to MSX-DOS from BASIC, CALL SYSTEM must be executed.

##### NOTES:

In BASIC use the "CTRL + STOP" keys to stop the execution of a program. The MSX STOP key is mapped to the END key of the PC.
To change the video mode from 50HZ to 60HZ, and play PAL games at the correct speed, such as "Invasion of the Monsters
Zombies ", for VGA you have to use the" DISPLAY.COM "program, you can download it from this thread (https://www.msx.org/forum/msx-talk/software/dos-tool-to-switch-from -50-to-60hz).

SOFTWARE LOAD:
A.- .ROM files
They are dumps of programs in cartridges.

Use the SROM.COM utility to load the ROMs. Ex: SROM NEMESIS1.ROM

B.- .DSK files
They are program dumps on floppy disks.

Use the SRI.COM utility to emulate a disk. Ex: SRI GAME.DSK

C.- .CAS files
They are images with the content of audio tapes. The way to use them is very well explained in the article "Load CAS files with MegaFlashROM and an MSX-2" (https://programbytes48k.wordpress.com/2015/11/19/cargar-archivos-cas-con-megaflashrom- y-un-msx-2 /).

The LOADCAX and LOADCAXX files are located in the BIN folder of the floppy disk http://www.msxcartridgeshop.com/bin/ROMDISK.DSK of the MegaFlashROM SCC + SD.

D.- .BAS files
They are BASIC programs that can be recorded on the SD, and also loaded and executed. From BASIC we can type:

SAVE "TO: HOLA.BAS"
to record a program, and with

LOAD "A: HOLA.BAS"
get it back.

To know the differences between the CSAVE, BSAVE and SAVE commands, and other commands to store and retrieve information, you can consult this section (https://www.msx.org/wiki/Category:Disk_BASIC) with the Disk BASIC commands of the wiki from msx.org (https://www.msx.org/wiki/).

To load a .BAS file from Nextor-DOS, simply type its name with or without an extension and press ENTER.

E.- AUDIO input
The core allows the loading of audio programs. The way to do it is through the following BASIC commands:

RUN "CAS:"
or better:

BLOAD ”CAS:”, R
or better:

LOAD ”CAS:”, R
Don't forget to disable TURBO to load real K7 audio.

This is perfectly explained in the article "How to load programs in MSX" (https://programbytes48k.wordpress.com/2012/01/04/como-cargar-programas-en-msx/).

In the forum of (http://www.vintagenarios.com/hilo-oficial-wavs-msx-t1997.html) Vintagenarios you can find many MSX programs in WAV format and load them via audio.

### License


This program is free software: you can redistribute it and / or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.
