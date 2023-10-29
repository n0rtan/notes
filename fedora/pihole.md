# Fedora
### Install problem
```
The problem occured because /etc/init.d was a directory instead of a softlink to /etc/rc.d/init.d/. To fix it, simply do
```
* `mv /etc/init.d/* /etc/rc.d/init.d/`
* `rm /etc/init.d -r`
* `ln -s /etc/rc.d/init.d/ /etc/init.d`


# Links
* [Error unpacking rpm package chkconfig](https://samuel.dalesjo.net/2018/04/21/error-unpacking-rpm-package-chkconfig/)







