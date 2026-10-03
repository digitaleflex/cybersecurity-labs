# Raspberry Pi — Usages cybersécurité et techniques

> Fiche pédagogique. Les techniques offensives doivent rester dans un laboratoire ou sur des systèmes explicitement autorisés.

## 1. Le modèle mental

Un Raspberry Pi n'est pas « un outil de hacking ». C'est un ordinateur :

**Matériel → système d'exploitation → logiciel → configuration → rôle**

Le même appareil peut devenir serveur, sonde réseau, honeypot, DNS, VPN, firewall, collecteur de logs, plateforme IoT, laboratoire ou serveur Docker.

## 2. Serveur de laboratoire

Il peut héberger un serveur web, une API, une petite base de données, Git, DNS, SSH, Docker ou des outils de monitoring.

**À retenir :** c'est une petite infrastructure informatique réelle, utile pour apprendre.

## 3. Honeypot

Un **honeypot** est un système leurre conçu pour attirer ou observer des comportements suspects.

Analogie : une fausse maison équipée de capteurs pour observer quelqu'un qui tente d'y entrer.

Il sert surtout à la détection, l'observation, la recherche et l'apprentissage. Il ne protège pas directement le serveur principal.

## 4. Honeynet

Une **honeynet** est un ensemble de systèmes leurres organisés.

**Honeypot = un leurre. Honeynet = plusieurs leurres.**

## 5. Network monitoring

Le Raspberry Pi peut devenir une sonde de surveillance réseau et observer trafic, connexions, latence, disponibilité, erreurs et bande passante.

**Limite :** sa visibilité dépend de sa position dans le réseau. Le brancher sur un réseau ne donne pas automatiquement accès à toutes les communications.

## 6. Packet capture

Un **packet** est une unité de données réseau. La capture de paquets consiste à observer certains paquets accessibles à une interface.

Outils connus : **Wireshark** et **tcpdump**.

Le chiffrement peut rendre le contenu illisible même si certaines métadonnées restent observables.

## 7. Wireshark

**Wireshark** est un analyseur de protocoles réseau. Il permet notamment d'étudier TCP, UDP, DNS, HTTP, TLS, DHCP et ARP.

> « Wireshark ne pirate pas le réseau : il analyse les communications auxquelles la machine a accès. »

## 8. tcpdump

**tcpdump** capture et analyse du trafic depuis le terminal.

**Wireshark → analyse graphique approfondie.**

**tcpdump → capture et analyse en ligne de commande.**

## 9. Nmap

**Nmap** est un outil de découverte et d'audit réseau. Il peut aider à identifier des machines accessibles, des ports exposés et certains services.

Il sert principalement à **cartographier une surface réseau autorisée** ; il ne « pirate » pas automatiquement une machine.

## 10. DNS

Le **DNS (Domain Name System)** traduit notamment des noms de domaine en informations permettant de localiser des services.

Un Raspberry Pi peut héberger un service DNS local.

## 11. Pi-hole et filtrage DNS

**Pi-hole** peut utiliser un Raspberry Pi comme serveur de filtrage DNS.

Concept : **client → DNS local → filtrage → Internet**.

Il peut bloquer certaines requêtes vers des domaines présents dans les listes configurées. Avec des sources fiables, le filtrage DNS peut aussi contribuer à réduire certaines communications vers des domaines malveillants.

## 12. DHCP

Le **DHCP** attribue automatiquement des paramètres réseau aux appareils, notamment adresse IP, passerelle et DNS.

Un Raspberry Pi peut jouer ce rôle dans un laboratoire.

## 13. VPN

Un **VPN (Virtual Private Network)** crée une connexion réseau protégée entre des appareils ou réseaux.

Le Raspberry Pi peut servir de point VPN.

**Attention :** un VPN ne signifie pas automatiquement anonymat. Il protège principalement le canal de communication selon sa configuration.

## 14. WireGuard

**WireGuard** est un protocole VPN moderne. Un Raspberry Pi peut servir de serveur ou de passerelle WireGuard.

## 15. Firewall

Un firewall contrôle certains flux réseau.

