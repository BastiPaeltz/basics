# Adding new users

* use **adduser** or **useradd**

## /etc/passwd and /etc/shadow

* login names stored in passwd
* passwords in shadow
* login names must be **unique**
* login name should always refer to same person
* edit with **vipw**

## UID and GID

* user ID
* root has UID 0
* recommmended UIDs start at 500 or higher
* GID 0 is group root
* groups defined in **/etc/groups**

## adduser

* configured in **/etc/adduser.conf**

## removing users

* use **deluser**
* configured in **/etc/deluser.conf**

## disabling logins

* use **usermod -L *user*** (and -U) -> lock and unlock


