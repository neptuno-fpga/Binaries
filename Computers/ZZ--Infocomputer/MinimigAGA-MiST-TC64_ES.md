# Minimig AGA
## Portado por rampa
Fuente: https://github.com/rampa069/MinimigAGA-MiST-TC64#readme

Para Turbo Chameleon TC64, MiST y otras plataformas. (Este núcleo debería ser fácilmente transportable a cualquier placa FPGA con salida VGA, entrada PS/2, tarjeta SD, unos 25.000 elementos lógicos y una SDRAM de 16 bits de ancho que soporte una disposición 13x9 para 32 megabytes de RAM).

Prólogo
minimig (abreviatura de Mini Amiga) es una reimplementación de código abierto de un Amiga utilizando una matriz de puertas programables en campo (FPGA). El autor original de minimig es Dennis van Weeren.

Amiga fue un increíble ordenador personal, anunciado alrededor de 1984, que -en su momento- superó con creces a cualquier otro ordenador personal del mercado, con avanzadas capacidades gráficas y de sonido, por no hablar de su gran sistema operativo con capacidad multitarea preventiva.

Esta variante de minimig ha sido actualizada con capacidades de chipset AGA, lo que le permite emular los últimos modelos de Amiga (Amiga 1200, Amiga 4000 y (parcialmente) Amiga CD32). Por supuesto, también es compatible con los anteriores Amigas OCS/ECS como Amiga 500, Amiga 600, etc.

Características principales soportadas
variantes de chipset : OCS, ECS, AGA
chipRAM : 0.5MB - 2.0MB
slowRAM : 0.0MB - 1.5MB
fastRAM : 0,0MB - 24MB
Núcleo de la CPU : 68000, 68010, 68020
kickstart : 1.2 - 3.2 (actualmente se admiten ROMs kickstart de 256kB, 512kB y 1MB)
HRTmon con espejo de registros personalizado
disquetes : 1-4 disquetes (soporta el formato de imagen de disquete ADF), con velocidades normales y turbo
discos duros : 1-2 imágenes de disco duro (soporta imágenes de disco entero, imágenes de partición, usando la tarjeta SD entera y usando la partición de la tarjeta SD)
estándar de vídeo: PAL / NTSC
soporta salida de video normal y escandinava (15kHz / 30kHz) - puede ser usado con un monitor o una TV con un cable SCART
periféricos : joysticks reales de Amiga / C64 conectados a los puertos de joysticks de C64, controladores de infrarrojos de CDTV, teclados PS/2, ratones PS/2, Turbo Chameleon Docking Station para joysticks adicionales o ratones reales de Amiga, y entrada/salida MIDI
soporta gráficos básicos retargeables con un controlador P96
tiene una implementación del convertidor Akiko chunky to planar
tiene un canal de audio extra que puede ser usado desde el Amiga para reproducir archivos WAV de calidad CD, o usado en algunas plataformas para emular sonidos de disquetera.
Uso
Hardware
Para utilizar este núcleo de minimig, necesitarás como mínimo una tarjeta SD/SDHC, formateada con el sistema de archivos FAT32, un teclado PS/2 y un monitor / TV compatible. Los joysticks y el ratón se pueden emular en el teclado. Probablemente querrás conectar un juego de altavoces o auriculares, un ratón Amiga real o USB y un joystick Amiga real.

Software
Para utilizar el núcleo, también necesitará un archivo de imagen Kickstart ROM, que puede obtener copiando el Kickstart ROM IC de su Amiga real, o comprando un paquete de software Amiga Forever. La imagen Kickstart debe colocarse en la raíz de la tarjeta SD con el nombre KICK.ROM. El Minimig también es compatible con el reemplazo de la ROM de arranque AROS.

El minimig puede leer cualquier imagen de disquete ADF que coloque en la tarjeta SD. Recomiendo al menos Workbench 1.3 o 3.1 (AmigaOS), algunos de los grandes juegos de Amiga (recomiendo Ruff'n'Tumble) o algunas de las increíbles demos de la vasta demoscene de Amiga (como State of the Art de Spaceballs).

El minimig también puede utilizar imágenes de disco duro HDF, que se pueden crear con WinUAE.

Configuración recomendada del minimig
para juegos / demos de ECS : CPU = 68000, Turbo=NONE, Chipset=ECS, chipRAM=0.5MB, slowRAM=0.5MB, Kickstart 1.3
para juegos AGA / demos : CPU = 68020, Turbo=NONE, Chipset=AGA, chipRAM=2MB, slowRAM=0MB, fastRAM=24MB, Kickstart 3.1 Para el uso de Workbench, puedes probar a poner TURBO=BOTH para aumentar un poco la velocidad.
Control de minimig
Teclas especiales del teclado:

F12 - menú OSD
F11 - iniciar el monitor (HRTmon) si HRTmon está habilitado en el menú OSD (de lo contrario F11 es la tecla HELP de Amiga)
ScrollLock - alternar la emulación de sólo teclado / ratón / joystick 1 / joystick 2 en el teclado (teclas de dirección + LCTRL)
Enlaces y más información
Página de Rok Krajnc somuch.guru.

Más información sobre minimig en el foro de discusión de Minimig.

El Turbo Chameleon 64 - Ordenadores individuales

Soporte de la placa MiST y otros núcleos en la página del proyecto MiST

Créditos
Este proyecto contiene código escrito por:

Jakub Bednarski
Sascha Boing
Tobias Gubener
Till Harbaum
Rok Krajnc
Alastair M. Robinson
Gyorgy Szombathelyi
Dennis van Weeren
Todo el código tiene copyright © 2005 - 2021 y es propiedad de sus respectivos autores.


License
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.

Building minimig-mist from sources
checkout the source
download / install Altera Quartus II (latest supported version for Cyclone III FPGA device used on the MiST board is 13.1; I'm still using version 10.1SP1)
build the core using Quartus GUI (project file in fpga/mist)
place the minimig-mist.rbf files on the root of your SD card (optionally, rename minimig-mist.rbf to core.rbf to make it the default core)
don't forget to place kickstart ROM of your choosing on the root of the SD card (these are still copyrighted, so either copy the ROM from your real Amiga, or buy AmigaForever)
place some ADF (floppy disk images) of your favourite games / demos / programs on your SD card
optionally place minimig.bal, minimig.art & minimig.cop files on the root of your SD card for a nice bootup animation
enjoy minimig! :)
Sources
This sourcecode is based on Rok's previous project (minimig-de1), and it continues from there. It was split into a new project to allow changes that would never fit in the FPGA on the DE1 board.

Original minimig sources from Dennis van Weeren with updates by Jakub Bednarski are published on Google Code.

Some minimig updates are published on the Minimig Discussion Forum, done by Sascha Boing.

ARM firmware updates and minimig-tc64 port changes by Christian Vogelsang (minimig_tc64) and A.M. Robinson (minimig_tc64).

MiST board & firmware by Till Harbaum (MiST).

TG68K.C core by Tobias Gubener (TG68K.C).
