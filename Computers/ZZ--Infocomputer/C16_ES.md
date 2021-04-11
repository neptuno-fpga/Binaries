## C16
#### Core portado por @NeruoRulez desde MiST port por Till Harbaum

Este es el código fuente del puerto MIST del proyecto FPGATED. El puerto MIST tiene los siguientes cambios sobre la versión original:

Scandoubler VGA (se puede desactivar a través del archivo de configuración mist.ini)
MIST OSD
Integración de joystick
Disposición de memoria conmutable de 16k / 64k
kernel incorporado se puede sobrecargar (por ejemplo, cambiar a NTSC)
inyección directa de PRG en la memoria c16
floppy 1541 (solo lectura) tomado de http://darfpga.blogspot.de/2015/05/fpga64027-with-c1541sd-sources-available.html
FPGATED v1.0 Copyright 2013-2016 Istvan Hegedus

FPGATED es un núcleo FPGA de ciclo exacto para el chip TED MOS 7360/8360 escrito en lenguaje verilog. MOS 7360/8360 es un chip complejo que proporciona control de gráficos, sonido, bus y memoria para las computadoras de 8 bits de la serie Commodore 264, a saber, Commodore Plus4, Commodore 16 y Commodore 116.

Además del módulo principal de TED, FPGATED contiene una implementación C16 simple que utiliza el núcleo TED y la plataforma Papilio One 500k de Gadget Factory con un ala IO personalizada llamada Papilio TEDWing. El núcleo de CPU 6502 de C16 es creado por Peter Wendrich en vhdl y se toma del proyecto FPGA64 con el permiso del autor.

Para obtener más detalles técnicos y la construcción del módulo Papilio TEDWing, visite https://hackaday.io/project/11460-fpgated

Archivos

basic_rom.v C16 / Plus4 Módulo rom básico c16.v Este es el módulo TOP de FPGATED que implementa una computadora C16 c16_testbench.v C16 testbench para simulación c16_keymatrix.v Módulo de emulación de matriz de teclado C16 / Plus4 colors_to_rgb.v Módulo de conversión de código de color TED a 12bit Valores RGB cpu65xx_e.vhd 6502 core vhdl header cpu65xx_fast.vhd 6502 core vhdl code dram.v Módulo DRAM para implementación de memoria FPGA SRAM interna kernal_rom.v C16 / Plus4 Módulo rom kernal mos6529.v MOS 6529 Módulo de emulación de chip IO mos8501.v MOS 8501 Carcasa de CPU para 6502 core palclockgen.v Módulo Xilinx DCM para señal de reloj del sistema PAL ps2receiver.v Módulo receptor de teclado PS2 ram.v RAM simulada para banco de pruebas ted.v MOS 7360/8360 FPGA core

basic.hex C16 / Plus4 BASIC rom volcado hexadecimal Diag264_NTSC.hex Diag264 NTSC kernal volcado hexadecimal Diag264_PAL.hex Diag264 PAL kernal volcado hexadecimal kernal_NTSC.hex C16 / Plus4 NTSC Kernal rom hexadecimal volcado kernal_PAL.hexade PAL.

TEDwing.ucf Archivo ucf Xilinx para Papilio TEDwing bin2hex.pl Script Perl para crear un volcado hexadecimal de archivos de imagen rom binarios

c16_PAL.bit Un núcleo PAL FPGATED compilado para la plataforma Papilio usando el ala FPGATED

Las instrucciones de instalación son para las plataformas FPGA de Xilinx, pero los archivos de origen, con la excepción de palclockgen.v y los archivos ucf de Xilinx, se pueden utilizar para los FPGA de otros proveedores. Algunos módulos están usando la directiva específica de Xilinx (* RAM_STYLE = "BLOCK" *) para forzar a la herramienta de síntesis a usar la RAM de bloque interna FPGA para ciertas matrices. En el caso de FPGA de otros proveedores, consulte la documentación específica del proveedor para generar bloques de RAM.

La construcción de FPGATED en la plataforma Papilio requiere un ala adecuada. Se puede usar el megawing Arcade, pero carece de memoria externa y bus IEC para conexiones periféricas. Por eso recomiendo construir TEDwing diseñado por mí. Busque eagle PCB y archivos esquemáticos en el paquete fuente FPGATED. Aunque FPGATED se puede sintetizar en una placa Papilio One usando el chip Spartan3E, recomiendo optar por la plataforma Papilio Pro que tiene una SDRAM externa de 8Mbyte y una FPGA Spartan 6 LX9 que tiene más sram interno. En ambos casos, hay muchos recursos gratuitos en FPGA para FPGATED (si usa una ram externa de 64k).

Instrucciones de instalación:

Cree un nuevo proyecto en Xilinx ISE Webpack y elija la familia FPGA adecuada para la implementación.
Elija utilizar HDL verilog y vhdl para el diseño.
Agregue todos los archivos * .v al proyecto
Con el asistente de ISE DCM, cree un generador de reloj para FPGATED. Use la salida CLKFX de DCM y especifique 28.37515MHz PAL o 28.63636MHz para el sistema NTSC Este será el reloj FPGA principal conectado a la señal clk de todos los módulos Modifique C16.v para usar la instanciación de DCM adecuada (fuera del alcance de este documento)
Abra kernal_rom.v y descomente el archivo Kernal adecuado (Kernal_NTSC.hex o Kernal_PAL.hex) para usar. Incluso puede usar una rom personalizada o JiffyDos si la posee (JiffyDos está funcionando bien, lo he probado). Las roms Diag264 se incluyen con fines de prueba.
Si no usa TEDwing, modifique o reemplace el archivo TEDwing.ucf para una configuración de pines adecuada
La salida de video de FPGATED es una señal PAL / NTSC RGBS, por lo que necesitará un cable personalizado VGA-> euroconector para conectarlo a un monitor o televisor. El cable es idéntico a los cables euroconectores minimig (consulte el diagrama de cableado en Internet)
Disfruta FPGATED.

Consulte https://hackaday.io/project/11460-fpgated para obtener instrucciones de instalación detalladas.

Señales del módulo TED:

input wire clk reloj FPGA principal debe ser 4 * dot clk por lo que 28.375152MHz para PAL y 28.63636 para NTSC cable de entrada [15: 0] addr_in 16 bits bus de direcciones en el cable de salida [15: 0] addr_out 16 bits dirección bus out cable de entrada [ 7: 0] data_in bus de datos de 8 bits en el cable de salida [7: 0] data_out 8 bits de datos