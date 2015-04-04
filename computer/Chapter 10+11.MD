# System Level IO

## Unix IO

* file is sequence of m bytes
* everything is a file, even network devices
* Unix IO allows uniform and consistentcy
  * *opening files* application asks kernel to open file, kernel returns *file descriptor* -> identifies file in all operations on the file
  * each process has at least STDIN(descriptor 0), STDOUT AND STDERR
  * *changing current file position* - kernel maintains file position k (initially 0), position is byte offset from beginning of file  
  * *reading files* -> read copies file data to memory starting at position k and increments k, when k >= read_size -> EOF   
  * *writing files* copies bytes from meory to file starting at pos. k
  * *closing files* programs asks kernel to close file, who respons in freeing the data structures it created when file was opened and restoring descriptor, if a pocess terminates (with files open) kernel closes all files and frees memory resources

## Sharing files

* open files are represented by the kernel as follows:
  * *descriptor table* - each process has own seperate DT whose entries are indexed by the process' open file descriptors
  * *file table* set of open file is represented by a file table -> shared by all processes - each entry consists of current position, reference count and number of descriptors and v-node table, if rc is 0 -> kernel deletes file table
  * *v-node table* shared by all processes, includes file metadata

## Networking

* **sockets** interface, clients and servers establish connection by using socket interface
* socket = endpoint of connection that is presented to apps in form of file descriptor
* clients and servers communicate with each other by reading and writing these descriptors
*     