Sous Linux, on rencontre notamment **nftables**, **iptables** et **UFW** comme interface simplifiée.

Le Raspberry Pi peut servir de petit pare-feu dans un laboratoire ou certains réseaux.

## 16. Reverse proxy

Un **reverse proxy** est une passerelle devant les applications.

Il peut gérer TLS, routage, limites, logs, cache et contrôle d'accès.

Exemples : NGINX, HAProxy, Traefik, Caddy.

## 17. Bastion / Jump Host

Un **bastion host** est une machine contrôlée servant de point d'accès vers une infrastructure interne.

**Administrateur → Bastion → Réseau interne**

Un Raspberry Pi peut jouer ce rôle dans un laboratoire. Il doit alors être fortement sécurisé.

## 18. SSH

**SSH (Secure Shell)** permet d'administrer une machine à distance de manière sécurisée lorsqu'il est correctement configuré.

Mesures : clés SSH, mises à jour, limitation réseau, MFA lorsque disponible, logs et moindre privilège.

## 19. Moindre privilège

Le principe du **moindre privilège** consiste à donner uniquement les droits nécessaires.

Un compte de monitoring ne devrait pas automatiquement avoir les droits administrateur sur toute la machine.

## 20. Docker

Docker permet d'exécuter des applications dans des conteneurs.

Un Raspberry Pi compatible peut héberger plusieurs services isolés logiquement : DNS, monitoring, honeypot, web, etc.

**Conteneur ≠ machine virtuelle :** un conteneur partage le noyau de l'hôte alors qu'une VM virtualise un système complet.

## 21. Prometheus

**Prometheus** collecte des métriques : CPU, RAM, disque, réseau, disponibilité.

Un Raspberry Pi peut servir de plateforme de monitoring légère.

## 22. Grafana

**Grafana** transforme les métriques en tableaux de bord.

Chaîne : **Raspberry Pi → métriques → Prometheus → Grafana → dashboard**.

## 23. Syslog et logs

Les **logs** sont les traces produites par les systèmes : authentifications, connexions, erreurs, événements réseau et applicatifs.

Un Raspberry Pi peut servir de collecteur de logs pour un petit laboratoire.

## 24. SIEM

Un **SIEM (Security Information and Event Management)** centralise et corrèle des événements de sécurité.

Un Raspberry Pi peut servir à expérimenter certaines solutions légères, mais ses ressources sont limitées pour un grand SOC.

## 25. IDS

Un **IDS (Intrusion Detection System)** détecte des comportements potentiellement suspects.

**Trafic → IDS → analyse → alerte**

## 26. IPS

Un **IPS (Intrusion Prevention System)** peut en plus intervenir pour bloquer certains flux.

**IDS → détecte. IPS → détecte + peut bloquer.**

La position du système dans le réseau est donc importante.

## 27. Suricata

**Suricata** est un moteur open source de détection et prévention réseau.

Sur un Raspberry Pi suffisamment puissant, il peut servir à l'apprentissage et à certains petits environnements.

## 28. Zeek

**Zeek** est une plateforme d'analyse réseau produisant des informations structurées sur les communications.

Il est davantage orienté vers l'observation et l'analyse que vers le simple blocage. Ses besoins en ressources doivent être pris en compte.

## 29. IoT Security

Le Raspberry Pi est utile pour comprendre la sécurité IoT.

Exemple : **capteur → Raspberry Pi → MQTT → application**.

On peut étudier authentification, chiffrement, segmentation, firmware, protocoles, logs et contrôle d'accès.

## 30. MQTT

**MQTT** est un protocole de messagerie très utilisé dans l'IoT.

Modèle : **Sensor → Broker → Application**.

Le broker reçoit et distribue les messages. La sécurité dépend notamment de l'authentification, TLS, permissions et segmentation.

## 31. Bluetooth / BLE

Le Raspberry Pi peut participer à des expérimentations Bluetooth et **BLE (Bluetooth Low Energy)**.

On peut étudier découverte, services, caractéristiques, appairage, authentification et chiffrement.

La proximité radio ne signifie pas automatiquement accès au système.

