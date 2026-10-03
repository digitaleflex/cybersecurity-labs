# LOIC — Fiche Live

## 1. Qu'est-ce que LOIC ?

**LOIC** signifie *Low Orbit Ion Cannon*. C'est un outil historique utilisé pour générer beaucoup de trafic réseau vers une cible afin d'étudier ou de provoquer une dégradation de service.

On peut le voir comme **une foule qui essaierait d'entrer en même temps dans une petite boutique** : si le nombre de demandes devient trop important, les clients légitimes peuvent avoir du mal à accéder au service.

LOIC est surtout intéressant aujourd'hui pour comprendre le principe d'une génération de trafic et l'histoire des outils de stress réseau. Il ne représente pas à lui seul toutes les techniques de **DDoS (Distributed Denial of Service, déni de service distribué)** modernes.

## 2. DoS et DDoS : quelle différence ?

**DoS (Denial of Service, déni de service)** : une ou plusieurs sources génèrent suffisamment de demandes pour perturber un service.

**DDoS (Distributed Denial of Service)** : le trafic provient d'un grand nombre de machines ou de sources.

Analogie simple :

- **DoS** = une personne bloque une porte.
- **DDoS** = une foule arrive simultanément devant la porte.

L'objectif principal est la **disponibilité** : faire en sorte que le service fonctionne mal ou ne soit plus accessible aux utilisateurs normaux.

## 3. Que se passe-t-il techniquement ?

Une application ou un serveur possède des ressources limitées.

Le trafic peut solliciter :

- la **bande passante** (quantité de données pouvant circuler) ;
- les **connexions** (communications ouvertes avec les clients) ;
- le **CPU** (processeur qui exécute les tâches) ;
- la **RAM** (mémoire utilisée temporairement) ;
- les ressources de l'application ou de la base de données.

Analogie : un serveur ressemble à un restaurant. Il a un nombre limité de serveurs, de tables et de cuisine. Si des centaines de commandes arrivent simultanément, le problème peut venir du nombre de commandes, même si la cuisine fonctionne normalement.

## 4. Ce qu'il faut observer pendant la démonstration

Regarder la chaîne suivante :

**Trafic anormal → ressources davantage sollicitées → ralentissement éventuel → utilisateurs impactés.**

Le point important est de comprendre **quelle ressource devient le goulot d'étranglement** (le point qui limite la capacité globale).

Une attaque n'a donc pas forcément besoin de « casser » ou de pénétrer un serveur. Elle peut simplement chercher à empêcher le serveur de répondre normalement.

## 5. Comment un défenseur peut le détecter ?

On cherche des écarts par rapport au comportement habituel :

- augmentation inhabituelle du trafic ;
- grand nombre de connexions ;
- hausse du CPU ou de la mémoire ;
- augmentation des temps de réponse ;
- erreurs ou indisponibilité ;
- comportement anormal provenant de certaines sources.

Le **monitoring** (surveillance des systèmes) joue ici le rôle d'un tableau de bord : il permet de voir qu'une voiture roule normalement puis, soudainement, qu'une route devient totalement saturée.

## 6. Comment se protéger ?

Selon le scénario, une organisation peut utiliser :

- **Rate limiting** (limitation du nombre de requêtes par période) ;
- limites de connexions ;
- pare-feu (**firewall**) ;
- **WAF (Web Application Firewall, pare-feu spécialisé pour les applications web)** ;
- **load balancing** (répartition des demandes entre plusieurs serveurs) ;
- **CDN (Content Delivery Network, réseau de serveurs répartis géographiquement)** ;
- services spécialisés de protection DDoS ;
- surveillance et plan de réponse à incident.

Analogie : au lieu de laisser tout le monde entrer directement dans le restaurant, on peut avoir une file d'attente, un contrôle à l'entrée et plusieurs serveurs pour répartir les clients.

## 7. Ce qu'il faut retenir

**LOIC montre surtout une idée : trop de demandes peuvent empêcher un service de répondre correctement.**

Il faut aussi éviter une confusion : un outil de génération de trafic comme LOIC n'est pas représentatif de toutes les attaques DDoS modernes, qui peuvent utiliser de nombreuses machines, des réseaux de machines compromises ou des mécanismes de réflexion et d'amplification.

## 8. Questions simples à poser à l'expert

1. Qu'est-ce qu'on est exactement en train de provoquer ?
2. Quelle ressource du serveur est sollicitée ?
3. Pourquoi le serveur commence-t-il à ralentir ?
4. Comment un administrateur verrait-il cette anomalie ?
5. Quelle protection pourrait être ajoutée ?
6. Est-ce que cette technique est encore représentative des attaques modernes ?
7. Quelle est la limite de cette démonstration ?

## Phrase prête à dire

> « Ici, l'objectif n'est pas forcément de pénétrer le serveur. On cherche surtout à perturber sa disponibilité en lui imposant une charge qu'il ne peut pas absorber correctement. »

**Lab : uniquement sur des systèmes autorisés et isolés.**
