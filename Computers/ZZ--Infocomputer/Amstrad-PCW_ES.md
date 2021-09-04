Amstrad PCW  Core por rampaAmstrad PCW MiSTer Core por rampa

Fuente: https://github.com/rampa069/Amstrad-PCW_MiSTer/tree/demistify

! [gnomo] (https://user-images.githubusercontent.com/31018768/132091373-d1695c1c-e9f4-430f-b65f-8bcec1fb8758.jpg)

Gnome Ranger ejecutándose en el núcleo de Amstrad PCW por [steddyman] (https://twitter.com/steddyman)
## Visión general
El Amstrad PCW fue una línea de computadoras lanzada por Amstrad UK a mediados de la década de 1980 para proporcionar una alternativa más barata a tener una PC IBM para procesamiento de texto y aplicaciones simples de oficina. Se suministró con un teclado desmontable, una impresora, una unidad de disco y un monitor de alta resolución. Este monitor permitió al PCW mostrar gráficos monocromáticos nítidos a una resolución de 720 x 256.

A pesar de que el mercado previsto son las aplicaciones comerciales y los usuarios de oficinas en el hogar, la computadora vendió más de 8 millones de unidades y también se desarrollaron varios juegos para la máquina, así como complementos de terceros, como tarjetas de sonido, adaptadores de joystick y ratones. El Amstrad PCW también se vendió como Schneider Joyce en Europa.

El PCW venía con 256k o 512k y se podía ampliar hasta 2 MB de memoria. La pantalla de alta resolución y la gran cantidad de memoria para la época, hacen de la PCW la máquina CP / M perfecta y un sistema ideal para reproducir aventuras gráficas y de texto temprano.

## Características
* Amstrad PCW con CPU Z80 operando a 4Mhz
* Soporte turbo a 8Mhz (2x), 16 Mhz (4x) o 32 Mhz (8x)
* Soporte de memoria expandido a un máximo de 2 MB
* Unidades de disco de 3 "y 3,5" con soporte de lectura y escritura
* Compatible con el formato DSK de emulador estándar
* Soporte de resolución PAL (720x256) o NTSC (720x200)
* Mapeo completo de teclado de PC
* Soporte de joystick para los siguientes tipos de joystick:
  * Joystick de Kempston
  * Joystick Spectravideo
  * Joystick en cascada
  * Joystick DKTronics
* Soporte de mouse para los siguientes tipos de mouse:
  * Ratón AMX
  * Ratón Kempston
  * Keymouse
* Sonido de pitido PCW normal y compatibilidad con el generador de sonido DKTronics (AY-3-8912)
* Modo de color configurable
 

## Usando el núcleo

A diferencia de muchas computadoras domésticas de mediados de los 80, la Amstrad PCW siempre incluyó una unidad de disco y un monitor y todo el software PCW se suministra solo en formato de disco. El emulador es compatible con las imágenes de formato DSK estándar que utilizan los dos emuladores principales de PCW, Joyce de John Elliot y CPM / Box de Habisoft.

El PCW tampoco tiene una ROM de ARRANQUE, sino que transmite una pequeña rutina de arranque desde el controlador del teclado en el momento del encendido. El núcleo de PCW recrea esta secuencia de arranque y no requiere ningún archivo ROM externo para arrancar. Simplemente coloque sus imágenes DSK en el directorio ** / Games / Amstrad PCW / ** en la raíz de la tarjeta SD.

Los juegos generalmente se suministran en dos discos, normalmente el primer disco es un disco de arranque CP / M. Inserte este disco de arranque en la unidad A: usando el Menú, luego seleccione ** RESTABLECER ** en el menú OSD para cargar el disco. Una vez que el disco de arranque haya terminado de arrancar, el PCW le pedirá que cambie el disco al segundo disco y presione Intro.

! [change_disk] (https://user-images.githubusercontent.com/31018768/132091383-a1f2a011-4e53-4938-8266-2e05c6521891.jpg)

El principal sistema operativo que utilizó PCW se llamó CP / M, que fue desarrollado por Digital Research y fue uno de los primeros sistemas operativos multiplataforma del mundo. Más información sobre CP / M y algunos comandos comunes disponibles están documentados en [The CP / M Wiki article] (https://en.wikipedia.org/wiki/CP/M)

## Modelos PCW

El núcleo de PCW emula dos modelos diferentes de PCW:
* ** PCW8256 / 8512 ** - Unidad A 3 "180k (CF2), Unidad B 3" 720k (CF2DD)
* ** PCW9256 / 9512 + ** - Ambas unidades 3,5 "720k (MF2DD)

Estos dos modelos diferentes de PCW requieren diferentes discos de arranque. Esto se debe a que cada modelo tiene un bootrom diferente, que busca diferentes sumas de comprobación en el sector de arranque del disco. Si se equivoca, sonará tres veces para indicar que no se reconoce el disco.

## Modo de color falso

Al igual que los emuladores CP / M Box y Joyce y un par de placas complementarias, este núcleo ahora admite modos de color. A diferencia de esos emuladores, no es necesario que abarque toda la pantalla y se puede configurar desde el software en caso de que los autores de nuevos juegos deseen utilizarlo.

! [gusano] (https://user-images.githubusercontent.com/31018768/132091395-3ccd3455-f367-4f31-bc56-b381b7386bc1.jpg)


Muchos juegos de aventuras de PCW contienen gráficos en la parte superior, con una interfaz de texto antes. Una vez que el modo de color falso está habilitado, puede usar las siguientes teclas para controlarlo:

* ** F9 ** - Mover la línea de color para habilitar la alineación
* ** F10 ** - Mover la línea de habilitación de la línea de color hacia abajo
* ** F11 ** - Activar / desactivar el modo de color de pantalla completa

El modo también viene con tres paletas CGA diferentes para seleccionar.

## Problema actual
* SymbOS no funciona correctamente
* PSI-5 Trading Company: requiere el comando de disco SCAN_EQUAL que no está implementado

# Cambios con respecto a la versión anterior
* Soporte para el modo PCW9512 + y unidades de 3,5 "
* Soporte para dos unidades de disco
* Soporte SDRAM para proporcionar hasta 2 MB de memoria
* Modo de color con punto de partida configurable
* Modo de paginación CPC. Soluciona problemas con varios juegos (por ejemplo, Abadia, Head over Heels)
* Mejoras en el movimiento del mouse
* Emulación de puerto Daisywheel para permitir que PCW915 + CPM arranque
* Problemas resueltos con la corrupción del disco y errores de arranque
* Solucionado el problema de corrupción con RAMtest
* F2 / F4 / F6 / F8 ya no requieren que presione shift

Todas las nuevas características se demuestran en el siguiente video:

https://youtu.be/z-IoDr81xjE

## Próximas funciones
Las siguientes características estarán disponibles en breve
* Soporte para SymbOS

## Notas del juego
* Blagger: se moverá a la izquierda a menos que el Joystick esté configurado en Cascade

## Gracias
Un agradecimiento especial a las siguientes personas:
* John Elliott por la fantástica [guía de hardware de PCW] (https://www.seasip.info/Unix/Joyce/hardware.pdf), el [emulador de Joyce] (https://www.seasip.info/Unix/Joyce /) y por responder a mis correos electrónicos
* Javier Chocano de Habisoft para el [emulador CP / M Box] (http://www.habisoft.com/pcw/) y orientación inicial
* [@zigazou] (https://twitter.com/zigazou) para su [artículo wiki] detallado (https://github.com/Zigazou/amstrad-pcw-technical-info/tree/master/video-memory) en la estructura de memoria de la pantalla PCW
* [@asicguy] (https://github.com/asicguy), [@alanswx] (https://github.com/alanswx) y [@dshadoff] (https://github.com/dshadoff) para ayuda, eoncouragment y apoya el desarrollo del core
* [@sorgelig] (https://github.com/sorgelig) por el fantástico proyecto y trabajo de MiSTer
