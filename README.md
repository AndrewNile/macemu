# Basilisk II
Tweaked for compilation using the mxe.cc build environment on a Linux system. Forked from kanjitalk755's fork.

mxe creates 100% statically-linked executables.

NB: You can only use the 32-bit compiler (i686-w64-mingw32) at the moment.

#### BasiliskII
```
MinGW x86        JIT
```
#### SheepShaver
```
MinGW x86        JIT
```
### How To Build

#### BasiliskII
Preparation:
```
(from the mxe directory)
$ make gtk2 sdl2 sdl2_image sdl_sound zlib zstd
```
Build:
```
(Step 1: Generates config.h for host compiler)
$ cd macemu/BasiliskII/src/uae_cpu
$ ../Unix/autogen.sh

(Step 2: The rest)
$ cd macemu/BasiliskII/src/Windows
$ ../Unix/autogen.sh --host=i686-w64-mingw32.static
$ make
```
Build Options (append to the end of autogen.sh command):
```
--enable-jit-compiler   enable JIT compiler [default=yes]
--enable-jit-debug      activate native code disassemblers [default=no]
--enable-fpe=FPE        specify which fpu emulator to use [ieee uae x86][default=ieee]
--enable-addressing=AM  specify the addressing mode to use [direct banks fastest][default=fastest]

--with-gtk              use GTK user interface [default=yes]
--with-sdl3             use SDL 3.x, rather than SDL 2.x [default=no]

--enable-vosf           enable video on SEGV signals [default=no]
--with-bincue           Allow cdrom image files in bin/cue mode [default=no]
```
#### SheepShaver
Preparation: same as BasiliskII  
  
Build:
```
$ cd macemu/SheepShaver
$ make links
$ cd src/Windows
$ ../Unix/autogen.sh --host=i686-w64-mingw32.static
$ make
```
