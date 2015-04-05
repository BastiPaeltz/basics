# Accress Control and Rootly Powers

* Objects (files and processes) have **owners**
* **You own** objects you create
* **root** can act as owner of any object
* only root can perform certain admin operations

## Filesystem access controls

* owner can set **permissions** of file
* many people who are part of the same group can be **group owners**
* groups are located in **/etc/group**
* look at ownership with **ls -l**

## Modern access control

* **SELinux** : enables mandatory access control, all permisisions are assigned by admins -> users can **NOT** set control params on objects they own
* **PAM** : authentication technology - **"Does X have permissions to perform operation Y?" "How do I know it is really user X"**
  * programs that want to authenticate a user simply call the PAM system - see security chapter
* **Kerberos** : authentication method, used together with PAM - PAM is the wrapper and Kerberos brings the implementation 
* **Access control lists** : part of filesystem, used by Windows

## root

* dont log in  as root - **no logs*
* use **su** command to log in as someone else
* better call **/usr/bin/su**
* reserved for emergencies, best way: **sudo**
* every sudo is *logged* 
* edit */etc/sudoers* only with **visudo**
