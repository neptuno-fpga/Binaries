## MSX-X + smx improvements

#### Core by @NeuroRulez

---------------------------------


Usando la imagen lista

Descomprima el archivo ./sdimg/SD_SM-X.ZIP para obtener el archivo SD_SM-X.img.

Utilice Etcher o Win32DiskImager para guardar esta imagen en una tarjeta SD (mínimo 1 Gb).

Después de grabar, copie el archivo "SM-X.MCP" a la raíz de la tarjeta. Cambie el nombre a "core.np1" si desea que el arranque sea automático.

Generando desde sdcreate

En el directorio ./sdcreate hay 2 scripts, uno para Windows y otro para Linux, para
generar una tarjeta SD utilizando toda su capacidad (hasta el tamaño máximo de
una partición FAT16: 4GB)

Más información en el archivo README dentro del directorio ./sdcreate
