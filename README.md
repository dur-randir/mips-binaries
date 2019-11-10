This is a collection of (almost) statically linked binaries and libraries for a MIPS
based Wi-Fi router RT-N56U running Padavan firmware (https://bitbucket.org/padavan/rt-n56u).

uClibc and libgcc may be linked dynamically.

## compilation notes

To reduce the size of the statically linked stuff, compile it with
CFLAGS='-Os -fdata-sections -ffunction-sections' and then link with
LDFLAGS='-Wl,--gc-sections -Wl,--strip-all'. 

First, you place every function into a separate section and then
prune all unused sections and symbols during linking.
