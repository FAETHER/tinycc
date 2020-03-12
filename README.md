# Tinycc
Single header C99 compiler (TCC)

Entire core of TCC compiler in one file. Including all achitectures. 43000 LOC

# Why?

It may be painful to deal with complex build systems and files may harm code navigation and/or understanding. 
Many people prefer single header libraries, and this is just that, entire compiler is here. 

# Compiling Tcc 

The most simple command will be

For Unix

```
gcc tinycc.c -ldl -lpthread
or bootstrap:
tcc tinycc.c -ldl -lpthread
```

For win32

```
gcc tinycc.c 
or more explicit, both commands equalent.
gcc tinycc.c -DTCC_TARGET_PE -DTCC_TARGET_I386
```

For win64

```
gcc tinycc.c -DTCC_TARGET_PE -TCC_TARGET_X86_64
```

You can add compile defines options youself, look into the file and see what is available or what you need.

Using to build

# Using Tcc

Make _start() function.

To include CRT on windows link library using -luser32 for example. This will link to a dll using user32.def file in ./lib
For reference refer to tinycc.c file. 

------------------------------------------------------------------------
Have not tested on Arm, riscv64 but it should work unless i screwed up.

Move the rest of compiler files needed to actually start using the compiler here.
They are not part of the compiler, but need to be scoped when you compile C programs.
