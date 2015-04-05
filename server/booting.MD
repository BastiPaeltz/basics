# Booting
* kernel is loaded into memory and begins to execute
* **init** process is invoked (PID: 1)
  * spawns system deamons and startup scripts 

**see page 78 and following**

##  GRUB

* config in **/boot/grub/grub.conf (or cfg)**
* also editable via **grub command line**
* grub can also boot to **single user mode**

## Startup scripts

* located in **/etc/init.d**
  * understand *stop*, *start* and also probably *restart*
* **DONT** modify startup scripts
* only modify appropiate **config** files

## init run levels

* **level 0** - system is shut down
* **level 1 and S** - single user mode
* **level 2 through 5** - support for networking
* **level 6** - reboot 
* run level changed via **telinit** command

## Rebooting and shutting down

* use **shutdown**
* halt: **-h**, reboot: **-r**  
