# La couche de distribution
La couche de distribution se compose de deux commutateurs multicouches vEOS-DIS-I et vEOS-DIS-II. Les commutateurs sont des appliances Arista vEOS version 4.17.2F Qemu installées sur des disques VMware.

![couche D](https://github.com/bfaycal197/Enterprise-Network-on-GNS3/assets/91549637/7368a0cf-780e-43ad-b856-7a013077f11d)

## Explication du mode de fonctionnement
Les commutateurs de distribution acheminent le trafic entre les VLAN des utilisateurs finaux et connectent le réseau de couche inférieure à une couche centrale. Les interfaces de la couche 3 (routées) connectent les deux commutateurs de distribution entre eux et avec les commutateurs centraux.  Les interfaces vers la couche d'accès sont de couche 2 (switchports). Le protocole de routage OSPF est exécuté sur les commutateurs de distribution, de sorte qu'il n'y a qu'une connectivité de couche 3 entre la distribution et la couche centrale.
