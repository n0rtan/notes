# IP Forwarding

* vi /etc/sysctl.conf
```
net.ipv4.ip_forward = 1
```
#### or
* `sysctl -w net.ipv4.ip_forward=1`
#### Vew state
- `sysctl -p`

# Links
* [How to enable IP Forwarding in Linux](https://www.ducea.com/2006/08/01/how-to-enable-ip-forwarding-in-linux/)


