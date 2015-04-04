# memory hierarchy

## RAM

* 2 varieties - static and dynamic -> SRAM and DRAM
* SRAM for chache memories on and off the CPU chip -> only a few megabytes
* DRAM is used for main memory -> gigabytes
* each DRAM chip is connced to memory controller

* DDR RAM = Double Data Rate RAM, synchrounous communication with controller
* VRAM = Video RAM, used in Graphics Cards, allows writing and reading memory concurrently

--> DRAM and SRAM are volatile, they loose their information if power is turned off
	--> ROM is non volatile
	* most important: Flash memory
	* ROM is used in firmware

* data exchange between CPU and RAM over buses

## Disk storage

* HDD is like a CD -> round

## Locality

* spatial locality: memory location referenced once the program is likely to reference a nearby location soon

* temporal locality: memory location referenced once is likely to be referenced again in the near future multiple times

--> programs with good locality run faster


## Memory hierarchy 

* the smaller the faster
* the larger the slower

## Cache 

* cache hit: if data requested from next higher storage is already stored in the cache
* cache miss: object is not stored in cache, object gets read from next higher storage and written to its cache --> overwrite if cache is full

## Writing cache-friendly code

* cache matters, beware how the compiler arranges your data types and structures in memory

Focus attention on inner loops where bulk of computation and memory accesses occur
Maximixe locality by reading data objects sequentially in the order they are stored in memory
Maximize locality by using data objects as often as possible once it has been read from memory 