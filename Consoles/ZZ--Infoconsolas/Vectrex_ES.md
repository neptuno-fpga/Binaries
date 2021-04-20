# Vectrex
### Port NeptUNO por Jose Manuel @delgrom
Fuentes:

Información del sistema original reimplementado en Fpga: https://es.wikipedia.org/wiki/Vectrex

! [250px-Vectrex-Console-Set] (https://user-images.githubusercontent.com/31018768/115450130-d10c6800-a21b-11eb-973f-e0d51ac8cf79.jpg)



GCE (Electrónica de consumo general) - Vectrex For Mist FPGA

Soporta hasta 32kb Roms

Control S:
 Movimiento: Joystick
 Botones: 1-4 en los botones de disparo del joystick

CPU: es posible elegir entre dos CPU:
  - MC6809 - Ciclo exacto de Greg Miller 6809
  - CPU09 - CPU compatible con 6809 de John Kent

La extensión de voz puede chocar con los controles en algunos juegos,
apague Speech si ocurre.







-------------------------------------------------- -------------------------------
- DE10_lite Nivel superior para vectrex por Dar (darfpga@aol.fr) (27/12/2017)
- http://darfpga.blogspot.fr
-------------------------------------------------- -------------------------------
- Solo uso educativo
- No redistribuya archivos sintetizados con roms
- No redistribuir roms sea cual sea la forma
-- Úselo bajo su propio riesgo
-------------------------------------------------- -------------------------------
- Utilice vectrex_de10_lite.sdc para compilar (restricciones de Timequest)
- /! \
- No olvide configurar el modo de configuración del dispositivo con la inicialización de la memoria
- (Asignaciones / Dispositivo / Opciones de pin / Modo de configuración)
-------------------------------------------------- -------------------------------
-- QUE HACER :
- pequeña melodía de dibujos de personajes (demasiado ancho)
- sintonice hblank para evitar artefactos de persistencia en los primeros 4 píxeles de una línea
-------------------------------------------------- -------------------------------
-
-- Principales características :
- Entrada de teclado PS2 @ gpio pines 35/34 (cuidado con la traducción / protección de voltaje)
- Salida de audio pwm @ gpio pines 1/3 (cuidado con la traducción / protección de voltaje)
-
- Utiliza 1 pll para generación de 25 / 24MHz y 12.5 / 12MHz desde 50MHz
-
- Selección de visualización horizontal / vertical en la compilación
- 3 o ninguna selección de nivel de intensidad en la compilación
-
- Sin ariete externo
- Uso de RAM FPGA tan bajo como:
-
- 336.000b (42Ko) sin cartucho, pantalla vertical, sin nivel de intensidad (minestrom)
- 402.000b (50Ko) con cartucho 8Ko, pantalla vertical, sin nivel de intensidad
- 599.000b (74ko) con cartucho de 32Ko, pantalla vertical, sin nivel de intensidad
- 664.000b (82ko) con cartucho de 8Ko, pantalla horizontal, sin nivel de intensidad
- 1.188.000b (146ko) con cartucho 8Ko, pantalla horizontal, nivel de intensidad 3

- Cartucho probado:
-
- berzerk (4ko)
- estafa (4ko)
- revolver (4ko)
- guerra espacial (4ko)
- startrek (4ko)
- pole position (8ko)
- espiga (8ko)
- webwars (8ko)
- rana (16Ko)
- vecmania1 (32ko)
- guerra del robot (21ko)
-
- Llave de tablero:
- 0: reiniciar el juego
-
- Entradas de tecladistas:
-
- F3: botón
- F2: botón
- F1: botón
- ESPACIO: botón
- Flecha DERECHA: joystick a la derecha
- Flecha IZQUIERDA: joystick izquierdo
- Flecha ARRIBA: joystick hacia arriba
- Flecha ABAJO: joystick hacia abajo
-
- Otros detalles: ver vectrex.vhd
- Para entradas USB y salida de audio SGT5000, vea mi otro proyecto: xevious_de10_lite
-------------------------------------------------- -------------------------------
- Utilice la herramienta \ vectrex_unzip \ make_vectrex_proms.bat para crear archivos rom vhdl
-
--make_vhdl_prom exec_rom.bin vectrex_exec_prom.vhd (siempre necesario)
-
--make_vhdl_prom scramble.bin vectrex_scramble_prom.vhd
--make_vhdl_prom berzerk.bin vectrex_berzerk_prom.vhd
--make_vhdl_prom frogger.bin vectrex_frogger_prom.vhd
--make_vhdl_prom spacewar.bin vectrex_spacewar_prom.vhd
--make_vhdl_prom polepos.bin vectrex_polepos_prom.vhd
--make_vhdl_prom ripoff.bin vectrex_ripoff_prom.vhd
--make_vhdl_prom spike.bin vectrex_spike_prom.vhd
--make_vhdl_prom startrek.bin vectrex_startrek_prom.vhd
--make_vhdl_prom vecmania1.bin vectrex_vecmania1_prom.vhd
--make_vhdl_prom webwars.bin vectrex_webwars_prom.vhd
--make_vhdl_prom wotr.bin vectrex_wotr_prom.vhd
-------------------------------------------------- -------------------------------
Licencia ###


Este programa es software libre: puede redistribuirlo y / o modificarlo según los términos de la Licencia Pública General GNU publicada por la Free Software Foundation, ya sea la versión 3 de la Licencia o (a su elección) cualquier versión posterior.
Este programa se distribuye con la esperanza de que sea útil, pero SIN NINGUNA GARANTÍA; incluso sin la garantía implícita de COMERCIABILIDAD o APTITUD PARA UN PROPÓSITO PARTICULAR. Consulte la Licencia pública general GNU para obtener más detalles.
Debería haber recibido una copia de la Licencia Pública General GNU junto con este programa. De lo contrario, consulte http: // www.gnu.org / licence /. ''

### License


This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version.
This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License for more details.
You should have received a copy of the GNU General Public License along with this program. If not, see http://www.gnu.org/licenses/.
