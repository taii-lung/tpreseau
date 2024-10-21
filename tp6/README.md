### TP6 : Des bo services dans des bo LANs

## Prouver que une machine du LAN2 peut joindre internet 
'''
[wonana@web ~]$ ping amazon.com
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
'''
[wonana@dhcp ~]$ ping ynov.com
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
'''
[wonana@dhcp ~]$ ping 10.6.2.11
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