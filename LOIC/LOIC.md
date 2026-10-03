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

### « DDoS = piratage du serveur »

**Faux.** Une attaque DDoS vise principalement la **disponibilité**. Elle n'implique pas nécessairement une intrusion.

### « Plus on envoie de trafic, plus l'attaque est forcément efficace »

**Pas nécessairement.** Une infrastructure peut répartir, filtrer ou absorber une partie de la charge. Le véritable point déterminant est le **goulot d'étranglement**.

### « LOIC représente les DDoS modernes »

**Non.** LOIC est surtout un outil historique et pédagogique. Les attaques modernes peuvent être beaucoup plus distribuées, automatisées et sophistiquées.

## 5. Ce qu'il faut observer

**Trafic anormal → ressources sollicitées → ralentissement éventuel → utilisateurs impactés.**

Demander : **quelle ressource devient le goulot d'étranglement ?**

## 6. Détection

Chercher des écarts par rapport au comportement habituel :

- augmentation inhabituelle du trafic ;
- grand nombre de connexions ;
- hausse du CPU ou de la mémoire ;
- augmentation des temps de réponse ;
- erreurs ou indisponibilité ;
- comportement anormal provenant de certaines sources.

Le **monitoring** joue le rôle d'un tableau de bord.

## 7. Comment se protéger ? — scénarios pratiques

Il n'existe pas une protection unique contre tous les DoS/DDoS. OWASP distingue notamment les attaques **application**, **session/protocole** et **réseau/volumétriques** : la défense dépend donc de la ressource réellement saturée. 

### Scénario A — Trop de requêtes HTTP vers une page ou une API

**Problème :** l'application reçoit trop de requêtes et consomme CPU, RAM ou workers.

**Protection : Rate limiting**

On limite le nombre de requêtes par IP, session, compte, API key ou endpoint.

**Exemple :**
- page d'accueil : limite souple ;
- /login : limite stricte ;
- /api/search : limite par utilisateur/API key ;
- génération de PDF : quota strict.

Une API peut retourner **HTTP 429 — Too Many Requests** lorsqu'une limite est atteinte.

> « Le but n'est pas de bloquer tout le trafic, mais d'empêcher un acteur de consommer toutes les ressources disponibles. »

### Scénario B — Trop de connexions simultanées

**Problème :** le serveur conserve trop de connexions ouvertes et manque de ressources.

**Protections :**
- limite de connexions ;
- timeouts ;
- limite par IP/utilisateur ;
- fermeture des connexions inactives ;
- reverse proxy/load balancer.

**Exemple :** si un serveur dispose de 500 connexions disponibles mais qu'un grand nombre reste ouvert inutilement, les utilisateurs légitimes peuvent être refusés.

Pour les WebSockets, on peut aussi limiter les connexions, la taille des messages, l'inactivité et le débit des messages.

### Scénario C — Attaque HTTP lente

Des connexions sont maintenues ouvertes très longtemps et consomment progressivement les ressources.

**Protections :**
- timeout ;
- débit minimal acceptable ;
- nombre maximal de connexions ;
- reverse proxy ;
- détection des connexions anormalement longues.

> « Une connexion normale se termine rapidement. Une grande quantité de connexions anormalement longues est un signal à examiner. »

### Scénario D — Une requête est très coûteuse

Un DoS peut être efficace avec peu de trafic si chaque requête déclenche beaucoup de calcul.

Exemples : recherche complexe, export massif, génération PDF, traitement d'image, requête SQL coûteuse.

**Protections :**
- quotas ;
- pagination ;
- cache ;
- limites de taille ;
- optimisation SQL ;
- files de traitement asynchrones ;
- limitation des opérations coûteuses.

**Exemple :** au lieu de générer immédiatement un énorme PDF, l'application crée une tâche asynchrone et limite le nombre d'exports simultanés.

### Scénario E — Saturation de la bande passante

Ici, le lien Internet lui-même devient le goulot d'étranglement.

Un rate limiting placé uniquement sur le serveur peut arriver trop tard : le trafic a déjà traversé le lien.

**Protections :**
- CDN ;
- service de mitigation DDoS ;
- filtrage en amont ;
- capacité réseau adaptée ;
- architecture distribuée.

Un CDN correctement dimensionné peut absorber et distribuer une partie du trafic avant qu'il atteigne le serveur d'origine. citeturn0search25

> « Si la route vers l'entreprise est déjà bouchée, renforcer uniquement le serveur à l'intérieur ne suffit pas. Il faut agir avant le bouchon. »

