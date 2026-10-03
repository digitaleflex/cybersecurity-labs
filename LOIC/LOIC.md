# LOIC — Fiche Live

## 1. Qu'est-ce que LOIC ?

**LOIC** signifie *Low Orbit Ion Cannon*. C'est un outil historique utilisé pour générer du trafic réseau vers une cible afin d'étudier ou de provoquer une dégradation de service.

Analogie : imaginez **une foule qui se présente en même temps devant une petite boutique**. Même si personne ne casse la boutique, le nombre de personnes peut empêcher les vrais clients d'entrer.

LOIC est surtout intéressant aujourd'hui pour comprendre le principe d'une génération de trafic et l'histoire des outils de stress réseau. Il ne représente pas à lui seul toutes les techniques de **DDoS (Distributed Denial of Service, déni de service distribué)** modernes.

## 2. Comprendre l'interface LOIC

L'interface historique est relativement simple. Pour la commenter à l'écran, lire les éléments dans cet ordre :

### Cible

Le champ de cible indique **vers quel système le trafic est dirigé**.

> « Ici, on définit simplement la destination du trafic. Définir une cible ne signifie pas qu'on a pris le contrôle de cette machine. »

### Port

Le port identifie le **service réseau** concerné.

Analogie : l'adresse IP correspond à l'immeuble ; le port correspond à une porte ou un service précis.

Exemples courants :

- **80** → HTTP ;
- **443** → HTTPS.

> « Le port permet de préciser quel service réseau est concerné par la communication. »

### Méthode / protocole

LOIC propose différents paramètres liés à la génération du trafic.

Le point important pour le public est de comprendre :

**protocole → trafic généré → traitement par la cible → consommation éventuelle de ressources.**

Il ne faut pas présenter ces modes comme des « armes différentes » : leur effet dépend du protocole, du service ciblé et de l'architecture.

### Paramètres de trafic

Ces réglages déterminent certaines caractéristiques du trafic généré.

> « Plus de trafic ne signifie pas automatiquement plus d'impact. Tout dépend de la capacité du réseau, des protections et surtout du goulot d'étranglement. »

### Bouton de démarrage / arrêt

Il permet de lancer ou d'arrêter la génération de trafic.

> « Ce bouton ne donne pas magiquement accès au serveur. Il déclenche une génération de trafic vers la cible. »

### Statistiques

Les compteurs permettent d'observer l'activité générée.

Pour commenter côté défenseur :

> « Si on regardait maintenant le serveur cible, qu'est-ce qu'on verrait dans les logs, le CPU, la mémoire, les connexions ou les temps de réponse ? »

### Schéma mental de l'interface

```text
┌──────────────────────────────────┐
│              LOIC                │
├──────────────────────────────────┤
│ CIBLE                            │
│ IP / domaine                     │
├──────────────────────────────────┤
│ PORT                             │
│ Service réseau                   │
├──────────────────────────────────┤
│ MÉTHODE / PROTOCOLE              │
│ Type de trafic                   │
├──────────────────────────────────┤
│ PARAMÈTRES                       │
│ Caractéristiques du trafic       │
├──────────────────────────────────┤
│ CONTRÔLE                         │
│ Démarrage / arrêt                │
├──────────────────────────────────┤
│ STATISTIQUES                     │
│ Activité générée                 │
└──────────────────────────────────┘
```

### Commentaire prêt à dire

> « L'interface de LOIC est finalement assez simple : on définit une cible, un service réseau, certains paramètres de génération de trafic, puis on observe l'activité produite. Mais il faut retenir que LOIC ne donne pas automatiquement accès au serveur : il génère du trafic et permet surtout d'illustrer le principe d'un déni de service. »

### Question forte

> **« On voit ce que LOIC envoie. Mais si on se place maintenant du côté du défenseur, qu'est-ce que le serveur voit exactement ? »**

## 3. DoS et DDoS : quelle différence ?

**DoS (Denial of Service, déni de service)** : une ou plusieurs sources génèrent suffisamment de demandes pour perturber un service.

**DDoS** : le trafic est distribué entre de nombreuses sources.

Analogie :

- **DoS** = une personne bloque une porte ;
- **DDoS** = une foule arrive simultanément devant la porte.

