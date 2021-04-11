# XZ SPECTRUM 128 

### Core portado por Jose Manuel @delgrom

![zx128](https://user-images.githubusercontent.com/31018768/81352408-c74f2a80-90c6-11ea-8396-9087222a6d24.jpg)

En este proyecto se utilizaron algunos modelos de verilog del núcleo de Till Harbaum Spectrum.

Características:
ZX Spectrum 48K, 128K, +3 y Pentagon 128 completamente funcional con CPU y tiempos de video correctos.
Interfaces de memoria Pentagon 1024K y Profi 1024K.
Turbo 7MHz, 14MHz, 28MHz, 56MHz.
Paletas programables ULA + v1.1 con control Timex extendido.
Modos Timex HiColor, HiRes.
Carga de cinta original a través de OSD (archivos CSW).
TR-DOS (Beta Disk Interface) e imágenes TRD nativas.
Imágenes G + DOS (interfaz de disco MGT + D) e IMG, MGT (solo en los modos de memoria ninguno + 2A / 3).
+3 Unidad de disco utilizable con + 3DOS.
Complemento Multiface 128 y Multiface 3 (en modo +3).
Guardar / cargar instantáneas de memoria en + D y Multiface.
TAP nativo con carga turbo. Carga rápida para TAP, CSW y TZX.
Ratón y joystick Kempston.
Joystick Sinclair I
Interfaz Turbo-Sound (chips de sonido duales YM2149)
Interfaz de sonido general
Entrada de audio desde un dispositivo de cinta real
Core requiere la actualización de firmware MiST para compilar 2016/06/26 o más reciente.

### Requerimientos

Necesita la roms Spectrum.dat

Notas sobre los formatos compatibles:
TRD es una imagen TR-DOS utilizada con Beta Disk Interface (BDI). Para usar TR-DOS, primero debe elegir la imagen TRD en OSD. En el modo 128K use el menú para ingresar a TR-DOS. En el modo 48K use el comando RANDOMIZE USR 15616 para ingresar TR-DOS. En el modo +3, ingrese al modo 48K desde el +3 BÁSICO a través del comando USR0, luego emita RANDOMIZE USR 15616. Use el comando RETURN para salir de TR-DOS.

IMG es una imagen de G + DOS que se utiliza con la interfaz de disco + D. Aunque es totalmente compatible, no pude encontrar ningún juego en esos discos. El objetivo principal de estas imágenes es utilizar la función de instantánea de + D y Multiface.

MGT es una imagen de G + DOS y MasterDOS (SAM Coupe). Es similar a IMG pero usa un diseño diferente. El propósito principal es transferir datos hacia / desde SAM Coupe.

Formato de disco DSK +3. En los modos none- +3, + D intenta montarlo, sin embargo, las imágenes de disco +3 no son compatibles con G + DOS. La unidad de disco +3 original es una unidad de doble densidad de una cara de 170 K, pero este núcleo también admite imágenes de doble densidad de 720 K de doble cara. Una imagen DSDD vacía es ideal para guardar desde Multiface. Nota: en el modo +3, se admiten tanto la unidad de disco Beta como la +3, pero solo se puede montar una imagen, por lo que no se pueden usar ambas al mismo tiempo.


TAP es un formato de volcado de cinta simple. Es posible usar carga normal y turbo (solo si la aplicación usa rutinas de carga estándar desde ROM). Para cargar en modo turbo, primero debe elegir el archivo TAP en OSD y luego comenzar a cargar la aplicación a través del menú (128K) o mediante el comando LOAD "" (48K, 128K). Para cargar un archivo TAP en modo normal a través del bucle AUDIO IN interno, primero debe comenzar a cargar a través del menú o comando y luego elegir el archivo TAP a través del OSD. Si la aplicación utiliza un cargador no estándar, el archivo TAP se reproducirá automáticamente en modo normal. Por lo tanto, es seguro elegir siempre el modo turbo. Algunas aplicaciones se dividen en varias partes dentro de un archivo TAP. Por ejemplo, aplicaciones de demostración en las que cada parte se carga una vez finalizada la parte anterior, o niveles de carga de juegos por solicitud. El núcleo pausa la reproducción de TAP después de cada parte del código (bandera = # 255). Si la aplicación usa un cargador estándar de ROM, entonces todo se manejará automáticamente y pasará desapercibido. Si la aplicación utiliza un cargador no estándar, no hay forma de detectar la carga. En este caso, debe presionar la tecla F1 para continuar / pausar la reproducción TAP. No presione la tecla F1 mientras se cargan los datos (o tendrá que reiniciar y comenzar desde el principio). Para ayudar a operar con TAP (para cargadores no estándar) hay una señalización LED amarilla especial:

CONTROLES DE GRIFO
-------------------------------------

F1 - pausar / continuar

F2: salta a la parte anterior (si se presiona durante el tono piloto) o al comienzo de la parte actual (si se presiona mientras se está transfiriendo el código).

F3 - pasar a la siguiente parte

CSW es ​​formato de cinta, útil solo para aplicaciones que utilizan cargadores no estándar con velocidades de transferencia no estándar. Estos archivos se cargan siempre en modo normal. Puede usar la tecla F1 para pausar / continuar.

Los archivos TZX contienen copias exactas de cintas originales. Este formato es muy complejo y no todas las funciones son compatibles. Puede usar la tecla F1 para pausar / continuar.

Opción OSD La carga rápida de cinta aumenta la frecuencia de la CPU a 56MHz mientras se carga la cinta.

Modos turbo
Puede controlar la velocidad de la CPU con las siguientes teclas:

F4 - velocidad normal (3,5 MHz)
F5 - 7 MHz
F6 - 14 MHz
F7 - 28 MHz
F8 - 56 MHz
F9 - pausar / continuar
Es útil cambiar a la velocidad máxima cuando está cargando cinta en modo normal. Debido a la limitación de velocidad de la SDRAM, las velocidades de 28MHz y 56MHz incluyen estados de espera, por lo que la velocidad efectiva de la CPU es menor que la nominal.

Configuraciones de memoria con RAM adicional:
Pentagon 1024K usa los bits 5, 6 y 7 en el puerto 7FFD para acceder a memoria adicional. El puerto EFFD / bit 2 restaura la funcionalidad original de 7FFD / bit 5 (deshabilita la paginación).
Profi 1024K usa los bits 0-2 en el puerto DFFD para acceder a memoria adicional.
Ratón y joystick:
El mouse Kempston no tiene una convención estricta sobre qué bit (D0 o D1) refleja un botón principal. Después de cada reinicio, el primer botón presionado en el mouse (solo botones izquierdo o derecho) será representado por el bit D0 (el otro botón será reprimido