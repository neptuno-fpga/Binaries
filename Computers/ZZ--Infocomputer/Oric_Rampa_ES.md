# Oric 48K en MiST , SiDi y neptUNO FPGA

Reimplementación de Oric-1 y Oric Atmos en una FPGA moderna.

### Fondo:

Hay una versión hecha y portada por [Gehstock] (https://github.com/Gehstock/Mist_FPGA/tree/master/Computer_MiST/OricInFPGA_MiST) en github, pero está lejos de ser funcional como un Oric. La versión de Gehstock para la placa MiST se lanzó como prueba de concepto con solo 32 KB de RAM (no existía oric con esa memoria, solo ** 16K **, ** 48K ** y ** 64K **) (64KB es RAM real) por lo que hubo errores al administrar el modo ** HIRES **) y no hubo forma de cargar cintas de audio y muchos errores gráficos en la pantalla.

### ¿Qué puede esperar de Oric 48K en MiST y SiDi FPGA?

Este proyecto comenzó en noviembre de 2019 con el objetivo de preservar la familia de computadoras Oric en fpga.

En realidad, Oric 1, Oric Atmos y Microdisc son completamente funcionales.
* ** ULA HCS10017 **.
* ** VIA 6522 **.
* ** CPU 6502 **.
* 64 KB completos de ** RAM **.
* Teclado gestionado por GI-8912.
* Sonido (** AY-3-8910 **).
* ** ROM ** conmutable (entre la versión 1.1a ATMOS y la versión 1.0 ORIC 1).
* Carga de cinta en funcionamiento (a través del cable de audio en el pin RX).
* Implementación Oric Microdisc vía ** CUMULUS **
* Las operaciones de lectura / escritura de disco son totalmente compatibles con el formato EDSK (lo mismo que amstrad cpc).
* Disco Sedoric / OricDOS Sistema operativo Cargando completamente funcionando

### HACER

 * Depuración, comprobación de posibles errores en vídeo y mejora del núcleo.


### ERRORES CONOCIDOS

   * Ninguno por el momento ..., pero si lo encuentra, avísenos, por favor.

### CÓMO UTILIZAR ORIC 1 & ATMOS CON placas MiST, MiSTica y SiDi FPGA.

* ** Cree un directorio llamado ORIC en la raíz de su sd y colóquelo dentro de las imágenes del disco para trabajar **

   * Una vez que se lanza el núcleo:

   Atajos de teclado:
   * F10 - Botón NMI, actúa como ORIC NMI original
   * F11 - Restablecer. Use F11 para reiniciar una vez que se selecciona un DSK en OSD
   * F12 - Menú principal OSD.

   ! [atajos] (img / shorcuts.jpg? raw = true "Atajos de teclado")

   * Activar el controlador FDC en el MENÚ OSD
   * Seleccione una imagen del directorio / ORIC, salga del OSD y presione F11. El sistema se iniciará inmediatamente



## El EQUIPO de preservación de Oric Fpga

   * Ron Rodritty: Coordinación del equipo y pruebas de control de calidad.
   * Fernando Mosquera: gurú de la FPGA.
   * Subcrítico: Verilog y VHDL.
   * ManuFerHi: Consultoría de hardware.
   * Chema Enguita: Oric Software gurú
   * SiliceBit: Oric hardware Gurú
   * ZXMarce: Soporte de hardware 24/7 ...
   * Ramón Martínez: hardware Oric, algún software y codificación fpga.
   Slingshot: trabajo y asesor SDRAM.

* Felicitaciones a: Sorgelig, Gehstock, DesUBIKado, RetroWiki y amigos.

## Acerca de las imágenes de disco.

  A pesar de la extensión .dsk, las imágenes de disco son el estándar ** edsk ** de facto para la conservación del disco (también conocido como "AMSTRAD CPC EXTENDED FORMAT"). Para convertir imágenes
  desde el "dsk" oric al "dsk" necesario, necesita el [software HxCFloppyEmulator] (https://hxc2001.com/download/floppy_drive_emulator/HxCFloppyEmulator_soft.zip).

  Cargue el disco oric disk y expórtelo como ** archivo CPC DSK **, la imagen resultante debería cargarse sin problemas en Oric.
  Estas imágenes también son compatibles con el firmware fastfloppy en gothek, cuamana reborn, etc. trabajando con orics reales.

## Joystick

 casi todos los juegos de Oric no son compatibles con joystick, pero puedes "mapear" el
las teclas más utilizadas para un joystick agregando thist a su archivo ** mist.ini **.

[oric]
joy_key_map = 1,4f; cursor a la derecha
joy_key_map = 2,50; cursor a la izquierda
joy_key_map = 4,51; cursor abajo
joy_key_map = 8,52; cursor arriba
joy_key_map = 10,2c; botón A como ESPACIO
joy_key_map = 40,28; botón SEL como ENTER
joy_key_map = 80,44; botón STA como F11

## Redistribución de software.

 En el directorio dsk, encontrará algunas imágenes de disco en el formato adecuado.

* ** SEDORIC 4.0 ** Imagen de disco del sistema operativo redistribuida con permiso de Symoon.
* ** Juego de Blake 7 **, redistribuido con permiso de chema enguita. Puedes descargar el manual y la información adicional de [Defense force] (http://www.defence-force.org/index.php?page=games&game=blakes7)
* ** Juego de Oricium **, redistribuido con permiso de chema enguita. Puedes descargar el manual e información adicional de [Defense force] (http://www.defence-force.org/index.php?page=games&game=oricium)
* ** Espacio: 1999 ** juego, redistribuido con permiso de chema enguita. Puedes descargar el manual e información adicional de [Defense force] (http://www.defence-force.org/index.php?page=games&game=space1999 )
* ** Juego 1337 **, redistribuido con permiso de chema enguita. Puedes descargar el manual e información adicional de [Defense force] (http://www.defence-force.org/index.php?page=games&game=1337)
