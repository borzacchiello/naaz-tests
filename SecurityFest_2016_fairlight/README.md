Taken from https://github.com/angr/angr-doc/blob/master/docs/more-examples.md

To solve the challenge with `naaz` run:

``` bash
$ naaz_finder -f 0x401a91 -o output ./fairlight @@:14
$ cat output/argv.txt
0: ./fairlight\x00
1: 4ngrman4gem3nt\x00
$ cat output/stdout.bin
OK - ACCESS GRANTED: CODE{4ngrman4gem3nt}
$ ./fairlight 4ngrman4gem3nt
OK - ACCESS GRANTED: CODE{4ngrman4gem3nt}
```

##### Notes

- `-f 0x401a91`: find a state that reaches address `0x405afa`
- `-o output`: output directory
- `@@:14`: symbolic argument of length 14
