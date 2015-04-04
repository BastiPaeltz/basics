# Exceptional control flow

- abrupt changes in control flow of programs

* how my application interacts with the operating system

  * difference between hardware and software exceptions

## hardware exceptions

* abrupt change in control flow

### classes of exceptions

#### interrupts

* occur **asynchronously** as result of signals from I/O devices

* returns to next instruction 

  * program continues as if interrupt never happened


#### traps

* occur **synchronously**

* are intentional

* return to next instruction

* provides interface between user program and kernel : **system call**

  * e.g. user program needs to read a file

  * system call runs in *kernel mode*

#### faults

* synchronously

* results from error conditions that the exception handler might be able to correct

  * e.g. page fault exception = reference of virtual adresss whose physical page is not resident in memory -> must be retrieved from disk

* returns control to instruction which caused the fault


#### aborts

* synchronously


* result from unrecoverable fatal errors
  * e.g. RAM is corrupted

* returns to abort routine which exectues the program

#### exception examples

* divide error - exception number 0 - **fault**

* machine check (occurs from fatal hardware error) - exception number 18 - **abort**

* system call - exception number 128 (0x80) - **trap**

#### system calls examples (linux)

* exit - nr: 1 - terminate process

* read - nr: 3 - read file

* kill - nr: 37 - send signal to another process

* getpid - nr:20 - get process ID

## Processes

* exceptions are the building blocks which allow the notion of **processes**

* has an indepent logical control flow 
  
  * provides illusion that program has exclusive use over **processor**

* private address space 

  * provides illusion that program has exclusive use over **memory**

### Logical control flow

* program's instructions get executed by program counters (PCs) = logical flow

#### Concurrent control flows

* a logical flow whose execution overlaps with another flow is a **concurrent flow**
	
  * both flows run *concurrently* 

#### Private Address space

* each program has its own private address space

  * provided by the OS

#### User and Kernel Mode

* way to restrict instructions that an application can execute as well as address pace it can access

* solution : ** user and kernel mode**

* if *mode bit* is set on processor (register) then program is in kernel mode else user mode

* programs in user mode CAN NOT:

  * halt the processor
  * change mode bit
  * initiate I/O operation
  * not allowed to reference data or code from kernel's address space

* a program is initially in user mode 

  * needs way to change to user mode to for example read from a file
  * done via exception: mostly trapping (system calls)
  * up on return (e.g. file was read successfully) program goes right back to user mode

### context switches

* kernel implements multitasking via exceptional control flow known as **context switch**

* kernel maintains context for each running process
  
  * consists of regsters, stacks (user and kernel), PC, kernel data structures

* during execution kernel can decide to **preempt** current running process and restart a previously preemted one
	* known as *scheduling*

* kernel transfers control to new process using the context switch mechanism, which:
  * saves context of current process
  * restores saved context of previous process
  * passes control to the (previous) process

### Process control

* each process has unique PID

* three states of processes
  1. **Running** - process is either executing on CPU or waiting to be executed (will eventually be scheduled by kernel)
  2. **Stopped** - process is suspended and will not be scheduled
  3. **Terminated** - process is stopped *permanently* 

FORK is important ... but COMPLEX

### Signals

* Unix **signal** allows processes and kernel to interrupt other processes
* kill system call

* example of signals:
	* SIGHUP - Terminate - Terminal line hangup
	* SIGINT - Terminate - Interrupt from Keyboard
	* SIGILL - Terminate - Illegal instruction
	* SIGCONT - Ignore - Continue process if stopped
	* SIGWINCH - Ignore - Window size changed

* a signal is a small message that notifies a process that an event of some type has occured in the system

* each signal corresponds to some kind of system event

* normally exceptions are processed by kernels exception handlers
  * are not visible to user processes
  * signals provide a way to exposing exceptions to them (user processes)
  * e.g. a divide by zero triggers a SIGFPE signal, a ctrl-c triggers a SIGINT 
  * kernel sends that signal to user process

#### signal terminology

* *sending a signal*: the kernel sends signal to destination process because of 1 of 2 reasons: kernel detected a system event (dvide by zero for instance) or another process invoked the **kill** function

* *receiving a signal* process is forced by kernel to reat in some way to that signal
  * can ignore signal, terminate or catch the signal 

#### signal handling issues

* Pending signals are blocked
* Pending signals are not queued
* System calls can be interrupted

COMPLEX 

### Manipulating processes

* ps
* top
* pmap - memory map of process
* /proc - virt. file system

## summary

* ECF occurs on all levels of the computer and is a basic mechanism for providing cocnurrency

* hardware exceptions are abrupt changes in control flow and get triggered by events in processor

* on OS level kernel uses exceptions to provide fundamental notion of a process

*   