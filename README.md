enable
configure terminal
interface gigabit/0/0
ip address 192.168.1.1 255.255.255.0
no shutdown
do write
exit

interface serial0/0/0 
ip address 192.168.4.1 255.255.255.0
no shutdown
exit
end
copy running-confing startup-config

------siguente router en este podemos tirar los dos serial de una vez el izquierdo y derecho luego de que lo configuremos todo se configura los pc para comprobar que si funcionan 

ip 192.168.1.2
mascara 255.255.255.0 tipo c
(router)default gateway 192.168.1.1
antes de seguir hacer un ping a cada subred es decir pc0 a pc1 

ahora ripv2 en el router 0
enable
configure terminal
route rip network 192.168.1.0
route rip network 192.168.4.0
version 2
exit, exit
copy running-config startup config

ahora ripv2 en el router 1
enable configure terminal
route rip 
network 192.168.4.0
network 192.168.2.0
network 192.168.5.0
