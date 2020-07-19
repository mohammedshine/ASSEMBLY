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
#### ESI Source index for string operations
#### EDI Destination Index for string operations
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
#### ESP Extended Stack pointer always points to top of the stack
#### EBP Extended Base  pointer

The 4 registers EAX, EBX, ECX, EDX has a subregister of 16 bits and 2 subregisters of 8bits each.

- AX is the primary accumulator; it is used in input/output and most arithmetic instructions. For example, in multiplication operation, one operand is stored in EAX or AX or AL register according to the size of the operand.

- BX is known as the base register, as it could be used in indexed addressing.

- CX is known as the count register, as the ECX, CX registers store the loop count in iterative operations.

- DX is known as the data register. It is also used in input/output operations. It is also used with AX register along with DX for multiply and divide operations involving large values.

#### EIP Exteded Instruction Pointer always points to the next instruction to be executed.

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
