# Shell basics

## General 
* use file descriptors: 0 STDIN 1 STDOUT 2 STDERR
* find / -name core > /tmp/corefiles 2> /dev/null
  * write to /tmp/corefiles and discard error messages to /dev/null
* sudo apt-get update && sudo apt-get upgrade
  * only run upgrade if update **exits with status code 0 (succeeds)**
* echo "My shell is ${SHELL} - oh yeah."
*My shell is /bin/bash - oh yeah.*
* important variables (login vars) go into **.profile** or **.bash_profile**

**wrap text into " " not ' '**  
    $ mylang="Pennsylvania Dutch"  
    $ echo "I speak ${mylang}."  
    I speak Pennsylvania Dutch.  
    $ echo 'I speak ${mylang}.'  
    I speak ${mylang}.  

**back ticks used in text**  
$ echo "There are \`wc -l /etc/passwd\` lines in the passwd file."  
There are 28 lines in the passwd file.  

## filter commands

* cut (-d DELIMITER - default: tab -f which fields to include)
* sort - sorts input lines
* uniq - similar to sort
* tee - copy input to two destinations
  * find $(pwd) -name Chapter\* 2> /dev/null | tee /dev/tty | wc -l  
    /home/sebastian/basics/computer/Chapter1.MD   
    /home/sebastian/basics/computer/Chapter9.MD  
    /home/sebastian/basics/computer/Chapter7.MD  
    /home/sebastian/basics/computer/Chapter8.MD  
    /home/sebastian/basics/computer/Chapter12+13.MD  
    /home/sebastian/basics/computer/Chapter2.MD  
    /home/sebastian/basics/computer/Chapter6.MD  
    /home/sebastian/basics/computer/Chapter3.MD  
    /home/sebastian/basics/computer/Chapter 10+11.MD  
    9  

* * *A common idiom is to terminate a pipeline that will take a long time to run with a
tee command so that output goes both to a file and to the terminal window for
inspection*

* head - obsolete by **less**
* tail - -f waits for new lines to be added and prints them - *good for monitoring*
* grep - -i ignore case