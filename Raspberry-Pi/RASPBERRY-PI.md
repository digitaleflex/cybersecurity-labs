# Raspberry Pi — Fiche Live

## 1. Qu'est-ce que c'est ?

Un **Raspberry Pi** est un petit ordinateur monocarte : ses principaux composants sont regroupés sur une seule petite carte.

Il peut faire fonctionner **Linux**, installer des logiciels et exécuter des services réseau.

Analogie : c'est comme **un petit PC réduit à l'essentiel**.

Point important : **un Raspberry Pi n'est pas un outil de hacking en lui-même**.

## 2. Pourquoi est-il intéressant en cybersécurité ?

On peut l'utiliser comme :

- **serveur de laboratoire** ;
- outil de **monitoring** (surveillance) ;
- **honeypot** (leurre destiné à observer des tentatives) ;
- serveur **DNS** (service qui traduit les noms de domaine en adresses IP) ;
- **VPN (Virtual Private Network, réseau privé virtuel)** ;
- plateforme d'automatisation ;
- plateforme **IoT (Internet of Things, objets connectés)** ;
- petit serveur Docker.

## 3. Mythes et rumeurs à déconstruire

### « Un Raspberry Pi est un appareil de hacking »

**Faux.** C'est avant tout un ordinateur.

Dire « Raspberry Pi = hacking » revient à dire « ordinateur = piratage ». Le matériel peut servir à de nombreux usages légitimes.

### « Parce qu'il est petit, il est peu puissant et inutile »

**Faux.** Sa puissance est limitée par rapport à un PC moderne, mais elle peut être largement suffisante pour des services légers, de l'automatisation, du réseau ou un laboratoire.

### « Un Raspberry Pi peut pirater n'importe quel Wi-Fi »

**Faux.** Les possibilités dépendent du matériel, des logiciels, de la configuration du réseau et surtout des mécanismes de sécurité utilisés.

Avoir un ordinateur capable d'analyser un réseau ne signifie pas automatiquement pouvoir compromettre ce réseau.

### « On peut brancher un Raspberry Pi sur un réseau et tout voir »

**Faux.** Ce qu'une machine peut observer dépend notamment de sa position dans le réseau, de sa configuration, du chiffrement et de l'architecture réseau.

### « Un Raspberry Pi caché suffit à espionner une entreprise »

**Pas automatiquement.** Il faut encore qu'il ait accès au réseau ou aux équipements concernés et que les contrôles de sécurité ne bloquent pas son activité.

## 4. Le vrai sujet : le rôle de la machine

**Matériel → système d'exploitation → logiciel → configuration → rôle.**

C'est cette chaîne qui explique ce que le Raspberry Pi peut réellement faire.

Analogie : un véhicule n'est pas « un véhicule de livraison » par nature. Il le devient lorsqu'on lui donne un rôle, un équipement et une mission.

## 5. Risques à surveiller

Comme tout ordinateur :

- mot de passe faible ;
- logiciel non mis à jour ;
- service inutile exposé ;
- ports inutilement ouverts ;
- mauvaise configuration ;
- accès physique non protégé.

Un **port réseau** peut être comparé à une porte. Une porte ouverte n'est pas forcément dangereuse, mais il faut savoir pourquoi elle est ouverte et qui peut l'utiliser.

## 6. Comment le sécuriser ?

- identifiants solides ;
- mises à jour ;
- services minimaux ;
- contrôle des accès ;
- pare-feu lorsque nécessaire ;
- limitation de l'exposition Internet ;
- surveillance des connexions.

## 7. Questions simples à poser à l'expert

1. Quel rôle joue le Raspberry Pi ?
2. Quel logiciel lui donne cette capacité ?
3. Est-ce le matériel ou le logiciel qui est important ici ?
4. Quelles données peut-il réellement observer ?
5. Quelle condition rend cette démonstration possible ?
6. Comment sécuriser cette machine ?

## Phrase prête à dire

> « Le Raspberry Pi n'est pas magique : c'est un petit ordinateur. Sa capacité en cybersécurité vient surtout des logiciels qu'on installe et du rôle qu'on lui donne. »
