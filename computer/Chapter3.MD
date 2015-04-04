# Machine-Level Representation of Programs

- machine code encodes operations that manipulate data, manage memory etc.
* compiler generates machine level code

## Machine level code

* abstraction : ISA -> defines format and behaviour of machine level program 

* program counter: indicates adress of memory with next instruction
* register file: small storage, used to keep track of critical parts of the programs state and hold values (e.g. local variables)

* program uses virtual memory -> only has access to a few MB (not the whole RAM)
	-> holds executable machine code, run time stack, block of allocated memory

* program is simply a sequence of bytes encoding a series of instructions
* C uses the hardware RAM, Java uses java byte code provided with the JVM -> virtual RAM, implemented by software


