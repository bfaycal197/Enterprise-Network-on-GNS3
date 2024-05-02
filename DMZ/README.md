# DMZ
Notre DMZ se compose de trois appareils - ASAv-DMZ-I, un commutateur multiniveau vIOS-DMZ-I et Serv-DMZ-I. Tous les appareils de la DMZ sont exécutés par l'hyperviseur Qemu.

![Sans titre](https://github.com/bfaycal197/Enterprise-Network-on-GNS3/assets/91549637/55b4f911-fe97-4286-9d88-d5366ff88963)

## les appareils de la DMZ et leur adressage
Le serveur Serv-DMZ-I fournit des services DNS, NTP, Syslog pour les appareils de la DMZ et un service web public pour tous les hôtes sur Internet. Tous les appareils situés dans la DMZ ont leurs adresses IP attribuées à partir du sous-réseau 195.1.1.128/25. 
Le sous-réseau 195.1.1.128/27 est ensuite divisé avec un masque /30, créant 8 sous-réseaux adaptés à la configuration des liaisons point à point. Les serveurs situés dans la DMZ sont affectés à différents VLAN. Actuellement, seul le serveur Serv-DMZ-I est déployé dans la DMZ et configuré avec les adresses IP 195.1.1.161/29. Le serveur est affecté au VLAN10 sur le commutateur vIOS-DMZ-I. Le sous-réseau réservé aux appareils dans le VLAN10 est 195.1.1.160/29 avec l'adresse IP de passerelle par défaut 196.1.1.166.
