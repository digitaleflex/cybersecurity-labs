# Raspberry Pi — Fiche Live

## 1. Qu'est-ce que c'est ?

Un **Raspberry Pi** est un petit ordinateur monocarte : tous ses principaux composants sont regroupés sur une seule petite carte.

Il peut généralement faire fonctionner **Linux**, installer des logiciels et exécuter des services réseau.

Analogie simple : c'est comme **un petit PC réduit à l'essentiel**, que l'on peut utiliser comme serveur, ordinateur de laboratoire ou machine d'expérimentation.

Point important : **un Raspberry Pi n'est pas un outil de hacking en lui-même**. C'est une plateforme. Ce sont les logiciels installés et l'usage qu'on en fait qui déterminent son rôle.

## 2. Pourquoi est-il intéressant en cybersécurité ?

Sa petite taille, sa faible consommation et son fonctionnement proche d'un ordinateur Linux le rendent pratique pour les laboratoires.

On peut par exemple l'utiliser comme :

- **serveur de laboratoire** : héberger un petit service pour faire des tests ;
- **monitoring** (surveillance) : observer l'état d'un réseau ou d'un équipement ;
- **honeypot** (leurre) : installer un faux service pour observer des tentatives de connexion ;
- **DNS** (service qui transforme un nom comme example.com en adresse IP) ;
- **VPN (Virtual Private Network, réseau privé virtuel)** : créer un tunnel sécurisé pour certains usages ;
- machine d'automatisation ;
- plateforme pour l'**IoT (Internet of Things, objets connectés)** ;
- petit serveur Docker.

## 3. Pourquoi un hacker pourrait-il aussi l'utiliser ?

Parce qu'un Raspberry Pi peut exécuter beaucoup de logiciels Linux et peut être placé physiquement près d'un équipement ou d'un réseau.

Mais il faut distinguer deux choses :

**Le matériel** = le petit ordinateur.

**Le logiciel** = ce qui lui donne une fonction particulière.

Analogie : un couteau de cuisine et un couteau de bricolage sont tous deux des outils ; leur usage dépend de ce qu'on leur demande de faire. Pour un Raspberry Pi, c'est encore plus clair : la carte n'est pas l'attaque.

## 4. Ce qu'il faut observer pendant la démonstration

Si l'expert présente un Raspberry Pi, demander :

- Quel logiciel tourne dessus ?
- Quel est son rôle dans le scénario ?
- Est-il connecté au réseau ?
- Est-il utilisé comme serveur, capteur, relais ou machine de test ?
- Quelles données peut-il recevoir ou envoyer ?
- Comment est-il protégé ?

Cela permet de comprendre **le rôle réel de la machine**, plutôt que de penser que « Raspberry Pi = hacking ».

## 5. Risques à surveiller

Comme n'importe quel ordinateur, un Raspberry Pi peut être mal sécurisé.

Quelques risques :

- mot de passe faible ;
- service inutile exposé sur Internet ;
- logiciel non mis à jour ;
- ports réseau inutilement ouverts ;
- mauvaise configuration ;
- accès physique non protégé.

Un **port réseau** peut être comparé à une porte. Une porte ouverte n'est pas automatiquement dangereuse, mais il faut savoir pourquoi elle est ouverte et qui peut l'utiliser.

## 6. Comment le sécuriser ?

- utiliser des identifiants solides ;
- maintenir le système et les logiciels à jour ;
- limiter les services exposés ;
- utiliser un pare-feu lorsque nécessaire ;
- contrôler les accès ;
- éviter d'exposer directement des services sensibles sur Internet ;
- surveiller les connexions.

## 7. Questions simples à poser à l'expert

1. Quel rôle joue le Raspberry Pi dans cette démonstration ?
2. Quel logiciel lui donne cette capacité ?
3. Est-ce un outil d'attaque ou simplement une plateforme ?
4. Quelle donnée peut-il observer ou manipuler ?
5. Quel serait le risque pour une entreprise ?
6. Comment sécuriser cette machine ?

## Phrase prête à dire

> « Le Raspberry Pi n'est pas magique : c'est un petit ordinateur. En cybersécurité, son intérêt vient surtout des logiciels qu'on installe dessus et du rôle qu'on lui donne. »
