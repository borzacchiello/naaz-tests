Taken from https://github.com/angr/angr-doc/blob/master/docs/more-examples.md

To solve the challenge with `naaz` run:

``` bash
$ naaz_finder \
    -f 0x40294b \
    -a 0x402941 \
    -J cfg.json \
    -o output \
    ./baby-re

$ cat output/cfg_syms.txt
val0 (32) : M\x00\x00\x00
val1 (32) : a\x00\x00\x00
val2 (32) : t\x00\x00\x00
val3 (32) : h\x00\x00\x00
val4 (32) :  \x00\x00\x00
val5 (32) : i\x00\x00\x00
val6 (32) : s\x00\x00\x00
val7 (32) :  \x00\x00\x00
val8 (32) : h\x00\x00\x00
val9 (32) : a\x00\x00\x00
val10 (32) : r\x00\x00\x00
val11 (32) : d\x00\x00\x00
val12 (32) : !\x00\x00\x00

$ cat output/stdout.bin
The flag is: Math is hard!
```
