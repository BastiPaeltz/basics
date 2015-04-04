# Representing and Manipulating Data

## Information storage

* computers store information in 2 value signals -> bits
* group of bits can be interpreted -> bit patterns have meaning

* most computers use blocks of eight bits = BYTES as smallest adressable unit of memory

### Hexadecimal notation
	
* most convenient way to describe bit patterns
* 0 to 9 and A to F -> base 16
* conversion between hexadecimal and binary:

* 2^n can be converted to hex:
* n = i + 4j, j times trailing '0's,i=0 > hex: 1, 
									i=1 > hex: 2, 
									i=2 > hex: 4,
									i=3 > hex: 8
e.g. : n^11 = 3 + 4 * 2 yields 0x800

### word size

* indicating nominal size of integers and pointers
  * with n-byte word size, virtuall adress can range from 0 to (2^n)-1 -> 2^n bytes acccessable
  * 32 bit systems, 4gb virtual address space

### Data size

* computers and compilers use different ways to encode data types
* e.g. smalles data type in C is char: 1 byte address space

### Byte ordering and addressing

* little endian vs big endian
	* most significant bit first (big) or last (little)?
	* Intel = little endian
	* becomes an issue when binary data is communicated over network

### summary

* different encodings used for different data types
* chance of overflow or underflow, especially when casting between data types
* floating point numbers only approximates *> limited precision

 
