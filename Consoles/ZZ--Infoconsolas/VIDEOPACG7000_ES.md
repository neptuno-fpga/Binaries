# Videopac G7000 / Odyssey2 para FPGA.

## Ramon Martínez @ rampa069 portado para Neptuno y Unamiga Reloaded por Neuro.

Gracias a:
René van den Enden Gurú de Videopac. nos ayudó por correo electrónico y publicó mucha información en videopac.nl
Soporte Mejias3D en internos de videopac y programación del ensamblador 8048.
avlixa Para el puerto ZXDOS.
Antonio Sanchez Para el puerto LX16.
Wilco2009 Para el SD-cart para la consola real y para ayudar con los componentes internos del hardware y trucos, ¡su cartucho sd para la consola real es imprescindible !.
Neuro For the Neptuno y Unamiga recargaron los puertos.
Benitoss para el puerto ZX Next (próximamente)

Fuentes: https://github.com/RW-FPGA-devel-Team/Videopac-G7000

![Magnavox-Odyssey-2-Console-Set](https://user-images.githubusercontent.com/31018768/106388338-4ff0c200-63de-11eb-9ed3-aa8d39326e83.jpg)

Esta es una implementación FPGA del Magnavox Oddysey2 / Videopac G700 basada en FPGA videopac de Arnim Laeuger y portado a MiSTer (con trabajo adicional de wsoltys) por Jamie Dickson.
Características
Cambie entre los modos Odyssey2 y Videopac.
Cambie entre dos paletas (emulación de RF compuesta y RGB para colores más vivos)
Teclado completamente funcional.
Botones de joystick para teclas 0-9.
juego de caracteres de ROM VDC cargable para algunas rom personalizadas. Para obtener información, cómo prepararlos y ejemplos, lea el manual. También tenga algunas ROM personalizadas listas para usar.
Sonido correcto, tiempos y mejor detección de colisiones.
Periférico "La Voz".
disponible en:
Señor
Neblina
SiDi
Neptuno
Unamiga recargada
ZxDOS
ZX Siguiente (pronto)
Instalación
Copie el archivo * .rbf a su tarjeta SD. Cree una carpeta Videopac en la tarjeta y coloque las roms Odyssey2 / Videopac (* .BIN) dentro de esta carpeta. Los volcados de XROM (por el momento, solo Musician conocido y 4 seguidos) deben cambiarse de nombre a * .rom.

Al cargar una ROM, la mayoría de los juegos le pedirán al usuario "SELECCIONAR JUEGO". Presione 0-9 en el teclado o el botón del controlador asignado para jugar. Desafortunadamente, no hay visualización en pantalla de las opciones del juego, por lo que mirar los manuales de instrucciones puede ser útil para seleccionar un juego. Tenga en cuenta que el sistema no tenía un controlador de jugador 1 o jugador 2 bien definido, se alternarían de un juego a otro. Es posible que deba intercambiar controladores para usar la entrada.

Problemas conocidos
Aún quedan algunos fallos gráficos.

Licencia
Este programa es software libre: puede redistribuirlo y / o modificarlo según los términos de la Licencia Pública General GNU publicada por la Free Software Foundation, ya sea la versión 3 de la Licencia o (a su elección) cualquier versión posterior. Este programa se distribuye con la esperanza de que sea útil, pero SIN NINGUNA GARANTÍA; incluso sin la garantía implícita de COMERCIABILIDAD o APTITUD PARA UN PROPÓSITO PARTICULAR. Consulte la Licencia pública general GNU para obtener más detalles. Debería haber recibido una copia de la Licencia Pública General GNU junto con este programa. De lo contrario, consulte http://www.gnu.org/licenses/.