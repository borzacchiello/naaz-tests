Taken from https://github.com/angr/angr-doc/blob/master/docs/more-examples.md

To solve the challenge with `naaz` run:

``` bash
$ naaz_finder \
    -f 0x40083e \
    -o output \
    ./unbreakable-enterprise-product-activation \
    @@:print:51
$ cat output/argv.txt
0: ./unbreakable-enterprise-product-activation\x00
1: CTF{0The1Quick2Brown3Fox4Jumped5Over6The7Lazy8Fox9}\x0
$ cat output/stdout.bin
Thank you - product activated

$ ./unbreakable-enterprise-product-activation CTF{0The1Quick2Brown3Fox4Jumped5Over6The7Lazy8Fox9}
Thank you - product activated
```

##### Notes
- `-f 0x40083e`: find a state that reaches address `0x40083e`
- `-o output`: output directory
- `@@:print:51`: the first command line argument is symbolic, and has a length of 51 with only printable characters
