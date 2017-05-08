This is a collection of statically linked tools/libraries for a RT-N56U Wi-Fi router
running Padavan firmware (https://bitbucket.org/padavan/rt-n56u). Inside, it's
just a LSB MIPS32 with uClibc, so they should run on any such system.

## compilation notes

To reduce the size of the statically linked stuff, compile it with
CFLAGS='-Os -fdata-sections -ffunction-sections' and then link with
LDFLAGS='-Wl,--gc-sections -Wl,--strip-all'. 

First, you place every function into a separate section and then
prune all unused sections and symbols during linking.