# Shell basics

## General 
* use file descriptors: 0 STDIN 1 STDOUT 2 STDERR  
* `find / -name core > /tmp/corefiles 2> /dev/null`  
  * write to /tmp/corefiles and discard error messages to /dev/null  
* `sudo apt-get update && sudo apt-get upgrade`
  * only run upgrade if update **exits with status code 0 (succeeds)**  
* `echo "My shell is ${SHELL} - oh yeah."`  
*My shell is /bin/bash - oh yeah.*  
* important variables (login vars) go into **.profile** or **.bash_profile**  
* **wrap text into " " not ' '**  
```bash
$ mylang="Pennsylvania Dutch"  
$ echo "I speak ${mylang}."  
I speak Pennsylvania Dutch.  
$ echo 'I speak ${mylang}.'  
I speak ${mylang}.    
```
**back ticks used in text**    
```bash
$ echo "There are `wc -l /etc/passwd` lines in the passwd file."  
There are 28 lines in the passwd file.    
```
## filter commands

* **cut** (-d DELIMITER - default: tab -f which fields to include)  
* **sort** - sorts input lines  
* **uniq** - similar to sort  
* **tee** - copy input to two destinations  
```bash
find $(pwd) -name Chapter\* 2> /dev/null | tee /dev/tty | wc -l  
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
```

  * *A common idiom is to terminate a pipeline that will take a long time to run with a tee command so that output goes both to a file and to the terminal window for inspection*

  
* **head** : obsolete by **less**  
* **tail** : -f waits for new lines to be added and prints them - *good for monitoring*  
* **grep** : supports RegEx, -i ignore case, -v non matching lines  

## bash scripting

* **approach of Unix handbook**

    • Develop the script (or script component) as a pipeline, one step at a time, entirely on the command line.   
    • At each step, use the shell’s command history to recall pipelines and the
    shell’s editing features to tweak them.   
    • Send output to standard output and check to be sure it looks right.
    • Until the output looks right, you haven’t actually done anything, so
    there’s nothing to undo if the command is incorrect.  
    • Once the output is correct, execute the actual commands and verify that
    they worked as you intended.  
    • Use **fc** to capture your work, then clean it up and save it.  

## Input and Output

* **output** echo or printf
* **input** read

## CMD VARS

* **$1** **$2** - cmd line array
* **$0** - calling executable
* **$#** - number of cmd line args
* **$\*** - all arguments at once
* **$?** - exit status of last command executed in shell

* **more found in Unix handbook from page 42 on**

## Best Practices

* scripts should **print usage message**  
* **validate input** and sanity check computed values  
* return **appropiate exit code** -> non-zero = failure 
* **naming conventions**  
* *keep var names short but they should reflect what they keep*  
* **comment code**  
* *Comment at the level you yourself will find helpful when you return to
the script after a month or two. Some useful points to comment on are
the following: choices of algorithm, reasons for not doing things in a
more obvious way, unusual paths through the code, anything that was a
stumbling block during development*
* use **bash -x**
* Error messages must go to **STDERR**
* State **what operation** failed

 
