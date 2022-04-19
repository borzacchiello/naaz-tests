Taken from https://github.com/angr/angr-doc/blob/master/docs/more-examples.md

To solve the challenge with `naaz` run:

``` bash
$ naaz_finder \
    -T 100000 \
    -P \
    -f 0x405afa \
    -a 0x402c3c,0x402eaf,0x40311c,0x40338b,0x4035f8,0x403868,0x403ad5,0x403d47,0x403fb9,0x404227,0x404496,0x40470a,0x404978,0x404bec,0x404e59,0x4050c7,0x405338,0x4055a9,0x4057f4,0x405a2b \
    -o output \
    yolomolo
$ cat output/stdin.bin
HACKCON{VVhYS04ngrY}@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
$ cat output/stdout.bin
YAYY : HACKCON{VVhYS04ngrY}@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
$ ./yolomolo < ./output/stdin.bin
YAYY : HACKCON{VVhYS04ngrY}@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@
```

##### Notes
- `-T 100000`: 100 seconds of timeout for Z3
- `-P`: stdin contains only printable characters
- `-f 0x405afa`: find a state that reaches address `0x405afa`
- `-a 0x402c3c,0x402eaf...`: avoid the listed addresses
- `-o output`: output directory
