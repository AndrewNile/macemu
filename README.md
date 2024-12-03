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
preparation:
```
(from the mxe directory)
$ make gtk2 sdl2 sdl2_image sdl_sound zlib zstd
```
build:
```
$ cd macemu/BasiliskII/src/Windows
$ ../Unix/autogen.sh --host=i686-w64-mingw32.static
$ make
```
#### SheepShaver
##### MinGW32/MSYS2
preparation: same as BasiliskII  
  
build:
```
$ cd macemu/SheepShaver
$ make links
$ cd src/Windows
$ ../Unix/autogen.sh --host=i686-w64-mingw32.static
$ make
```
