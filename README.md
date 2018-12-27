# TinyBasic64
A Tiny BASIC cross-compiler for the Commodore-64 

This program will compile Tiny BASIC source code to Commodore-64 assembly in DASM format.

## Usage
1. Pick a pre-built executable from the `bin/` directory or type `dub build` to compile from source (install dub first)
2. Type `./TinyBasic64 source.bas > target.asm` to compile basic source code to asm

## Differences in syntax
There are a few differences to the original gramamar definition ([read Tiny BASIC on Wikipedia](https://en.wikipedia.org/wiki/Tiny_BASIC)):
1. Line numbers are optional. You can use labels, line numbers or both. The following example will compile:
```
10 rem this line is numbered
20 gosub my_sub
print "this is just a line"
end
my_sub:
  print "this will be printed first"
  return
```
2. Variable names are case-sensitive and they can consist of any letters, numbers or underscores of any length. (they must not start with a number though).
3. `GOSUB <expression>` and `GOTO <expression>` are not supported. You can only use labels or line numbers.
4. `POKE n,m` and `PEEK(n)` are supported
