


### 🌞 Lister les ports en écoute sur la machine
'''[wonana@localhost ~]$ sudo ss -ltpn
[sudo] password for wonana:
State       Recv-Q      Send-Q           Local Address:Port            Peer Address:Port      Process
LISTEN      0           511                    0.0.0.0:80                   0.0.0.0:*          users:(("nginx",pid=1612,fd=6),("nginx",pid=1611,fd=6))
LISTEN      0           128                    0.0.0.0:22                   0.0.0.0:*          users:(("sshd",pid=689,fd=3))
LISTEN      0           511                       [::]:80                      [::]:*          users:(("nginx",pid=1612,fd=7),("nginx",pid=1611,fd=7))
LISTEN      0           128                       [::]:22                      [::]:*          users:(("sshd",pid=689,fd=4))
'''

### 🌞 Ouvrir le port dans le firewall de la machine
'''[wonana@localhost ~]$ sudo firewall-cmd --permanent --add-port=80/tcp
[sudo] password for wonana:
Warning: ALREADY_ENABLED: 80:tcp
success
'''
# 🌞 Vérifier que ça a pris effet
### faites un ping vers sitedefou.tp7.b1
'''tai_lung@serveurw:/$ ping sitedefou.tp7.b1
PING sitedefou.tp7.b1 (10.7.1.11) 56(84) bytes of data.
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=1 ttl=64 time=1.76 ms
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=2 ttl=64 time=2.27 ms
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=3 ttl=64 time=2.43 ms
64 bytes from sitedefou.tp7.b1 (10.7.1.11): icmp_seq=4 ttl=64 time=2.21 ms
^C
--- sitedefou.tp7.b1 ping statistics ---
4 packets transmitted, 4 received, 0% packet loss, time 3002ms
rtt min/avg/max/mdev = 1.756/2.167/2.433/0.250 ms
'''

### visitez http://sitedefou.tp7.b1
'''tai_lung@serveurw:/$ curl    sitedefou.tp7.b1
<html>
<head><title>403 Forbidden</title></head>
<body>
<center><h1>403 Forbidden</h1></center>
<hr><center>nginx/1.20.1</center>
</body>
</html>
'''