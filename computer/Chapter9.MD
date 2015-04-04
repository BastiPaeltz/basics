# Virtual Memory

* if too many processes need too much memory -> some processes are not able to run properly 

* **virtual memory** is an elegant interaction of harware exceptions, hardware address translation, main memory, disk files and kernel software

* provides 3 important capabilities:
  1. uses main memory efficiently by treating it as cache for an address space stored on disk
  2. simplifies memory management by providing each process with a uniform address space
  3. protects address space of each program from corruption by other programs

## physical memory and virtual addressing

* RAM = array of M contignous byte-sized cells
* each byte has unique **physical address (PA)**
* CPU accesses memory by generating virtual address (VA) -> **virtual addressing**
  * converted to appropiate physical address before being sent to memory 
  * converting VA to PA is known as *address translation*  
  * requires close cooperation between CPU and OS -> dedicated hardware on CPU chip called * memory management unit* (MMU) does the translating


## Address space

* ordered set of nonnegative integer addresses
* makes clean distincion between data objects (bytes) and their attributes (addresses) 
  * each data object can have multiple addresses
  * -> each byte of main memory has virtual address chosen from virtual address space 
  * as well as a physical address from physical address space

### VM as tool for caching

* v-memory gets partitioned into fixed size blocks called *virtual pages* (VPs)
  * at any point in time page is partitioned into 3 subsets:
    1. **Unallocated**: page has not yet been allocated (or created), have no data associated -> don't occupy space on disk
    2. **Cached**: currently cached in physical RAM, allocated
    3. **Uncached**: not cached in physical RAM, allocated

### advantages of VM

* simplifying linking
  * seperate address space allows processes to use same basic format of memory image regardless of where code and data reside in actual memory, e.g. stack occupies highest address space and grows downwards -> simplifies design and implementation of *linkers*

* simplifies loading
  * when bytes are loaded into v-memory, nothing is copied from disk 
  * gets copied when needed / page is referenced, e.g. CPU fetches instruction

* simplifies sharing
	* e.g. printf C library function gets mapped from virtual page to actual physical memory page for each program which needs printf

* simplifies memory allocation
  * providing additional memory for user processes is easy with virtual memory

* simplifies memory protection 
  * incorporates protection bits

## summary

* address translation must be integrated with the operation of any hardware caches (L1, L2 ...) 

* memory mapping = associating v-memory with chunks of files on disk

