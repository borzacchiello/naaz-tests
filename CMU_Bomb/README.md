Taken from https://github.com/angr/angr-doc/tree/master/examples/cmu_binary_bomb

To solve the challenge with `naaz` run:

#### Phase 1

``` bash
$ naaz_finder \
    -f 0x400ef7 \
    -a 0x40143a \
    -J phase1.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
input (512) : Border relations with Canada have never been better.\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00
```

#### Phase 2

``` bash
$ naaz_finder \
    -f 0x400f3c \
    -a 0x40143a \
    -J phase2.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
val1 (32) : \x01\x00\x00\x00
val2 (32) : \x02\x00\x00\x00
val3 (32) : \x04\x00\x00\x00
val4 (32) : \x08\x00\x00\x00
val5 (32) : \x10\x00\x00\x00
val6 (32) :  \x00\x00\x00
```

#### Phase 3

``` bash
$ naaz_finder \
    -f 0x400fc9 \
    -a 0x40143a \
    -J phase3.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
val1 (32) : \x07\x00\x00\x00
val2 (32) : G\x01\x00\x00
```

#### Phase 4

``` bash
$ naaz_finder \
    -E cov \
    -f 0x40105d \
    -a 0x40143a \
    -J phase4.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
val1 (32) : \x07\x00\x00\x00
val2 (32) : \x00\x00\x00\x00
```

#### Phase 5

``` bash
$ naaz_finder \
    -f 0x4010d9 \
    -a 0x40143a \
    -J phase5.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
input (48) : \x09\xff\x0e\x05\x06\x07
```

#### Phase 6

``` bash
$ naaz_finder \
    --disable-lazy-solving \
    -E bfs \
    -f 0x4011f7 \
    -a 0x40143a \
    -J phase6.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
val1 (32) : \x04\x00\x00\x00
val2 (32) : \x03\x00\x00\x00
val3 (32) : \x02\x00\x00\x00
val4 (32) : \x01\x00\x00\x00
val5 (32) : \x06\x00\x00\x00
val6 (32) : \x05\x00\x00\x00
```

#### Phase Secret

``` bash
$ naaz_finder \
    -f 0x401282 \
    -a 0x40143a \
    -J phase_secret.json \
    -o output \
    ./bomb

$ cat output/cfg_syms.txt
input (64) : \x00\x00\x00\x00\x00\x00\x00\x14
```
