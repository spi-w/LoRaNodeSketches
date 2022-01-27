# LoRaNodeSketches


## Lowcost directory

Contient des programmes basés sur le travail de CongducPham (LowCostLoRaGw).
[https://github.com/CongducPham/LowCostLoRaGw](URL 'LowCostLoRaGw framework')

Ce sont des programmes pour single-channel gateways.
Cette implémentation permet une première approche avec LoRaWan. Elle permet de comprendre le déroulement globale des opérations d'un noeud. Bien que les packets peuvent être au format Lorawan et être réceptionné par une gateway Lorawan, ce n'est pas du "pur" Lorawan, car la couche MAC n'est pas implémenté/géré.
L'ensemble des opérations réalisé lors d'un "cycle" (boucle loop()) correspond à l'implémentation d'un noeud de classe A.

##Lmic directory

Contient des programmes basé sur la librairie arduino-lmic de MCCI-catena.
[https://github.com/mcci-catena/arduino-lmic] (URL 'arduino-lmic')

Contrairement à l'implémentation précédente, ici la couche MAC est implémenté. Il peut s'agir de noeuds de classe A ou B, de plus l'OTAA est possible. Cette librarie correspond aux spécifications du cahier des charges LoRaWan.

Mon travail précédent avec LowCostLoRaGw sera en parti repris/adapté (implémentation des sensors sous formes d'objets et gestion des interruptions).
CongducPham propose également une manière d'utiliser cette librarie en single-channel, ainsi qu'une manière d'ajouter le mode LowPower (absent de lmic, qui est absolument essentiel à implémenter). Ce travail sera donc également repris.
