### affichez l'adresse MAC de votre carte WiFi !
'''
PS C:\windows\system32> ipconfig

Configuration IP de Windows

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6 de liaison locale. . . . .: fe80::e8cb:cd94:b7cf:38da%8
   Adresse IPv4. . . . . . . . . . . . . .: 10.33.78.147
   Masque de sous-réseau. . . . . . . . . : 255.255.240.0
   Passerelle par défaut. . . . . . . . . : 10.33.79.254
'''

### Affichez votre table ARP
'''
PS C:\windows\system32> arp -a

Interface : 10.33.78.147 --- 0x8
  Adresse Internet      Adresse physique      Type
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
  10.33.79.255          ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  239.255.255.253       01-00-5e-7f-ff-fd     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

Interface : 192.168.56.1 --- 0xa
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  239.255.255.253       01-00-5e-7f-ff-fd     statique
'''

### Déterminez l'adresse MAC de la passerelle du réseau de l'école
'''
PS C:\windows\system32> arp -a

Interface : 10.33.78.147 --- 0x8
  Adresse Internet      Adresse physique      Type
  10.33.79.254          7c-5a-1c-d3-d8-76     dynamique
'''

### Supprimez la ligne qui concerne la passerelle
'''
PS C:\windows\system32> arp -d 10.33.79.254
'''

### Prouvez que vous avez supprimé la ligne dans la table ARP
'''
PS C:\windows\system32> arp -a

Interface : 192.168.56.1 --- 0xa
  Adresse Internet      Adresse physique      Type
  192.168.56.255        ff-ff-ff-ff-ff-ff     statique
  224.0.0.2             01-00-5e-00-00-02     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  230.0.0.1             01-00-5e-00-00-01     statique
  239.242.6.7           01-00-5e-72-06-07     statique
  239.255.132.178       01-00-5e-7f-84-b2     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  239.255.255.253       01-00-5e-7f-ff-fd     statique
'''

### determiner pour la carte réseau impliquée dans le partage de connexion
'''
PS C:\windows\system32> arp -a

Interface : 172.20.10.10 --- 0x8
  Adresse Internet      Adresse physique      Type
  172.20.10.1           fe-aa-81-5d-f1-64     dynamique
  172.20.10.15          ff-ff-ff-ff-ff-ff     statique
  224.0.0.22            01-00-5e-00-00-16     statique
  224.0.0.251           01-00-5e-00-00-fb     statique
  224.0.0.252           01-00-5e-00-00-fc     statique
  239.255.255.250       01-00-5e-7f-ff-fa     statique
  255.255.255.255       ff-ff-ff-ff-ff-ff     statique

### prouvez que vous avez bien changé d'IP
'''
PS C:\windows\system32> ipconfig

Configuration IP de Windows

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6. . . . . . . . . . . . . .: 2a01:cb1a:34:4c89:5068:c933:d922:731f
   Adresse IPv6 temporaire . . . . . . . .: 2a01:cb1a:34:4c89:cd1d:abde:8353:f25
   Adresse IPv6 de liaison locale. . . . .: fe80::e8cb:cd94:b7cf:38da%8
   Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.10 ### <-- a la place de 172.20.10.9
   Masque de sous-réseau. . . . . . . . . : 255.255.255.240
   Passerelle par défaut. . . . . . . . . : fe80::fcaa:81ff:fe5d:f164%8
                                       172.20.10.1
'''
### Pingz !
'''
PS C:\windows\system32> ping ynov.com

Envoi d’une requête 'ping' sur ynov.com [2606:4700:20::681a:ae9] avec 32 octets de données :
Réponse de 2606:4700:20::681a:ae9 : temps=41 ms
Réponse de 2606:4700:20::681a:ae9 : temps=70 ms
Réponse de 2606:4700:20::681a:ae9 : temps=53 ms
Réponse de 2606:4700:20::681a:ae9 : temps=59 ms

Statistiques Ping pour 2606:4700:20::681a:ae9:
    Paquets : envoyés = 4, reçus = 4, perdus = 0 (perte 0%),
Durée approximative des boucles en millisecondes :
    Minimum = 41ms, Maximum = 70ms, Moyenne = 55ms
''' 













































### vérifiez avec une commande ping que vous avez bien un accès internet
'''
PS C:\windows\system32> ipconfig

Configuration IP de Windows

Carte réseau sans fil Wi-Fi :

   Suffixe DNS propre à la connexion. . . :
   Adresse IPv6. . . . . . . . . . . . . .: 2a01:cb1a:34:4c89:5068:c933:d922:731f
   Adresse IPv6 temporaire . . . . . . . .: 2a01:cb1a:34:4c89:cd1d:abde:8353:f25
   Adresse IPv6 de liaison locale. . . . .: fe80::e8cb:cd94:b7cf:38da%8
   Adresse IPv4. . . . . . . . . . . . . .: 172.20.10.10
   Masque de sous-réseau. . . . . . . . . : 255.255.255.240
   Passerelle par défaut. . . . . . . . . : fe80::fcaa:81ff:fe5d:f164%8
                                       172.20.10.1
'''
