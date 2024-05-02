# La couche d'accès 
Elle permet aux utilisateurs finaux d'accéder au réseau. Deux commutateurs d'accès sont situés à l'intérieur de la couche d'accès. Les commutateurs d'accès OpenSwitch-Acc-I et OpenSwitch-Acc-II sont des appliances OpenSwitch Qemu installées sur des disques VMware VMDK.

![access](https://github.com/bfaycal197/Enterprise-Network-on-GNS3/assets/91549637/3eeafae4-5914-40d4-ad27-de30672f4652)

## Explication du mode de fonctionnement
Les ports Ethernet 3 a et 4 des deux commutateurs sont configurés comme ports d'accès et connectent PC1 et PC4 au réseau du campus. Les ports Ethernet 1 et Ethernet 2 sont des liaisons montantes qui relient les commutateurs d'accès aux commutateurs de distribution. Ils sont configurés comme des ports trunk, transportant le trafic de plusieurs VLAN. Grâce à la connexion redondante de la liaison montante, les commutateurs d'accès restent connectés à la couche supérieure, même en cas de défaillance de l'un des commutateurs de distribution.

Les ordinateurs des utilisateurs finaux sont affectés aux VLAN 10, 20, 30 et 40. Grâce à la segmentation en VLAN, le trafic des utilisateurs est envoyé à la couche de distribution sans être réparti sur les autres commutateurs d'accès du campus. Le PC4 est connecté au port Ethernet 4 qui est assigné au VLAN de gestion 40. La gestion des commutateurs d'accès est assurée par la connexion du port de gestion Ethernet0 au port Ethernet6 du commutateur de distribution concerné. Les deux ports sont configurés comme des ports routés (couche 3) et des adresses IP du sous-réseau avec un masque /30 leur ont été attribuées.

La Switch Virtual Onterface (SVI) créée sur les deux commutateurs d'accès permet à ces derniers de synchroniser leur heure avec le serveur NTP fonctionnant sur l'appliance Server1 172.16.50.1 dans le centre de données (DC). Les commutateurs envoient également des journaux au serveur syslog-ng installé sur la même appliance.
