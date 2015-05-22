# Software installation and managemenet

* for systems > 10 hosts, do **network installation**
* **pXe** allows systems to boot from network, **PXELINUX**
* Debian uses **debian installer** and its utility **debconf**
* Red Hat uses comfortable **Kickstart**

## Managing packages

* **dpkg + APT**
* list all installed packages with **dpkg -l** (leading ii = *installed*)

## APT

* main config file of APT is **/etc/apt/sources.list**
* mirror with **apt-mirror** package


## localization

* **cfengine**
* **rsync** is efficient since it only transfers incremental changes


## sharing software over nfs

* **Unix handbook p. 411+**


    * Bind account (read-only):
        - Name: vmail, Password: pIu5r0S0c3Ovc8sufdRC2UdcYYT4RC
    * Vmail admin account (read-write):
        - Name: vmailadmin, Password: jRRUI4Oe3azvdtYsaf01XQu7oxVWbW
    * Database stored in: /var/lib/postgresql/9.1/main


