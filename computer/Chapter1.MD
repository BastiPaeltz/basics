#General

- Information is bit + context

- compilation process involves multiple stages, e.g. prepocessor, linker, assembly


##Hardware Organisation of a system:


-Buses: connect system components, transport data with a special size, called WORD
	--> usually word = 4 or 8 byte ( = 32 or 64 bit)

-I/O Devices: Connect the system with the outer world, e.g. mouse, network, Graphics Adapter --> Every I/O Device is a file

-Main Memory(RAM): holds program and the data, while the processor is manipulating them. Serves as cache for disk. Organized as array of bytes with unique adresses.

-Processor: interprets instructions in main memory, core = word-sized storage device called Program Counter (PC). At ANY time it points at a adress in the main memory. The processor then reads, interprets and executes the instruction of that adress and the PC eventually points to another adress afterwards.   
	--> ALU : Arithmetic-Logic Unit, mainly does math
	--> Register file: word sized (small) storage device consisting of some registers --> very fast but also very small storage.

##Caches

-The larger the storage, the slower it is
--> fastest storage = registers
-processor-memory gap (easier to speed up processors than RAM)
	- implementation of L1, L2 (sometimes also L3) caches for processors
	- = temporary staging areas for information the processor might need in future 

-basically every storage serves as cache for all bigger storages, for example RAM is a storage for the disk. 



#OPERATING SYSTEM

-layer between application and hardware
	--> protect hardware from misuse of applications
	--> provide applications with uniform methods to operate on the hardware
		--> achieved through abstraction: processes, virtual memory and files


##Processes

* abstraction for a running program

* context switch = saving context of current process, at the same time restoring the context and state of the new process

* system call = instruction that passes control to the OS which then performs a context switch. 

##Threads

- multiple execution units
	--> sharing same code and global data
-better than running multiple processes
-makes programs run faster on systems with multiple processors

##Virtual Memory

* virtual address space 
  * number of well-defined areas, each with a specfiic purpose



##Files

-a sequence of bytes
-every IO device is modelled as a file
	--> IO is performed by reading and writing files


BILD LINUX EINFÜGEN

#Virtual Machines

-provides an abstraction of the entire computer


#Networks

-Network (adapter) = IO device


##Important Themes

###Concurrency and Parallelism

-concurrency = multiple, simultanious activities on a system
-parallelism = use of concurrency to make a system run faster

	--> Thread-Level Concurrency:
		-processor runs multiple threads and uses them efficiently, e.g. doesn't block while loading data
		-hyperthreading = CPU can execute multiple control flows at once

	--> Instruction-Level Parallelism:
		-pipelining = instructions are divided in stages which can be operated in parallel

	--> SIMD - Single Instruction Multiple Data Parallelism:
		-special processor hardware allows a single instruction to be performed in parallel in multiple operations, e.g. compute adding of 4 floats
			--> mainly used for image, audio or video processing