## 32. GPIO

Les **GPIO (General-Purpose Input/Output)** sont des broches permettant d'interagir avec des composants électroniques : capteurs, boutons, LEDs, relais et alarmes.

Cela relie cybersécurité et sécurité physique.

## 33. RFID / NFC

Avec le matériel approprié, un Raspberry Pi peut participer à des projets RFID/NFC.

On peut étudier identification, badges, lecteurs, authentification, protocoles et chiffrement.

**Important :** le Raspberry Pi seul ne possède pas toutes les interfaces nécessaires à chaque technologie RFID/NFC.

## 34. Caméra

Avec une caméra, il peut servir à la surveillance, au laboratoire IoT et au contrôle physique.

Il faut protéger authentification, chiffrement, mises à jour, flux vidéo et accès.

## 35. Automatisation

Le Raspberry Pi peut automatiser surveillance, sauvegardes, vérifications, alertes, collecte de métriques et synchronisation.

En cybersécurité, l'automatisation réduit les tâches répétitives.

## 36. Python et scripts

Python permet d'automatiser une chaîne simple :

**Collecte → Analyse → Détection → Alerte**

La programmation est une capacité du système, pas une propriété magique du Raspberry Pi.

## 37. Threat Intelligence

Une machine peut récupérer des informations publiques de sécurité : domaines malveillants, IP signalées, indicateurs de compromission et listes de blocage.

Il faut vérifier la qualité et la fraîcheur des sources.

## 38. Cyber-range miniature

Plusieurs Raspberry Pi peuvent constituer un environnement pédagogique :

**Pi 1 → serveur web**

**Pi 2 → client**

**Pi 3 → monitoring**

**Pi 4 → IDS**

**Pi 5 → honeypot**

Cela permet de comprendre une infrastructure distribuée.

## 39. Segmentation réseau

On peut séparer utilisateurs, IoT, serveurs et administration.

Exemple : **VLAN 10 utilisateurs / VLAN 20 IoT / VLAN 30 serveurs / VLAN 40 administration**.

Le but est d'éviter qu'un appareil compromis puisse communiquer librement avec tout le réseau.

## 40. Wi-Fi

Selon le modèle et le matériel ajouté, le Raspberry Pi peut participer à des expérimentations Wi-Fi.

Mais toutes les interfaces ne supportent pas toutes les fonctions. Certains scénarios nécessitent un adaptateur externe.

Les possibilités dépendent du chipset, du pilote, de la configuration et des mécanismes de sécurité du réseau.

> « Raspberry Pi = outil pour casser n'importe quel Wi-Fi » est donc une simplification fausse.

## 41. Sécurité du Raspberry Pi

Le Raspberry Pi doit être protégé comme n'importe quel ordinateur.

Risques : mot de passe faible, système non mis à jour, SSH exposé, services inutiles, ports ouverts, permissions excessives, stockage non protégé et accès physique.

## 42. Hardening

Le **hardening** signifie renforcer la configuration d'un système.

Mesures : supprimer les services inutiles, appliquer les mises à jour, utiliser des comptes individuels, limiter les privilèges, sécuriser SSH, configurer le firewall, surveiller les logs et limiter l'exposition Internet.

## 43. Stockage et secrets

Le stockage peut contenir mots de passe, clés privées, tokens, certificats et configurations.

Il faut éviter de stocker les secrets inutilement en clair.

## 44. Sécurité physique

Une personne ayant accès physiquement au Raspberry Pi peut manipuler le stockage, les ports, la configuration ou les GPIO.

La cybersécurité doit donc inclure la sécurité physique.

## 45. Limites matérielles

Le Raspberry Pi a des limites en CPU, RAM, stockage, réseau, température et alimentation.

Un service adapté à un serveur moderne peut être trop lourd pour un Raspberry Pi.

## 46. Raspberry Pi vs serveur professionnel

Il est excellent pour l'apprentissage, le prototypage, les petits services, l'IoT, les laboratoires et le monitoring léger.

Il n'est pas automatiquement adapté aux gros volumes, grandes bases de données, SIEM massif ou trafic réseau élevé.

