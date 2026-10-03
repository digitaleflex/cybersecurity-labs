# LOIC — Fiche Live

## 1. Qu'est-ce que LOIC ?

**LOIC** signifie *Low Orbit Ion Cannon*. C'est un outil historique utilisé pour générer du trafic réseau vers une cible afin d'étudier ou de provoquer une dégradation de service.

Analogie : imaginez **une foule qui se présente en même temps devant une petite boutique**. Même si personne ne casse la boutique, le nombre de personnes peut empêcher les vrais clients d'entrer.

LOIC est surtout intéressant aujourd'hui pour comprendre le principe d'une génération de trafic et l'histoire des outils de stress réseau. Il ne représente pas à lui seul toutes les techniques de **DDoS (Distributed Denial of Service, déni de service distribué)** modernes.

## 2. DoS et DDoS : quelle différence ?

**DoS (Denial of Service, déni de service)** : une ou plusieurs sources génèrent suffisamment de demandes pour perturber un service.

**DDoS** : le trafic est distribué entre de nombreuses sources.

Analogie :

- **DoS** = une personne bloque une porte.
- **DDoS** = une foule arrive simultanément devant la porte.

L'objectif principal est la **disponibilité** : faire fonctionner le service moins bien ou le rendre inaccessible.

## 3. Que se passe-t-il techniquement ?

Un serveur possède des ressources limitées.

Le trafic peut solliciter :

- la **bande passante** (capacité de circulation des données) ;
- les **connexions** ;
- le **CPU** (processeur) ;
- la **RAM** (mémoire temporaire) ;
- les ressources de l'application ou de la base de données.

Analogie : un restaurant possède un nombre limité de tables, de serveurs et de capacités en cuisine. Trop de commandes simultanées peuvent provoquer un ralentissement.

## 4. Mythes et rumeurs à déconstruire

### « LOIC permet de pirater un serveur »

**Faux.** Générer du trafic et obtenir un accès au système sont deux choses différentes.

LOIC est associé au **déni de service**, pas à une fonction magique permettant de prendre le contrôle d'un serveur.

### « Un clic suffit pour faire tomber n'importe quel site »

**Faux.** L'efficacité dépend de nombreux facteurs : capacité de la cible, protections en place, volume de trafic, architecture et nature du service.

Un site correctement dimensionné et protégé peut absorber ou filtrer une partie importante du trafic.

### « DDoS = piratage du serveur »

**Faux.** Une attaque DDoS vise principalement la **disponibilité**. Elle n'implique pas nécessairement une intrusion.

Un attaquant peut chercher à empêcher les utilisateurs légitimes d'accéder à un service sans avoir obtenu les droits d'administration.

### « Plus on envoie de trafic, plus l'attaque est forcément efficace »

**Pas nécessairement.** Le trafic doit rencontrer un véritable goulot d'étranglement. Une infrastructure peut répartir, filtrer ou absorber une partie de la charge.

### « LOIC représente les DDoS modernes »

**Non.** LOIC est surtout un outil historique et pédagogique pour comprendre certaines idées de génération de trafic. Les attaques modernes peuvent être beaucoup plus distribuées, automatisées et sophistiquées.

## 5. Ce qu'il faut observer pendant la démonstration

**Trafic anormal → ressources sollicitées → ralentissement éventuel → utilisateurs impactés.**

Le point important est de comprendre **quelle ressource devient le goulot d'étranglement** (le point qui limite la capacité globale).

## 6. Comment un défenseur peut le détecter ?

On cherche des écarts par rapport au comportement habituel :

- augmentation inhabituelle du trafic ;
- grand nombre de connexions ;
- hausse du CPU ou de la mémoire ;
- augmentation des temps de réponse ;
- erreurs ou indisponibilité ;
- comportement anormal provenant de certaines sources.

Le **monitoring** (surveillance des systèmes) joue le rôle d'un tableau de bord.

## 7. Comment se protéger ?

Selon le scénario :

- **Rate limiting** (limitation du nombre de requêtes) ;
- limites de connexions ;
- pare-feu (**firewall**) ;
- **WAF (Web Application Firewall)** ;
- **load balancing** (répartition des demandes) ;
- **CDN (Content Delivery Network)** ;
- protection DDoS spécialisée ;
- surveillance et plan de réponse à incident.

## 8. Questions simples à poser à l'expert

1. Qu'est-ce qu'on provoque exactement ?
2. Quelle ressource est sollicitée ?
3. Pourquoi le serveur ralentit-il ?
4. Comment un administrateur détecterait-il cela ?
5. Quelle protection pourrait être ajoutée ?
6. Est-ce encore représentatif des attaques modernes ?
7. Quelle est la limite de cette démonstration ?

## Phrase prête à dire

> « Une attaque par déni de service ne cherche pas forcément à entrer dans le système. Elle peut simplement chercher à empêcher le service de fonctionner normalement. »

**Lab : uniquement sur des systèmes autorisés et isolés.**
