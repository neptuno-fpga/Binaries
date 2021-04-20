#PC Engine

#### Core ported by Jose Manuel @delgrom
#### Sources: https://en.wikipedia.org/wiki/TurboGrafx-16

![PC-Engine-Console-Set](https://user-images.githubusercontent.com/31018768/115451325-56444c80-a21d-11eb-8460-9d41820d70bf.jpg)


Información del sistema original reimplementado en Fpga:
  PC-Engine / SuperGrafx para MIST / SiDi
  ================
  Instrucciones: coloque el archivo .rbf en SD.

Esta es una continuación de la bifurcación FPGAPCE de Alastair Robinson, que se centra principalmente en
en el tablero MiST. Contiene CPU, VDP y otras correcciones del proyecto MiSTer.
El código de otra placa y el controlador ZPUFlex todavía están en el repositorio, pero no
no hubo esfuerzos para hacerlos funcionar. Se agradecería mucho arreglarlos.

Características:

- Descarga estándar de MiST OSD y ARM ROM
- Soporte de SuperGrafx
- Soporte de mapeador ROM especial 384K, 768K y SF2
- Multitap hasta 5 controladores (4 reportados para trabajar)
- Soporte de controlador de 6 botones

README anterior:
================

TENGA EN CUENTA: esta es una bifurcación del núcleo FPGA PC Engine original, que agrega
una segunda CPU y un menú de visualización en pantalla para configurar las opciones y seleccionar
ROM. Es posible que haya introducido errores en el proceso, y esto debería ser
considerado altamente experimental.

En particular, la extraña reasignación de bancos utilizada en ROM de 768K no está actualmente
compatible: si tiene una ROM de este tipo, hágamelo saber.

Actualmente, el núcleo se construye para las siguientes plataformas:
Turbo Camaleón 64
NEBLINA
Altera DE1 (sonido actualmente desactivado para hacer espacio para la CPU OSD - desde
de lo contrario, nos quedamos sin RAM de bloque.

Actualmente, solo se admite un joypad. Además de compatibilidad nativa con joypad
el firmware OSD proporciona emulación de joypad a través del teclado, utilizando el
teclas de cursor, ctrl derecho y teclas AltGr.
Los botones Run y ​​Select son Enter y Right Shift, respectivamente.

En última instancia, intentaré agregar soporte para múltiples pulsaciones.

A continuación, el archivo README original:

================================================ ==============================
fpgapce: un clon NEC PC-Engine / Turbografx-16 en un FPGA.
Copyright (c) 2011-2013 Gregory Estrade (greg@torlus.com)
Reservados todos los derechos

fpgapce es un intento de clonar la consola NEC PC-Engine / Turbografx-16 en una FPGA.
Actualmente es lo suficientemente avanzado como para ejecutar muchos juegos.

================================================ ==============================
Para ejecutar este proyecto, necesitará:
- Una placa Terasic / Altera DE1.
- Un monitor VGA.
- Un auricular, si quieres disfrutar del sonido.
- Contenido del CD-ROM DE1. (http://www.terasic.com/downloads/cd-rom/de1/)
- Edición web de Altera Quartus II 9.1.
- (opcional) ModelSim-Altera 6.5b Starter Edition.

Primero, la FPGA EEPROM debe programarse con el diseño de demostración
"DE1_USB_API.sof". Debería ser el caso si nunca lo ha reprogramado.
Eso le permitirá utilizar el software "Panel de control DE1".

Encienda su placa DE1, asegúrese de que esté conectada a través de USB a su computadora.
Ejecute el programa "DE1_Control_Panel.exe".
Haga clic en "Abrir", seleccione "Abrir puerto USB 0".
Seleccione la pestaña "FLASH" y haga clic en "Chip Erase".
Marque "Longitud del archivo", luego haga clic en "Escribir un archivo en FLASH".
Elija una ROM de PC-Engine.
Una vez realizada la operación de escritura, cierre el "Panel de control DE1".

Si descargó el archivo de programación, ejecute Quartus Programmer
("quartus_pgmw.exe" ubicado en "<directorio raíz alternativo> \ 91 \ quartus \ bin").
Seleccione el archivo "pce_top.sof", haga clic en "Inicio", ¡y listo!

Notas:
- Asegúrese de realizar siempre un "Borrado de chip" antes de programar una nueva ROM.
- No sé si se debe a mi propia configuración, pero descubrí que la escritura flash
  La operación no es muy confiable, ya que a menudo obtengo un byte cuando intento leer
  retrocede el flash. Para algunos juegos no importa (si tienes la suerte y
  que el error de escritura ocurre en una sección de datos y no en una sección de código).
  Sin embargo, algunos juegos realizan una verificación de autoconsistencia y no se ejecutan en absoluto.
  Solo solución alternativa hasta ahora: borre y vuelva a programar el flash hasta que tenga éxito.

Las ROM son volcados de memoria de cartucho, que pueden incluir un encabezado de 512 bytes.
También hay una asignación de memoria especial para ROM que tienen un tamaño de 768 Kb.
Así que configuré algunos interruptores para hacer frente a estas diferentes configuraciones:
- SW1: encabezado presente o no (por lo general, las ROM tienen este encabezado, así que configúrelo en "1").
- SW2: configúrelo en "1" si su ROM es de 768 Kb.
- SW3: configúrelo en "1" si está tratando con una ROM TGFX en lugar de una ROM PCE.
  NEC creó un bloqueo de región muy básico al intercambiar bits de datos en el cartucho
  y conector de cartucho en las consolas de EE. UU. (TGFX-16).
  Por lo tanto, para las (muy pocas) ROM que se han descargado de un cartucho de EE. UU., Configúrelo en "1".
  Si no está seguro, ajústelo a "0".

Una almohadilla de 4 botones está asignada a los interruptores y botones de la placa.
Aquí hay una descripción de los controles:
- KEY0: Botón I
- KEY1: Botón II
- KEY2: Ejecutar
- KEY3: Seleccionar
- SW9: Arriba
- SW8: Abajo
- SW7: Izquierda
- SW6: Derecha
SW0 realiza una operación de reinicio completo.

================================================ ==============================
Gregory Estrade (Torlus) - 02/02/2012
greg@torlus.com

Licencia ###


Este programa es software libre: puede redistribuirlo y / o modificarlo bajo los términos de la Licencia Pública General GNU publicada por la Free Software Foundation, ya sea la versión 3 de la Licencia, o (a su elección) cualquier posterior.
 
### License


This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.