## 47. Architecture pédagogique

**Internet → Firewall → Raspberry Pi Gateway → DNS / IDS / Monitoring → réseau de laboratoire → Web Lab / IoT Lab / Honeypot**

Cette architecture permet de comprendre plusieurs rôles dans une seule plateforme.

## 48. Comment analyser une démonstration

1. Quel rôle joue le Raspberry Pi ?
2. Quel logiciel lui donne cette capacité ?
3. Quelle interface utilise-t-il : Ethernet, Wi-Fi, USB, GPIO ou Bluetooth ?
4. Quelle position occupe-t-il dans le réseau ?
5. Quelle donnée peut-il réellement voir ?
6. Quelle condition rend la démonstration possible ?
7. Quelles sont les limites du matériel, du logiciel ou de l'architecture ?
8. Comment un défenseur détecterait-il cette activité ?
9. **Qu'est-ce qui a réellement été démontré ?**

## 49. Mythes

**« Raspberry Pi = outil de hacking »** → Faux : c'est un ordinateur.

**« Il peut pirater n'importe quel Wi-Fi »** → Faux : les capacités dépendent du matériel, du protocole et des protections.

**« Il suffit de le brancher pour voir tout le réseau »** → Faux : visibilité et position réseau sont déterminantes.

**« Un petit ordinateur ne sert pas professionnellement »** → Faux : certains rôles sont parfaitement adaptés à ses capacités.

**« Un Raspberry Pi compromis est sans importance »** → Faux : il peut devenir un point d'entrée ou un pivot selon son emplacement et ses privilèges.

## 50. Questions fortes pour le live

> « Quel logiciel transforme ce Raspberry Pi en outil de cybersécurité ? »

> « Quelle position occupe-t-il dans le réseau ? »

> « Quelles informations peut-il réellement observer ? »

> « Qu'est-ce qui dépend du matériel et qu'est-ce qui dépend du logiciel ? »

> « Quelle protection empêcherait cette démonstration ? »

> « Qu'est-ce qui a réellement été démontré ? »

## 51. Phrase prête à dire

> « Le Raspberry Pi n'est pas une arme de hacking. C'est un petit ordinateur qui devient intéressant en cybersécurité lorsqu'on lui donne un rôle : sonde réseau, serveur, honeypot, VPN, IDS, plateforme IoT ou laboratoire. La vraie question n'est donc pas “est-ce qu'un Raspberry Pi peut hacker ?”, mais “quel logiciel, quelle configuration et quelle position dans le réseau lui donnent cette capacité ?”. »

## 52. Tableau résumé

| Fonction | Rôle |
|---|---|
| Serveur | Héberger un service |
| Honeypot | Observer des comportements suspects |
| Honeynet | Organiser plusieurs leurres |
| DNS | Résoudre des noms |
| DHCP | Distribuer des paramètres réseau |
| VPN | Créer un tunnel réseau protégé |
| Firewall | Filtrer des flux |
| Reverse proxy | Contrôler l'accès aux applications |
| Bastion | Point d'accès contrôlé |
| Packet capture | Observer des paquets accessibles |
| Wireshark | Analyser les protocoles |
| Nmap | Cartographier un réseau autorisé |
| IDS | Détecter des activités suspectes |
| IPS | Détecter et bloquer certains flux |
| Prometheus | Collecter des métriques |
| Grafana | Visualiser des métriques |
| SIEM | Corréler des événements de sécurité |
| MQTT | Échanger des messages IoT |
| Docker | Exécuter des applications dans des conteneurs |
| GPIO | Interagir avec du matériel |
| RFID/NFC | Expérimenter avec certaines technologies d'identification |
| Bluetooth/BLE | Expérimenter avec certaines communications radio |
| Python | Automatiser des tâches |

## 53. Règle finale

Pour comprendre n'importe quelle démonstration Raspberry Pi :

**Matériel → Interface → Logiciel → Position réseau → Données accessibles → Capacité → Limites → Détection → Défense**

**Usage : formation, laboratoire, administration et défense.**
