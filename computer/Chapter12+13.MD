# Concurrent programming

* modern OS provide following ways to achieve concurrency:
  * *processes* - each logical control flow is process with own virtual address space and scheduled and maintained by kernel 
  * *IO multiplexing* applications schedule own logical flow explicitly in context of a single process
  * *Threads* logical flows that run in context of a single process and are scheduled by kernel, hybrid of other 2 approaches (same virtual address space sharing but scheduled by kernel)

## Processes 

* much file descriptor :(

## multiplexing

* laime

## threads

* **Thread execution Model**: threads are not in parent-child relationships, but form a pool of peers
* main thread = first thread that runs in the program
* **semaphores** by Dijkstra
* readers-writers problem

### thread safety

* Class 1: **functions do not protect shared variables** 
* Class 2: **functions that keep state across multiple invocations** 
* Class 3: C- related
* Class 4: **functions that call thread-unsafe functions** 

* important class of thread-safe functions: **reentrant functions**
* dont reference any shared data when they are called by multiple threads

* races - when it is necessary for stability of program that thread x finishes before thread y
* deadlocks - collection of threads are blocked, waiting for a condition that will never be true

## error handling

* ANGUCKEN