### Scénario F — Un seul serveur porte toute l'application

**Problème :** si cette machine tombe, tout le service tombe.

**Protection : Load Balancing + haute disponibilité**

Architecture :

Utilisateur → Load Balancer → Serveur A / Serveur B / Serveur C

Si A devient indisponible, le répartiteur peut continuer à envoyer les requêtes vers B et C.

Cela réduit les **SPOF (Single Points of Failure)**, c'est-à-dire les composants uniques dont la panne suffit à interrompre le service.

### Scénario G — Une fonctionnalité précise est ciblée

Le trafic global peut sembler normal alors qu'un endpoint coûteux est surchargé.

**Protections :**
- WAF ;
- rate limiting par endpoint ;
- quotas ;
- authentification renforcée pour les fonctions coûteuses ;
- cache ;
- limitation des opérations coûteuses.

Exemple : /api/search peut recevoir une limite différente de /api/profile parce que les deux endpoints n'ont pas le même coût.

### Scénario H — Le trafic vient de nombreuses sources

Bloquer une seule IP ne suffit plus : c'est le principe du DDoS distribué.

**Protections :**
- CDN ;
- mitigation DDoS spécialisée ;
- filtrage en amont ;
- analyse comportementale ;
- coordination avec l'ISP/hébergeur ;
- architecture distribuée.

> « Une liste noire d'adresses IP n'est pas une stratégie complète contre un DDoS distribué. »

## 8. Exemple d'architecture défensive

Pour un site web :

Internet → CDN / DDoS Protection → WAF → Reverse Proxy → Application → Cache → Database

| Couche | Rôle |
|---|---|
| **CDN / DDoS** | Absorber ou filtrer une partie du trafic massif |
| **WAF** | Filtrer des requêtes web suspectes |
| **Reverse Proxy** | Contrôler les connexions et distribuer les requêtes |
| **Rate limiting** | Limiter la consommation par client |
| **Application** | Protéger les fonctions coûteuses |
| **Cache** | Éviter de recalculer les mêmes données |
| **Database** | Protéger les ressources et requêtes coûteuses |
| **Monitoring** | Détecter les anomalies |

L'objectif est la **défense en profondeur** : plusieurs contrôles indépendants plutôt qu'une seule protection. citeturn0search0turn0search1

## 9. Quelle protection choisir ?

La question centrale est :

**Qu'est-ce qui est saturé ?**

- **Bande passante** → CDN / mitigation DDoS / filtrage en amont.
- **Connexions** → limites / timeouts / reverse proxy.
- **CPU** → rate limiting / optimisation / cache.
- **RAM** → limites de taille / connexions / ressources.
- **Base de données** → cache / optimisation SQL / quotas / asynchronisme.
- **Fonction précise** → protection de l'endpoint / quotas / WAF.

## 10. Exemple concret pour le public

### Sans protection

1000 clients → serveur → base de données

Une surcharge peut faire tomber le serveur ou la base.

### Avec plusieurs couches

1000 clients → CDN → WAF → Rate Limit → Load Balancer → Applications → Cache → Database

Le but n'est pas de rendre le système impossible à attaquer.

Le but est d'éviter qu'une surcharge provoque immédiatement une panne complète et de préserver les utilisateurs légitimes.

## 11. Lorsqu'une attaque commence

### 1. Détecter
Surveiller trafic, latence, CPU, RAM, connexions, erreurs et disponibilité.

### 2. Confirmer
Comparer avec le comportement normal pour distinguer incident, pic légitime et attaque.

### 3. Activer le plan de réponse
Savoir qui intervient, qui contacte l'hébergeur/ISP et qui applique les mesures.

### 4. Mitiger
Selon le scénario : rate limiting, filtrage, WAF, CDN, mitigation DDoS, adaptation de capacité ou désactivation temporaire de fonctions non essentielles.

### 5. Surveiller
Vérifier que la mesure réduit l'impact sans bloquer les utilisateurs légitimes.

### 6. Analyser après l'incident
Conserver les logs, identifier le goulot d'étranglement et corriger l'architecture.

CISA recommande notamment l'identification, l'activation du plan de réponse, la notification des fournisseurs, la collecte de preuves, le filtrage et l'activation de services de mitigation lorsque disponibles. citeturn0search24

## 12. Phrase forte pour le live

> « La bonne question n'est pas seulement : comment bloquer l'attaque ? C'est : quelle ressource l'attaque essaie-t-elle de saturer, et à quelle couche pouvons-nous arrêter le problème avant qu'il atteigne cette ressource ? »

## 8. Questions à poser

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
