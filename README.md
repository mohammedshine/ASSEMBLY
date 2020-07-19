# 1. What is the importance of Assembly Language in Bufferoverflow?
- Registers to understand about program flow
- Instructions for exploit development
# 2. Fundamentals, Registers and Instructions and the tool GDB
# 3. What is assembly language?
An assembly language is a language that can be used to directly tell the computer what to do.
An assembly language is almost exactly like the machine language that a computer can understand,
except that it uses words in place of numbers.
# 4. Registers
Temporary storage area in a CPU.
instructions and memory address
# Let's Talk about registers
## General Purpose Registers
which are mainly used for arithmetic operations and data movement
Each register can be addressed as 32 bit value
#### EAX 
#### EBX
#### ECX
#### EDX
#### ESI Source index
#### EDI Destination Index

The 4 registers EAX, EBX, ECX, EDX has a subregister of 16 bits and 2 subregisters of 8bits each.


# Simple Assembly code
- global _start : the directive global tells the linker that the entry point of our program is _start.
- _start : start of program
- mov eax,8 : moves 8 to eax
- mov eax,ebx : moves value of ebx to eax
# Compiling and running using gdb
```
Assemble

nasm <filename>.nasm -f elf32 -o <out>.o

-f : format type
-o : output file

Linking

32 bit machine: ld <out>.o -o out 64 bit machine: ld -m elf_i386 -o <file> <file>.o

Examine register

gdb ./out
```
