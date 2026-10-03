# Raspberry Pi — Fiche Live

## 1. Qu'est-ce que c'est ?

Un **Raspberry Pi** est un petit ordinateur monocarte. Il peut faire fonctionner Linux, installer des logiciels et exécuter des services réseau.

Analogie : **un petit PC réduit à l'essentiel**.

Point important : **un Raspberry Pi n'est pas un outil de hacking en lui-même**.

## 2. Pourquoi est-il intéressant en cybersécurité ?

On peut l'utiliser comme :

- serveur de laboratoire ;
- sonde de monitoring ;
- honeypot ;
- serveur DNS / DHCP ;
- VPN ;
- firewall ;
- reverse proxy ;
- bastion ;
- plateforme Docker ;
- IDS/IPS ;
- collecteur de logs ;
- plateforme IoT ;
- plateforme d'automatisation.

## 3. Le vrai sujet : le rôle de la machine

**Matériel → système d'exploitation → logiciel → configuration → position réseau → rôle**

C'est cette chaîne qui explique ce que le Raspberry Pi peut réellement faire.

Un Raspberry Pi placé comme serveur n'a pas le même rôle qu'un Raspberry Pi utilisé comme sonde réseau, passerelle, honeypot ou plateforme IoT.

## 4. Mythes et rumeurs

### « Un Raspberry Pi est un appareil de hacking »

**Faux.** C'est avant tout un ordinateur.

### « Un Raspberry Pi peut pirater n'importe quel Wi-Fi »

**Faux.** Les possibilités dépendent du matériel, des logiciels, des pilotes, de la configuration et des mécanismes de sécurité utilisés.

### « On peut brancher un Raspberry Pi sur un réseau et tout voir »

**Faux.** Ce qu'une machine peut observer dépend notamment de sa position dans le réseau, de sa configuration, du chiffrement et de l'architecture.

### « Un Raspberry Pi est trop faible pour la cybersécurité »

**Faux.** Il est très utile pour les petits services, les laboratoires, l'IoT, le monitoring et l'apprentissage. Ses ressources restent cependant limitées.

## 5. Pendant la démonstration

Chercher à identifier :

1. Quel matériel est utilisé ?
2. Quel système d'exploitation tourne dessus ?
3. Quel logiciel ou service lui donne sa capacité ?
4. Quelle interface est utilisée ?
5. À quel endroit du réseau est-il connecté ?
6. Quelles données peut-il réellement observer ou traiter ?
7. Quelle condition rend la démonstration possible ?
8. Quelle est sa limite ?
9. Comment un défenseur pourrait-il détecter ou bloquer cette activité ?

## 6. Quelques rôles importants

- **Honeypot** → système leurre pour observer des comportements suspects ;
- **IDS** → détection d'activités suspectes ;
- **IPS** → détection et blocage de certains flux ;
- **DNS** → résolution de noms ;
- **VPN** → tunnel réseau protégé ;
- **Firewall** → filtrage de flux ;
- **Reverse proxy** → contrôle devant une application ;
- **Bastion** → point d'accès contrôlé ;
- **Monitoring** → observation de l'état d'une infrastructure ;
- **IoT** → interaction avec des objets et capteurs.

## 7. Risques à surveiller

Comme tout ordinateur :

- mot de passe faible ;
- logiciel non mis à jour ;
- SSH exposé ;
- service inutile exposé ;
- ports inutilement ouverts ;
- mauvaise configuration ;
- privilèges excessifs ;
- secrets mal stockés ;
- accès physique non protégé.

Un **port réseau** peut être comparé à une porte. Une porte ouverte n'est pas forcément dangereuse, mais il faut savoir pourquoi elle est ouverte et qui peut l'utiliser.

## 8. Comment le sécuriser ?

- identifiants solides ;
- clés SSH lorsque possible ;
- mises à jour ;
- services minimaux ;
- moindre privilège ;
- contrôle des accès ;
- pare-feu lorsque nécessaire ;
- limitation de l'exposition Internet ;
- surveillance des connexions et logs ;
- protection physique.

## 9. Documentation technique complète

Pour comprendre les usages et techniques de cybersécurité autour du Raspberry Pi :

**[Raspberry Pi — Usages cybersécurité et techniques](./RASPBERRY-PI-SECURITY-USES.md)**

La fiche détaille notamment Wireshark, tcpdump, Nmap, DNS, DHCP, VPN, WireGuard, firewall, reverse proxy, Docker, Prometheus, Grafana, SIEM, IDS/IPS, Suricata, Zeek, MQTT, IoT, GPIO, RFID/NFC, Bluetooth/BLE, hardening, segmentation réseau et cyber-range.

## 10. Questions à poser

1. Quel rôle joue le Raspberry Pi ?
> **Réponse :** Son rôle dépend de sa configuration : il peut servir de sonde, serveur, honeypot, passerelle, VPN, firewall, plateforme IoT ou outil de laboratoire.
2. Quel logiciel lui donne cette capacité ?
> **Réponse :** C'est principalement le système d'exploitation et les logiciels ou services installés qui donnent au Raspberry Pi sa fonction de cybersécurité.
3. Est-ce le matériel ou le logiciel qui est important ici ?
> **Réponse :** Les deux comptent, mais dans la plupart des usages la capacité observée vient surtout du logiciel, de la configuration et de la position réseau.
4. Quelle position occupe-t-il dans le réseau ?
> **Réponse :** Il peut être placé comme poste, serveur, passerelle, sonde, bastion ou équipement intermédiaire, et cette position détermine ce qu'il peut observer ou contrôler.
5. Quelles données peut-il réellement observer ?
> **Réponse :** Il ne peut observer que les données accessibles depuis sa position réseau, ses interfaces, ses droits et les mécanismes de chiffrement utilisés.
6. Quelle condition rend la démonstration possible ?
> **Réponse :** La démonstration dépend généralement d'une combinaison de matériel compatible, logiciel adapté, configuration correcte, accès réseau et environnement autorisé.
7. Comment sécuriser cette machine ?
> **Réponse :** Il faut notamment limiter les services exposés, appliquer les mises à jour, utiliser des identifiants solides, réduire les privilèges et surveiller les accès.
8. Quelle est la limite de cette démonstration ?
> **Réponse :** La limite dépend surtout des ressources du Pi, du matériel utilisé, de sa position réseau et de ce que les logiciels lui permettent réellement de faire.
9. **Qu'est-ce qui a réellement été démontré ?**
> **Réponse :** On a démontré une capacité précise du Raspberry Pi dans une configuration donnée, et non une capacité universelle de hacking.

## Phrase prête à dire

> « Le Raspberry Pi n'est pas magique : c'est un petit ordinateur. Sa capacité en cybersécurité vient surtout des logiciels qu'on installe, de sa configuration et du rôle qu'on lui donne dans le réseau. »

**Lab : uniquement sur des systèmes autorisés et isolés.**


---

## Sources vérifiées

Voir **[Raspberry Pi — Sources vérifiées](./SOURCES.md)** pour les références primaires, institutionnelles et techniques utilisées dans cette fiche.


---

## Sources vérifiées

Voir **[Raspberry Pi — Sources vérifiées](./SOURCES.md)** pour les références utilisées dans cette fiche.
