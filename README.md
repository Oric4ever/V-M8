# V-M8
The V-M8 microcomputer

This is a micro-computer built around a 8-bit core with 64 KB of SRAM. This might sound ridiculous in 2020, but it is a joy to program and you get the satisfaction to master every aspect of it. It is able to run different personalities (virtual machines), and one of them is particularly interesting: see the companion project "Turbo Modula-2 Reloaded".

Architecture:

- 8-bits ATmega micro-controller with external memory bus (eg. ATmega128/161/162/1280/1281/2561...): AVR core, modified Harvard architecture.
- 32, 64 or 128 KB of external SRAM
- SD card
- serial port for VT100/ANSI/Xterm terminal
- PS/2 keyboard port

The prototype has an ATmega162 in standard DIP package, it can be built on a standard prototyping board.

There are plenty of AVR designs on the Internet, however this one has the objective to be a fully general micro-computer, when nearly all of the others are designs of embedded systems or game-consoles. This means that this V-M8 computer runs an operating system and associated environment development whereas all the other designs are programmed using development tools on PCs (either running MacOSX/Windows/Linux).

Due to the modified Harvard architecture, the V-M8 computer only runs native code from its integrated flash eprom. So, the rom typically contains code for a virtual machine (hence the V-M8 name). Currently, a few personalities have been programmed: a 6502 emulator, a 8080 and Z80 emulators running CP/M, and more recently a Modula-2 virtual machine allowing to run the Turbo Modula-2 Reloaded system (see companion repository).

TODO:
- currently the prototype has no video capability, so the V-M8 computer needs a serial terminal. In a quest of minimalism, I would like to implement the video output with a small CPLD (such as an XC9536). For now, the prototype runs very satisfactorily with different


