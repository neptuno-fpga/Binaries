# VIC-20
--------------------------------------------------
### Núcleo portado por @Neurorulez

#### Fuente: https://github.com/neurorulez/VIC20_MiST/tree/updated

#### Características:
-------------------------------------------------- ----

Basado en el código de The Replay Board
Expansión de 3k RAM a $0400
Paquetes de RAM de 8k/16k/24k desde $2000
Memoria CART de solo lectura o escritura a $a000
Soporte de joystick
Pantalla PAL/NTSC (con scandoubler opcional para monitores VGA y salida de componente YPbPr)
Carga de PRG/CARRO
Compatibilidad con la unidad de disco 1541
CARRITO/carga PRG
Los archivos CRT y PRG generalmente tienen la dirección de carga en los dos primeros bytes. Si un archivo en particular no contiene esta dirección, puede cargarlo en los $a000 predeterminados eligiendo la opción 'CRT con dirección de carga: No' en el menú OSD. Cargar un carrito en la ubicación de $a000 restablecerá automáticamente el núcleo, por lo que se iniciará automáticamente. Si tiene un cartucho de varias partes, primero cargue la parte que no carga a $a000. ¡Además, no olvide habilitar la opción de ROM de 8k para cartuchos!

expansiones de RAM
El núcleo admite desde la máquina original sin expandir (5k de RAM) hasta una completamente extendida (un total de 40k de RAM). Desafortunadamente, no todos los juegos son compatibles con todos los modos de expansión, por lo que debe averiguar qué requiere un juego en particular.

mapa RAM:
Extensión 3k: $0400
Extensiones 8k+: $2000, $4000, $6000
8k ROM/RAM: $a000
archivo ROM:
Un archivo VIC20.ROM es obligatorio en la raíz de la tarjeta SD. El formato de archivo es: 1541 (16k) + Kernal PAL (8k) + Kernal NTSC (8k) + Básico (8k) + Char (4k).

#### Teclas:
-------------------------------------------------- -----------------

F9 - Inicio/parada de cinta
F10 - Restablecer
RShift + F10 - Restablecer con descarga del carro
F11 - Restaurar

Descargar binarios prediseñados:
https://github.com/mist-devel/mist-binaries/tree/master/cores/vic20

Código fuente:
https://github.com/gyurco/VIC20_MiST

-------------------------------------------------- -
### Licencia


Este programa es software libre: puede redistribuirlo y/o modificarlo según los términos de la Licencia Pública General GNU publicada por la Free Software Foundation, ya sea la versión 3 de la Licencia o (a su elección) cualquier versión posterior.
Este programa se distribuye con la esperanza de que sea útil, pero SIN NINGUNA GARANTÍA; sin siquiera la garantía implícita de COMERCIABILIDAD o IDONEIDAD PARA UN PROPÓSITO PARTICULAR. Consulte la Licencia pública general de GNU para obtener más detalles.
Debería haber recibido una copia de la Licencia Pública General de GNU junto con este programa. Si no, consulte http://www.gnu.org/licenses/.
