clgpustress
===========

Heavy OpenCL GPU stress tester

### IMPORTANT CAUTION!!!!!

THIS PROGRAM IS VERY DANGEROUS FOR GRAPHICS CARD AND CAN OVERHEAT OR DAMAGE YOUR GRAPHICS CARD! PLEASE USE CAREFULLY
THIS PROGRAM. I RECOMMENDED TO RUN THIS PROGRAM ON ALL STOCK PARAMETERS (CLOCKS, VOLTAGES, ESPECIALLY GPU MEMORY CLOCK).

THIS PROGRAM IS INFLUENCED BY PRIMEGRID GENEFER AND ALSO VERY SENSITIVE FOR ANY OVERCLOCKING, BUT MUCH BETTER LOADS GPU CORE. MOREOVER MUCH BETTER BURNS GRAPHICS CARD THAN FURMARK!

THIS PROGRAM IS TESTED ONLY IN RADEON HD 7850 AND CAN BEHAVES INCORRECTLY ON OTHER GRAPHICS CARDS.

YOU ARE USING THIS SOFTWARE ONLY FOR OWN RISK!

### Software requirements:

- popt library
- OpenCL support
- cl.hpp (OpenCL C++ support)
- compiler with C++11 support
- Linux (currently this system is supported).

### Memory requirements

Program requires 256*workSize bytes in graphics card memory. WorkSize currently is computed in following way:
maxComputeUnits * maxWorkSize * workFactor. For example workFactor=512 in Radeon HD7850 requires 512 MB, because:
16 * 256 * 512 * 256 = 536870912 -> 512MB.

Program needs also host memory: 192*workSize bytes for buffers.

### Usage

- print help: ./gpustress -?

- run stress: ./gpustress -G -W512 -S32

- run specific OpenCL code (only in program directory): ./gpustress -G -W512 -S40 -P gpustressPW.cl

Currently program should be run in project directory, because loads OpenCL source codes available in this place.