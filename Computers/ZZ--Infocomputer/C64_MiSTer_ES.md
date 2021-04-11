## C64 para MiSTer

#### Core portado por @NeuroRulez, SID mejorado por Rampa

Fuente: https://github.com/neurorulez/C64_MiSTer

Basado en FPGA64 de Peter Wendrich con fuertes modificaciones posteriores por parte de diferentes personas.

Características
Modos C64 y C64GS.
Soporte de lectura / escritura de disco (* .D64)
Casi todos los formatos de cartuchos (* .CRT)
Inyección directa de archivos (* .PRG)
SID dual con varios grados de mezcla 6581/8580 de estéreo a mono.
Similar a los filtros SID 6581 y 8580.
Expansor de sonido OPL2.
Modo 4 joysticks.
Conexión UART a Internet.
ROM Kernal / C1541 cargables.
Modo de borde reducido especial para visualización 16: 9.
Instalación
Copie el * .rbf a la raíz de la tarjeta SD. Copie discos / carros a la carpeta C64.

Uso

Teclado

Las teclas F2, F4, F6, F8, izquierda / arriba activan automáticamente la tecla Shift.

F9 - tecla de almohadilla.

F10 - tecla más.

F11 - tecla de restauración. También clave especial en carros AR / FC.

Alt - C = tecla.

![keymap](https://user-images.githubusercontent.com/31018768/109422084-5ae94300-79da-11eb-9ae7-9e60d4e7f719.gif)

mapeo de teclado

ROM cargable
La ROM alternativa se puede colocar en la carpeta C64 con el nombre boot.rom. El formato es una simple concatenación de BASIC + Kernal.rom + C1541.rom

Para crear la ROM en DOS o Windows, reúna sus archivos en un solo lugar y use el siguiente comando desde el indicador de DOS. El lugar más fácil para adquirir los archivos ROM es la distribución de VICE. BASIC y KERNAL están en el directorio C64 y dos1541 está en el directorio Drives.

COPIA BÁSICA + KERNAL + dos1541 BOOT.ROM / B

Para usar JiffyDOS u otro kernel alternativo, reemplace los nombres de archivo con el nombre de su archivo ROM o BIN. (Tenga en cuenta que debe usar la ROM 1541-II. La ROM del 1541 original solo cubre la mitad de la ROM de la unidad y no funciona con emuladores).

COPY / B BASIC.bin + JiffyDOS_C64.bin + JiffyDOS_1541-II.bin BOOT.ROM

Para confirmar que tiene la imagen correcta, el BOOT.ROM creado debe tener exactamente 32768 bytes de longitud.

Autocargar el cartucho
Coloque el cartucho deseado con el nombre boot3.rom en la carpeta C64 para cargarlo automáticamente al inicio.

Licencia Este programa es software libre: puede redistribuirlo y / o modificarlo según los términos de la Licencia Pública General GNU publicada por la Free Software Foundation, ya sea la versión 3 de la Licencia o (a su elección) cualquier versión posterior. Este programa se distribuye con la esperanza de que sea útil, pero SIN NINGUNA GARANTÍA; incluso sin la garantía implícita de COMERCIABILIDAD o APTITUD PARA UN PROPÓSITO PARTICULAR. Consulte la Licencia pública general GNU para obtener más detalles. Debería haber recibido una copia de la Licencia Pública General GNU junto con este programa. De lo contrario, consulte http://www.gnu.org/licenses/.