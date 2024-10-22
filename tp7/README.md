


### Lister les ports en écoute sur la machine
'''[wonana@localhost ~]$ sudo ss -ltpn
[sudo] password for wonana:
State       Recv-Q      Send-Q           Local Address:Port            Peer Address:Port      Process
LISTEN      0           511                    0.0.0.0:80                   0.0.0.0:*          users:(("nginx",pid=1612,fd=6),("nginx",pid=1611,fd=6))
LISTEN      0           128                    0.0.0.0:22                   0.0.0.0:*          users:(("sshd",pid=689,fd=3))
LISTEN      0           511                       [::]:80                      [::]:*          users:(("nginx",pid=1612,fd=7),("nginx",pid=1611,fd=7))
LISTEN      0           128                       [::]:22                      [::]:*          users:(("sshd",pid=689,fd=4))
'''