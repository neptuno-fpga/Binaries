# TSConf Desmistificado por Rampa

Fuente: https://github.com/DECAfpga/TSConf_Demistify

Este es un port de TSConf (una mejora del clon del Spectrum ZX-Evolution ZX) a MiSTer.

Características del port
------------------------
Scandoubler con HQ2x y Scanlines.
RTC.
Configuraciones CMOS configurables a través de OSD.
Admite SD secundaria e imagen en SD primaria.
Joystick de Kempston.
Ratón Kempston.
Turbosound FM (doble YM2203)
Sonido general 512 KB-2 MB
SAA1099

Instalación
------------------------
coloque RBF en la raíz de la tarjeta SD principal. Y luego tienes 3 opciones:

1 Formatee la tarjeta SD secundaria con FAT32 y descomprima el contenido de SDCard.zip en ella.

2 Cree una imagen TSConf.vhd (¡no MBR!) Con formato FAT32 y descomprima SDCard.zip en ella. Luego, coloque TSConf.vhd en la raíz de la tarjeta SD principal.

3 Igual que 2, pero nombre el archivo boot.vhd y colóquelo en la carpeta TSConf de la tarjeta SD principal.

Coloque algunos archivos TAP, SNA, SCL, TRD, SPG en la tarjeta SD secundaria (o en la imagen TSConf.vhd) también.

De forma predeterminada, si todo se hace bien, Wild Commander se cargará donde puede elegir los juegos para comenzar.

Archivos VHD
Puede crear varios archivos VHD y ponerlos en la carpeta TSConf en la tarjeta SD principal y luego elegir entre OSD.

Nota
Aunque se puede iniciar la página de configuración de CMOS original (CTRL + F11), la configuración realizada allí no tendrá efecto. Necesita utilizar OSD para la configuración de CMOS.

La tecla TSConf F12 original (reinicio) se transfiere a F11.
