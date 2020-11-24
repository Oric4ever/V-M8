# V-M8
This is the hardware design repository for the V-M8 microcomputer

The V-M8 is a micro-computer built around a 8-bit core with 64 KB of SRAM. This might sound ridiculous in 2020, but it is a joy to program and you get the satisfaction to master every aspect of it. It is able to run different personalities (virtual machines), and one of them is particularly interesting: see the companion project "Turbo Modula-2 Reloaded".

Architecture:

- 8-bits ATmega micro-controller with external memory bus (eg. ATmega128/161/162/1280/1281/2561...): AVR core, modified Harvard architecture.
- 64 KB of external SRAM (actually either 2 chips of 32 KB, or a single chip of 128 KB)
- SD card
- serial port for VT100/ANSI/Xterm terminal
- PS/2 keyboard port

The prototype has an ATmega162 in DIP package, it has been built on a standard prototyping board. Here you will find Eagle schematics of the V-M8 prototype, PCB schematics haven't been drawed yet.

Goal: a fully general micro-computer.

There are plenty of AVR designs on the Internet, however this one has the objective to be a fully general micro-computer, when nearly all of the others are designs of embedded systems or game-consoles. This means that this V-M8 computer runs an operating system and associated environment development whereas the other designs are programmed using development tools on PCs (either running MacOSX/Windows/Linux).

Due to the modified Harvard architecture, the V-M8 computer only runs native code from its integrated flash eprom. Game consoles such as the UzeBox have shown that it is possible to provide a boot loader with flash reprogramming capability in order to load the flash with on-demand applications, however such a scheme is not desired here because flash has a limitation of about 10000 rewrites : reaching this rewrite count would be fast when developing and executing native programs on a general micro-computer.

So, the rom typically contains code for a virtual machine (hence the V-M8 name). Currently, a few personalities have been programmed: a 6502 emulator, a 8080 and Z80 emulators running CP/M, and more recently a Modula-2 virtual machine allowing to run the Turbo Modula-2 Reloaded system (see companion repository).

TODO:
- currently the prototype has no video capability, so the V-M8 computer needs a serial terminal. For now, the prototype runs very satisfactorily with different types of "terminals": Linux PCs, Raspberrys, Android tablets (by attaching an HC05 bluetooth module on the V-M8). But I would like the V-M8 to be fully independent of such a powerful terminal, and thus have an objective of implementing the video output with a small CPLD (such as an XC9536). 
- the audio part hasn't been fully implemented (capacitors and resistors for the line impedance), and the audio firmware hasn't been written yet. I intend to provide a simple interrupt driven output on the PWM registers...


