# About #

This is collection of (almost) statically linked binaries and libraries built for 32-bit LSB MIPS processor.

uClibc and libgcc may be linked dynamically.

# Compilation notes #

To reduce the size of the statically linked stuff, compile it with
CFLAGS='-Os -fdata-sections -ffunction-sections' and then link with
LDFLAGS='-Wl,--gc-sections -Wl,--strip-all'. 

First places every function into a separate section and then linker
prunes all unused sections and symbols.
