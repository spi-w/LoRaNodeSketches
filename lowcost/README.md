# Programmes 'lowcost'

## 'temp', 'Simple_temp', 'Generic_DHT'

Programmes d'origines de CongducPham, permettant une première prise en main. 'temp' permettent le cryptage en AES.

## 'Generic_DHT11'

Modification du programme 'Generic_DHT', pour fonctionner avec un capteur DHT11 (au lieu d'un DHT22).

## 'Geniric_DHT11_WITH_AES'

Fusion de 'Generic_DHT11' et 'temp', pour implémenter à la fois le cryptage en AES et la gestion des capteurs sous forme d'une classe d'objet.
Tout les programmes suivants sont dérivés de celui-ci.

## 'MH_IR'

Tentative d'implémentation d'un noeud avec un capteur MH (détection de mouvement en IR), en utilisant un système d'interruption.

En l'état, ne fonctionne pas, ou résultat innatendu (sera probablement supprimé à l'avenir, conservé pour l'instant car il y a du travail sur la manière d'utiliser le capteur MH).
Pour utiliser un système d'interruption, plutôt se baser 'HCSR04_withInt'.

## 'HCSR04'

Implémentation d'un noeud avec un capteur de distance ultrason, le HCSR04. Fonctionnel.

## 'HCSR04_withInt'

Basé sur le programme précédent, en implémentant un système d'interruption, pour envoyer des uplinks en cas d'information reçu sur le pin 2 ou 3. Fonctionnel.
Recommande de se baser sur ce programme pour toute futur implémentation.

### Interruptions

Quel est l'intérêt des interruptions ? Une interruption permet de lancer une "routine" (entendre fonction) prioritaire, en cas de déclenchement (voir [arduinoInt] pour une explication plus complète sur le principe).
L'utilisation des interruption parait pertinent pour les noeuds Lora : dans le cas où un noeud a pour fonction d'attendre un stimuli d'un capteur (et pas de faire un relevé 'analogique'), s'il n'y avait pas les interruptions, soit il faudrait vérifier en permanence le capteur, ce qui serait très énergivore (pas souhaitable pour un capteur autonome sur batterie), soit il faudrait programmer des relevés à certains moment uniquement, au prix d'un manque de réactivité et de risque de manquer l'information. Les interruptions permettent le parfait compromis : l'arduino peut être en mode LowPower, tout en étant capable d'envoyer un uplink dès qu'il y aura un stimuli sur un pin.

[arduinoInt]: https://www.arduino.cc/reference/en/language/functions/external-interrupts/attachinterrupt/ "cette page"
