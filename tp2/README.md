### infos liées à la carte réseau ethernet
'''
ahang@DemoBB:~$ ip addr show enp0s8
3: enp0s8: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 1500 qdisc fq_codel state UP group default qlen 1000
    link/ether 08:00:27:a8:ae:17 brd ff:ff:ff:ff:ff:ff
    inet 192.168.56.105/24 brd 192.168.56.255 scope global dynamic enp0s8
       valid_lft 500sec preferred_lft 500sec
    inet6 fe80::a00:27ff:fea8:ae17/64 scope link
       valid_lft forever preferred_lft forever
'''

### je met ma vm en serveur 
'''
ahang@DemoBB:~$ nc -lvp 9999
listening on [any] 9999 ...
'''

### voyons si cela fonctione et que j'ai un port qui écoute 
'''
ahang@DemoBB:~$ sudo ss -npt
State   Recv-Q   Send-Q       Local Address:Port       Peer Address:Port    Process
ESTAB   0        0           192.168.56.105:22         192.168.56.1:50087    users:(("sshd",pid=2684,fd=4),("sshd",pid=2654,fd=4))
ESTAB   0        0           192.168.56.105:22         192.168.56.1:50298    users:(("sshd",pid=3415,fd=4),("sshd",pid=3395,fd=4))
'''

### le client vient se connecter au port en écoute puis envoie quelques messages
'''
PS C:\Users\ahang\Downloads\netcat-win32-1.11\netcat-1.11> .\nc.exe 192.168.56.105 9999
saluuuuuut
je m'appelle william
j'adore elden ring!!!
'''

### le serveur en listening arrive à les recevoirs !!!
'''
ahang@DemoBB:~$ nc -lvp 9999
listening on [any] 9999 ...
192.168.56.1: inverse host lookup failed: Unknown host
connect to [192.168.56.105] from (UNKNOWN) [192.168.56.1] 50366
saluuuuuut
je m'appelle william
j'adore elden ring!!!
'''

### et inversement le serveur envoie ses messages et le client les reçoit
'''
ahang@DemoBB:~$ nc -lvp 9999
listening on [any] 9999 ...
192.168.56.1: inverse host lookup failed: Unknown host
connect to [192.168.56.105] from (UNKNOWN) [192.168.56.1] 50366
saluuuuuut
je m'appelle william
j'adore elden ring!!!
je suis le serveur
j'adore brawlhala
'''
'''
PS C:\Users\ahang\Downloads\netcat-win32-1.11\netcat-1.11> .\nc.exe 192.168.56.105 9999
saluuuuuut
je m'appelle william
j'adore elden ring!!!
je suis le serveur
j'adore brawlhala
'''

### on voit la connexion en cours depuis le serveur 
'''
ahang@DemoBB:~$ ss -npt
State  Recv-Q  Send-Q    Local Address:Port    Peer Address:Port   Process
ESTAB  0       52       192.168.56.105:22      192.168.56.1:50087
ESTAB  0       0        192.168.56.105:22      192.168.56.1:50298
ESTAB  0       0        192.168.56.105:9999    192.168.56.1:50366   users:(("nc",pid=3460,fd=4))
'''
### on la voit aussi depuis le client 
'''
PS C:\windows\system32> netstat -a -n -b

>   TCP    192.168.56.1:50366     192.168.56.105:9999    ESTABLISHED
   [nc.exe]
   '''

   ### je fais l'inverse avec mon windows et je discute avec mon client 
   ''' 
   PS C:\Users\ahang\Downloads\netcat-win32-1.11\netcat-1.11> ./nc64.exe -l -p 9999
saluuuuuty
je suis la
'''
# on regarde la connexion depuis les 2 port client et serveur 
# serveur 

'''
ahang@DemoBB:~$ ss -npt
State   Recv-Q   Send-Q      Local Address:Port        Peer Address:Port    Process
ESTAB   0        0          192.168.56.105:33416       192.168.56.1:9999     users:(("nc",pid=3553,fd=3))
ESTAB   0        52         192.168.56.105:22          192.168.56.1:50087

ESTAB   0        0          192.168.56.105:22          192.168.56.1:50298
'''
