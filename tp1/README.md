###
# Adresses IP de ta machine

"PS C:\Users\ahang> ipconfig /all

Carte réseau sans fil Wi-Fi :


   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : Realtek RTL8821CE 802.11ac PCIe Adapter
   Adresse physique . . . . . . . . . . . : 94-BB-43-D9-E1-25
   DHCP activé. . . . . . . . . . . . . . : Oui
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::e8cb:cd94:b7cf:38da%9(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.78.147(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Bail obtenu. . . . . . . . . . . . . . : vendredi 27 septembre 2024 14:08:52
   Bail expirant. . . . . . . . . . . . . : samedi 28 septembre 2024 14:04:57
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
   Serveur DHCP . . . . . . . . . . . . . : 10.33.79.254
   IAID DHCPv6 . . . . . . . . . . . : 127187779
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-1D-92-81-9C-EB-E8-F2-06-04
   Serveurs DNS. . .  . . . . . . . . . . : 8.8.8.8"

# Si t'as un accès internet normal, d'autres infos sont forcément dispos

"PS C:\Users\ahang> ipconfig /all

Carte Ethernet Ethernet 2 :

   Suffixe DNS propre à la connexion. . . :
   Description. . . . . . . . . . . . . . : VirtualBox Host-Only Ethernet Adapter
   Adresse physique . . . . . . . . . . . : 0A-00-27-00-00-0B
   DHCP activé. . . . . . . . . . . . . . : Non
   Configuration automatique activée. . . : Oui
   Adresse IPv6 de liaison locale. . . . .: fe80::a39f:f190:2c24:2%11(préféré)
   Adresse IPv4. . . . . . . . . . . . . .: 192.168.56.1(préféré)
   Masque de sous-réseau. . . . . . . . . : 255.255.255.0
   Passerelle par défaut. . . . . . . . . :
   IAID DHCPv6 . . . . . . . . . . . : 654966823
   DUID de client DHCPv6. . . . . . . . : 00-01-00-01-2E-1D-92-81-9C-EB-E8-F2-06-04
   NetBIOS sur Tcpip. . . . . . . . . . . : Activé"

### II. Utiliser le réseau

# ping vers moi même
"PS C:\Users\ahang> ping 10.33.78.147

Envoi d’une requête 'Ping'  10.33.78.147 avec 32 octets de données :
Réponse de 10.33.78.147 : octets=32 temps<1ms TTL=128
Réponse de 10.33.78.147 : octets=32 temps<1ms TTL=128
Réponse de 10.33.78.147 : octets=32 temps<1ms TTL=128
Réponse de 10.33.78.147 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 10.33.78.147:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms"

# ping vers le loopback
"PS C:\Users\ahang> ping 127.0.0.1

Envoi d’une requête 'Ping'  127.0.0.1 avec 32 octets de données :
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128
Réponse de 127.0.0.1 : octets=32 temps<1ms TTL=128

Statistiques Ping pour 127.0.0.1:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 0ms, Maximum = 0ms, Moyenne = 0ms" 

# ping un pote
"ping un pote :
    "PS C:\Users\ahang> ping 10.33.66.78

Envoi d’une requête 'Ping'  10.33.66.78 avec 32 octets de données :
Réponse de 10.33.66.78 : octets=32 temps=115 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=19 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=32 ms TTL=64
Réponse de 10.33.66.78 : octets=32 temps=47 ms TTL=64

Statistiques Ping pour 10.33.66.78:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 19ms, Maximum = 115ms, Moyenne = 53ms"

# On continue avec ping. Envoie un ping vers un site internet

"PS C:\Users\ahang> ping www.amazon.com

Envoi d’une requête 'ping' sur d3ag4hukkh62yn.cloudfront.net [205.251.207.238] avec 32 octets de données :
Réponse de 205.251.207.238 : octets=32 temps=13 ms TTL=248
Réponse de 205.251.207.238 : octets=32 temps=13 ms TTL=248
Réponse de 205.251.207.238 : octets=32 temps=13 ms TTL=248
Réponse de 205.251.207.238 : octets=32 temps=13 ms TTL=248

Statistiques Ping pour 205.251.207.238:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 13ms, Maximum = 13ms, Moyenne = 13ms"

adresse ip des domaines : 
----"PS C:\Users\ahang> nslookup www.thinkerview.com
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.thinkerview.com
Addresses:  2a06:98c1:3120::7
          2a06:98c1:3121::7
          188.114.97.7
          188.114.96.7"

----"PS C:\Users\ahang> nslookup www.wikileaks.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    wikileaks.org
Addresses:  80.81.248.21
          51.159.197.136
Aliases:  www.wikileaks.org"

----"PS C:\Users\ahang> nslookup www.torproject.org
Serveur :   dns.google
Address:  8.8.8.8

Réponse ne faisant pas autorité :
Nom :    www.torproject.org
Addresses:  2a01:4f8:fff0:4f:266:37ff:fe2c:5d19
          2a01:4f8:fff0:4f:266:37ff:feae:3bbc
          2620:7:6002:0:466:39ff:fe32:e3dd
          2620:7:6002:0:466:39ff:fe7f:1826
          2a01:4f9:c010:19eb::1
          204.8.99.146
          116.202.120.166
          116.202.120.165
          95.216.163.36
          204.8.99.144  "

### III. Sniffer le réseau
les dossiers sont dans github !!!

### IV. Network scanning et adresses IP
#  Effectue un scan du réseau auquel tu es connecté
"PS C:\Users\ahang> nmap.exe -sn -PR 10.33.64.0/20
Starting Nmap 7.95 ( https://nmap.org ) at 2024-09-27 17:37 Paris, Madrid (heure dÆÚtÚ)
Stats: 0:00:03 elapsed; 0 hosts completed (0 up), 4095 undergoing ARP Ping Scan
ARP Ping Scan Timing: About 1.71% done; ETC: 17:39 (0:01:55 remaining)"

# Changer d'adresse IP
"PS C:\Users\ahang> ipconfig

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::5cd2:c981:10b1:5928%19
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.78.249
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
"