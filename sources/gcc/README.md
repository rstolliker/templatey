# C Project template

This is a project template for the C language using the gcc compiler.

Put all .c and .h files in /src/ to be compiled by the makefile.
Object files go in the /out/ directory.
Final program will be put in root directory.

## Makefile Options

`make`: compiles all files

`make run`: runs the compiled program

`make clean`: deletes program and object files

`make memcheck`: runs compiled program with valgrind