L'objectif principal est la **disponibilité** : faire fonctionner le service moins bien ou le rendre inaccessible.

## 4. Que se passe-t-il techniquement ?

Un serveur possède des ressources limitées.

Le trafic peut solliciter :

- la **bande passante** ;
- les **connexions** ;
- le **CPU** (processeur) ;
- la **RAM** (mémoire temporaire) ;
- les ressources de l'application ou de la base de données.

Analogie : un restaurant possède un nombre limité de tables, de serveurs et de capacités en cuisine. Trop de commandes simultanées peuvent provoquer un ralentissement.

## 5. Mythes et rumeurs à déconstruire

### « LOIC permet de pirater un serveur »

**Faux.** Générer du trafic et obtenir un accès au système sont deux choses différentes.

### « Un clic suffit pour faire tomber n'importe quel site »

**Faux.** L'efficacité dépend de nombreux facteurs : capacité de la cible, protections en place, volume de trafic, architecture et nature du service.

### « DDoS = piratage du serveur »

**Faux.** Une attaque DDoS vise principalement la **disponibilité**. Elle n'implique pas nécessairement une intrusion.

### « Plus on envoie de trafic, plus l'attaque est forcément efficace »

**Pas nécessairement.** Une infrastructure peut répartir, filtrer ou absorber une partie de la charge. Le véritable point déterminant est le **goulot d'étranglement**.

### « LOIC représente les DDoS modernes »

**Non.** LOIC est surtout un outil historique et pédagogique. Les attaques modernes peuvent être beaucoup plus distribuées, automatisées et sophistiquées.

## 6. Ce qu'il faut observer

**Trafic anormal → ressources sollicitées → ralentissement éventuel → utilisateurs impactés.**

Demander : **quelle ressource devient le goulot d'étranglement ?**

## 7. Détection

Chercher des écarts par rapport au comportement habituel :

- augmentation inhabituelle du trafic ;
- grand nombre de connexions ;
- hausse du CPU ou de la mémoire ;
- augmentation des temps de réponse ;
- erreurs ou indisponibilité ;
- comportement anormal provenant de certaines sources.

Le **monitoring** joue le rôle d'un tableau de bord.

## 8. Comment se protéger ?

La protection dépend de la ressource réellement saturée.

- **Trop de requêtes HTTP** → rate limiting, quotas, cache ;
- **Trop de connexions** → limites, timeouts, reverse proxy ;
- **Requêtes coûteuses** → optimisation, cache, traitement asynchrone, quotas ;
- **Bande passante saturée** → CDN, mitigation DDoS, filtrage en amont ;
- **Serveur unique** → load balancing et haute disponibilité ;
- **Endpoint précis** → protection spécifique de l'API ou de la fonctionnalité.

Architecture défensive typique :

**Internet → CDN / DDoS Protection → WAF → Reverse Proxy → Application → Cache → Database**

L'objectif est la **défense en profondeur** : plusieurs contrôles plutôt qu'une seule protection.

## 9. Lorsqu'une attaque commence

1. **Détecter** — trafic, latence, CPU, RAM, connexions, erreurs.
2. **Confirmer** — distinguer pic légitime, incident et attaque.
3. **Activer le plan de réponse**.
4. **Mitiger** — filtrage, rate limiting, WAF, CDN ou service de mitigation selon le cas.
5. **Surveiller** — vérifier l'effet des mesures.
6. **Analyser après l'incident** — logs, goulot d'étranglement et corrections d'architecture.

## 10. Questions à poser

1. Qu'est-ce qu'on provoque exactement ?
2. Quelle ressource est sollicitée ?
3. Pourquoi le serveur ralentit-il ?
4. Comment un administrateur détecterait-il cela ?
5. Quelle protection pourrait être ajoutée ?
6. Est-ce encore représentatif des attaques modernes ?
7. Quelle est la limite de cette démonstration ?
8. **Qu'est-ce qui a réellement été démontré ?**

## Phrase prête à dire

> « Une attaque par déni de service ne cherche pas forcément à entrer dans le système. Elle peut simplement chercher à empêcher le service de fonctionner normalement. »

**Lab : uniquement sur des systèmes autorisés et isolés.**
