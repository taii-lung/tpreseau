# TP6 : Des bo services dans des bo LANs

## Prouver que une machine du LAN2 peut joindre internet 
'''[wonana@web ~]$ ping amazon.com
PING amazon.com (54.239.28.85) 56(84) bytes of data.
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=1 ttl=239 time=91.5 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=2 ttl=239 time=92.6 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=3 ttl=239 time=91.8 ms
64 bytes from 54.239.28.85 (54.239.28.85): icmp_seq=4 ttl=239 time=95.7 ms
^C
--- amazon.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3010ms
rtt min/avg/max/mdev = 91.524/92.928/95.737/1.669 ms
'''
## Prouver que une machine du LAN1 peut joindre internet 
'''[wonana@dhcp ~]$ ping ynov.com
PING ynov.com (104.26.11.233) 56(84) bytes of data.
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=1 ttl=53 time=21.5 ms
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=2 ttl=53 time=20.4 ms
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=3 ttl=53 time=22.6 ms
64 bytes from 104.26.11.233 (104.26.11.233): icmp_seq=4 ttl=53 time=21.4 ms
^C
--- ynov.com ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3008ms
rtt min/avg/max/mdev = 20.350/21.454/22.592/0.794 ms
'''

## Prouver que une machine du LAN1 peut joindre une machine du LAN2
'''[wonana@dhcp ~]$ ping 10.6.2.11
PING 10.6.2.11 (10.6.2.11) 56(84) bytes of data.
64 bytes from 10.6.2.11: icmp_seq=1 ttl=63 time=2.14 ms
64 bytes from 10.6.2.11: icmp_seq=2 ttl=63 time=2.38 ms
64 bytes from 10.6.2.11: icmp_seq=3 ttl=63 time=2.93 ms
64 bytes from 10.6.2.11: icmp_seq=4 ttl=63 time=2.66 ms
^C
--- 10.6.2.11 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3006ms
rtt min/avg/max/mdev = 2.141/2.527/2.933/0.296 ms
'''

# II. LAN clients
### 2. Client
```
tai_lung@serverw-ubuntu:~$ ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN group default qlen 1000
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host noprefixroute
       valid_lft forever preferred_lft forever
2: enp0s3: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:6a:3f:c3 brd ff:ff:ff:ff:ff:ff
    inet 10.6.1.37/24 brd 10.6.1.255 scope global dynamic noprefixroute enp0s3
       valid_lft 42771sec preferred_lft 42771sec
    inet6 fe80::a00:27ff:fe6a:3fc3/64 scope link
       valid_lft forever preferred_lft forever
```
```
tai_lung@serverw-ubuntu:~$ ping google.com
PING google.com (142.251.37.174) 56(84) bytes of data.
64 bytes from mrs09s14-in-f14.1e100.net (142.251.37.174): icmp_seq=1 ttl=111 time=19.6 ms
64 bytes from mrs09s14-in-f14.1e100.net (142.251.37.174): icmp_seq=2 ttl=111 time=15.9 ms
^C
--- google.com ping statistics ---
2 packets transmitted, 2 received, 0% packet loss, time 1000ms
rtt min/avg/max/mdev = 15.932/17.785/19.638/1.853 ms


tai_lung@serverw-ubuntu:~$ ip route show
default via 10.6.1.254 dev enp0s3 proto dhcp src 10.6.1.37 metric 100
10.6.1.0/24 dev enp0s3 proto kernel scope link src 10.6.1.37 metric 100

tai_lung@serverw-ubuntu:~$ resolvectl
Global
         Protocols: -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
  resolv.conf mode: stub

Link 2 (enp0s3)
    Current Scopes: DNS
         Protocols: +DefaultRoute -LLMNR -mDNS -DNSOverTLS DNSSEC=no/unsupported
Current DNS Server: 1.1.1.1
       DNS Servers: 1.1.1.1
```
# III. LAN serveurzzzz
### 1. Serveur Web
```
[wonana@web ~]$ sudo ss -lnpt | grep 80
LISTEN 0      511          0.0.0.0:80        0.0.0.0:*    users:(("nginx",pid=1485,fd=6),("nginx",pid=1484,fd=6))
LISTEN 0      511             [::]:80           [::]:*    users:(("nginx",pid=1485,fd=7),("nginx",pid=1484,fd=7))
```
Ouvrir le port 80 dans le firewall:
```
[wonana@web ~]$ sudo firewall-cmd --list-ports
80/tcp
```
Problème dans le HTML de la page je ne peux pas voir le début 
ducoup je met la fin.
```
 <footer class="col-sm-12">
      <a href="https://apache.org">Apache&trade;</a> is a registered trademark of <a href="https://apache.org">the Apache Software Foundation</a> in the United States and/or other countries.<br />
      <a href="https://nginx.org">NGINX&trade;</a> is a registered trademark of <a href="https://">F5 Networks, Inc.</a>.
      </footer>

  </body>
</html>
```
### 2. Serveur DNS
```
[wonana@web ~]$ sudo ss -lnpt | grep :53
LISTEN 0      10         127.0.0.1:53        0.0.0.0:*    users:(("named",pid=1550,fd=22))
LISTEN 0      10         10.6.2.12:53        0.0.0.0:*    users:(("named",pid=1550,fd=25))
LISTEN 0      10             [::1]:53           [::]:*    users:(("named",pid=1550,fd=27))

[wonana@web ~]$ sudo firewall-cmd --list-ports

53/tcp 53/udp
```
```
;; ANSWER SECTION:
web.tp6.b1.             86400   IN      A       10.6.2.11
```
J'ai reussi a capturer des paquets DNS avec tcpdump mais pas à transferer le fichier toto sur mon pc depuis ma vm
pour l'ouvir sur Wireshark donc pour l'instant j'ai que ça:
```
wonana@web-ubuntu:~$ sudo tcpdump -w toto.pcap -i enp0s3
[sudo] password for adam:
tcpdump: listening on enp0s3, link-type EN10MB (Ethernet), snapshot length 262144 bytes
tcpdump -w toto.pcap -i enp0s3
^C575 packets captured
577 packets received by filter
0 packets dropped by kernel
```