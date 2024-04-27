# La couche centrale
La couche centrale est constituée des commutateurs vIOS-Core-I et vIOS-Core-II. Il s'agit d'appliances Cisco vIOS-l2 Qemu sur disques qcow2, version 15.2.
La couche centrale est entièrement de niveau 3. Elle est connectée à la couche de distribution inférieure avec des liens P2P L3 configurés avec les adresses IP du sous-réseau 10.0.0.0/24.  Les commutateurs centraux connectent les couches de distribution et d'accès à l'appliance virtuelle de sécurité adaptative de Cisco (ASAv) configurée avec les adresses IP du sous-réseau 172.16.0.0/24.

![Couche C](https://github.com/bfaycal197/Enterprise-Network-on-GNS3/assets/91549637/08264455-0697-4abe-8b0b-8efe11d1f95e)
