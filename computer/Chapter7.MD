# Linking

* putting all needed pieces together into 1 executable file

  * can be dont at compile time, run time or load time (when program is loaded into memory)

  ## linking process

  * preprocessor (cpp) -> compiler (cc) -> assembler (as)

  * main.i -> main.s -> main.o

  * the linker (ld) then links all .o files together to an executable 


  
  
  * Relocatable object file. Contains binary code and data in a form that can be
  combined with other relocatable object files at compile time to create an
  executable object file.
  
  * Executable object file. Contains binary code and data in a form that can be
  copied directly into memory and executed.
  
  * Shared object file. A special type of relocatable object file that can be loaded
  into memory and linked dynamically, at either load time or run time.

  * shared libraries are shared across the whole system 

  * static linking at compile time
  * dynamic linking at run or load time
  