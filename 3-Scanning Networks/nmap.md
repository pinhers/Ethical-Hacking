Scanning Networks
kali
win11


nmap -sn -PR (Target ip add)
-sn  disables port scan
-PR performs ARP ping scan
-PU performs UDP ping scan
-PE ICMP ECHO ping scan

nmap -sn -PO (target)
ip protocol ping scan this tecnique send different probe packets of different ip protocols  any response indicates that a host is active



