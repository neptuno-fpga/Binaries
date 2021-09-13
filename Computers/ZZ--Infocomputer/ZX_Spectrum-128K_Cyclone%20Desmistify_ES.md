# ZX_Spectrum-128K_Cyclone Desmistify por @Neurorulez

fuente: https://github.com/neurorulez/ZX_Spectrum-128K_Cyclone/tree/Demist

ZX Spectrum 128K para [MIST Board] (https://github.com/mist-devel/mist-board/wiki)

En este proyecto se utilizaron algunos modelos de verilog del núcleo de Till Harbaum [Spectrum] (https://github.com/mist-devel/mist-board/tree/master/cores/spectrum).

### Características:
- ZX Spectrum 48K, 128K, +3 y Pentagon 128 completamente funcional con CPU y tiempos de video correctos.
- Interfaces de memoria Pentagon 1024K y Profi 1024K.
- Turbo 7MHz, 14MHz, 28MHz, 56MHz.
- Paletas programables ULA + v1.1 con control Timex extendido.
- Modos Timex HiColor, HiRes.
- Carga de cinta original a través de OSD (archivos CSW).
- TR-DOS (Beta Disk Interface) e imágenes TRD nativas.
- Imágenes G + DOS (interfaz de disco MGT + D) e IMG, MGT (solo en los modos de memoria ninguno + 2A / 3).
- Unidad de disco +3 utilizable con + 3DOS.
- Complemento Multiface 128 y Multiface 3 (en modo +3).
- Guardar / cargar instantáneas de memoria en + D y Multiface.
- TAP nativo con carga turbo. Carga rápida para TAP, CSW y TZX.
- Ratón y joystick Kempston.
- Joystick Sinclair I
- Interfaz Turbo-Sound (chips de sonido duales YM2149)
- Interfaz de sonido general
- Entrada de audio desde [dispositivo de cinta] real (http://www.atari-forum.com/viewtopic.php?p=298401#p298401)


### Instalación:
Copie el archivo * .rbf en la raíz de la tarjeta SD. Puede cambiar el nombre del archivo a core.rbf si desea que MiST lo cargue automáticamente al inicio.
Copie el archivo [spectrum.rom] (https://github.com/mist-devel/mist-binaries/tree/master/cores/spectrum/spectrum.rom) en la raíz de la tarjeta SD.
** Nota: ** siempre actualice el spectrum.rom junto con el core para asegurarse de que está utilizando una versión de ROM compatible. La ROM no siempre es compatible con todas las versiones (pero siempre es compatible con la última versión), por lo que debe conservar la ROM si desea utilizar una versión anterior del núcleo.

Para el modo PAL (salida RGBS), debe colocar el archivo [mist.ini] (https://github.com/sorgelig/ZX_Spectrum-128K_MIST/tree/master/releases/mist.ini) en la raíz de la tarjeta SD. Configure la opción ** scandoubler_disable ** para la salida de video deseada.

### Notas sobre los formatos compatibles:
** TRD ** es una imagen TR-DOS utilizada con Beta Disk Interface (BDI). Para usar TR-DOS, primero debe elegir la imagen TRD en OSD. En el modo 128K use el menú para ingresar a TR-DOS.
En el modo 48K use el comando ** RANDOMIZE USR 15616 ** para ingresar TR-DOS. En el modo +3, ingrese al modo 48K desde el +3 BÁSICO a través del comando USR0,
luego emita ** RANDOMIZE USR 15616 **. Use el comando ** RETORNO ** para salir de TR-DOS.

** IMG ** es una imagen de G + DOS utilizada con la interfaz de disco + D. Aunque es totalmente compatible, no pude encontrar ningún juego en esos discos. El objetivo principal de estas imágenes es utilizar la función de instantánea de + D y Multiface.

** MGT ** es una imagen de G + DOS y MasterDOS (SAM Coupe). Es similar a IMG pero usa un diseño diferente. El propósito principal es transferir datos hacia / desde SAM Coupe.

** DSK ** +3 formato de disco. En los modos none- +3, + D intenta montarlo, sin embargo, las imágenes de disco +3 no son compatibles con G + DOS.
La unidad de disco +3 original es una unidad de doble densidad de una cara de 170 K, pero este núcleo también admite imágenes de doble densidad de 720 K de doble cara.
Una [imagen DSDD] vacía (https://github.com/mist-devel/mist-binaries/tree/master/cores/spectrum/dsdd720k.dsk.gz) es excelente para guardar de Multiface.
*** Nota: *** en el modo +3, se admiten tanto la unidad de disco Beta como la +3, pero solo se puede montar una imagen, por lo que no se pueden usar ambas al mismo tiempo.

** TAP ** es un formato de volcado de cinta simple. Es posible usar la carga normal y ** turbo ** (solo si la aplicación usa rutinas de carga estándar desde la ROM). Para cargar en modo turbo, debe elegir el archivo TAP en OSD ** primero ** y luego comenzar a cargar la aplicación a través del menú (128K) o mediante el comando ** LOAD "" ** (48K, 128K). Para cargar un archivo TAP en modo normal a través del bucle AUDIO IN interno, debe comenzar a cargar a través del menú o comando ** primero ** y luego elegir el archivo TAP a través del OSD. Si la aplicación utiliza un cargador no estándar, el archivo TAP se reproducirá automáticamente en modo normal. Por lo tanto, es seguro elegir siempre el modo turbo. Algunas aplicaciones se dividen en varias partes dentro de un archivo TAP. Por ejemplo, aplicaciones de demostración en las que cada parte se carga una vez finalizada la parte anterior, o niveles de carga de juegos por solicitud. El núcleo pausa la reproducción de TAP después de cada parte del código (bandera = # 255). Si la aplicación usa un cargador estándar de ROM, entonces todo se manejará automáticamente y pasará desapercibido. Si la aplicación utiliza un cargador no estándar, no hay forma de detectar la carga. En este caso, debe presionar ** tecla F1 ** para continuar / pausar la reproducción TAP. No presione la tecla F1 mientras se cargan los datos (o tendrá que reiniciar y comenzar desde el principio). Para ayudar a operar con TAP (para cargadores no estándar) hay una señalización LED amarilla especial:
- LED encendido: hay más datos disponibles en el archivo TAP.
- LED parpadea: carga en curso.
- LED apagado: no quedan más datos en el archivo TAP.

En modo normal, mientras se carga TAP, se pueden utilizar las siguientes teclas:
- F1 - pausar / continuar
- - F2: salta a la parte anterior (si se presiona durante el tono piloto) o al comienzo de la parte actual (si se presiona mientras se está transfiriendo el código).
- F3 - pasar a la siguiente parte

** CSW ** es formato de cinta, útil solo para aplicaciones que utilizan cargadores no estándar con velocidades de transferencia no estándar. Estos archivos se cargan siempre en modo normal. Puede usar la tecla ** F1 ** para pausar / continuar.

Los archivos ** TZX ** contienen copias exactas de las cintas originales. Este formato es muy complejo y no todas las funciones son compatibles. Puede usar la tecla ** F1 ** para pausar / continuar.

La opción OSD ** Carga de cinta rápida ** aumenta la frecuencia de la CPU a 56MHz mientras se carga la cinta.

### Modos turbo
Puede controlar la velocidad de la CPU con las siguientes teclas:
- F4 - velocidad normal (3,5 MHz)
- F5 - 7 MHz
- F6 - 14 MHz
- F7 - 28 MHz
- F8 - 56 MHz
- F9 - pausar / continuar

Es útil cambiar a la velocidad máxima cuando está cargando cinta en modo normal. Debido a la limitación de velocidad de la SDRAM, las velocidades de 28MHz y 56MHz incluyen estados de espera, por lo que la velocidad efectiva de la CPU es menor que la nominal.

### Configuraciones de memoria con RAM adicional:
- ** Pentagon 1024K ** usa los bits 5, 6 y 7 en el puerto 7FFD para acceder a memoria adicional. El puerto EFFD / bit 2 restaura la funcionalidad original de 7FFD / bit 5 (deshabilita la paginación).
- ** Profi 1024K ** usa los bits 0-2 en el puerto DFFD para acceder a memoria adicional.

### Ratón y joystick:
El mouse Kempston no tiene una convención estricta sobre qué bit (D0 o D1) refleja un botón principal. Después de cada reinicio, el primer botón que se presione en el mouse (solo los botones izquierdo o derecho) estará representado por el bit D0 (el otro botón estará representado por el bit D1). Por lo tanto, si no está satisfecho con el mapa de botones del mouse, simplemente presione reiniciar y luego presione el otro botón primero.
Debido al conflicto de puertos con el joystick Kempston, el núcleo utiliza la detección automática. Cualquier actividad del mouse cambiará el puerto al control del mouse. Cualquier actividad del joystick cambiará el puerto al control del joystick.
Algunos juegos / aplicaciones detectan automáticamente el mouse. Por lo tanto, mueva el mouse o haga clic en su botón antes de usar dichos juegos / aplicaciones.
El segundo puerto de joystick D-SUB funciona como Sinclar Joystick 1 (emula las teclas 6,7,8,9,0)

### Instantáneas:
Core admite la funcionalidad de instantáneas de + D. Para usarlo, necesita montar una imagen IMG o MGT. La ROM incluye una imagen G + DOS precargada, por lo que puedes montar IMG / MGT en cualquier momento (incluso mientras juegas). ** Nota # 1 **: G + DOS precargado ha sido parcheado para permitir el cambio de disco sobre la marcha. Por lo tanto, si va a cargar G + DOS desde el disco, tenga cuidado, ¡puede dañar los guardados anteriores si cambia el disco! ** Nota 2: ** solo se puede montar una imagen de disco en cualquier momento. Por lo tanto, asegúrese de que si usa el juego de la imagen TRD, el juego no guardará nada más tarde en su disco.

Para guardar la instantánea usando + D (forma preferida), presione ** tecla F11 **. Verá rayas en el borde y el juego se congelará. Puede presionar las siguientes teclas:
- 3 - para guardar la pantalla.
- 4 - para guardar una instantánea de 48K.
- 5 - para guardar una instantánea de 128K.
Original + D ROM requiere presionar teclas Y / N adicionales en modo 128K para elegir el búfer de pantalla correcto. La ROM incluida se ha parcheado previamente para detectar automáticamente la pantalla. Entonces, solo presione 5 para una instantánea de 128K.

Para cargar la instantánea, simplemente monte IMG / MGT y vaya al indicador básico donde escriba ** CAT 1 ** para enumerar su contenido. Anote el número de archivos de instantáneas. Luego escriba ** LOAD pX ** donde X es el número de archivo de instantánea. Para otros comandos de disco, busque y lea el manual de G + DOS (MGT + D).

### Multiface 128 y Multiface 3:
Puede ingresar a la ROM multifacética usando ** RShift + F11 **. Multiface 128 incluye depurador precargado (Genie) donde puedes rastrear o modificar el juego.
Si prefiere usar la ROM simple de Multiface 128, realice el siguiente procedimiento: Mantenga presionado ** ESC **, luego presione ** RShift + F11 **.
Podrá usar la ROM multifacética desnuda presionando simplemente ** RShift + F11 ** hasta que se recargue el núcleo. Multiface proporciona funcionalidad de instantánea al guardar en discos IMG / MGT. Busque y lea el manual de Multiface 128.
** Nota: ** Multiface 128 expone su puerto, por lo tanto, si el juego tiene protección contra Multiface, no funcionará, a menos que presione (o) ff antes de salir del menú Multiface. Por lo tanto, se prefiere el uso de instantáneas + D.
Cuando se usa el modo Spectrum + 2A / 3, el Multiface 3 es compatible. No hay Genie para el +3, pero hay rutinas útiles del kit de herramientas en la ROM estándar.

### Formato ROM:

Puede crear su propio *** espectro. De ***, por ejemplo, para reemplazar +3 ROM con + 3e.
El formato es: Boot (GLUK) + TRDOS + 128 ROM0 + 128 ROM1 + +3 ROM0 / 1/2/3 + PlusD + MF128 + MF3 + 48K ROM + GS (bajo) + GS (alto). Cada parte es de 16k.

### Teclas especiales:
- Ctrl + F11 - reinicio en caliente
- Alt + F11: el reinicio en frío descargará el disco
- Ctrl + Alt + F11 - restablecer al menú ROM0
- F11: ingrese al menú de instantáneas + D (o al menú ROM0 si IMG / MGT no está montado)
- RShift + F11 - entrar en el menú Multiface 128
- F12 - Menú OSD

### Descarga binarios precompilados y ROM del sistema:
Vaya a [mist-binaries] (https://github.com/mist-devel/mist-binaries/tree/master/cores/spectrum).

### Código fuente
- https://github.com/sorgelig/ZX_Spectrum-128K_MIST
- https://github.com/gyurco/ZX_Spectrum-128K_MIST
