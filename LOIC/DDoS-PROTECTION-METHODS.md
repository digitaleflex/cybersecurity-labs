# DDoS — Méthodes de protection et de mitigation

> Référence pédagogique : cette fiche explique les mécanismes de défense et de résilience. Elle ne constitue pas un guide pour attaquer un système tiers.

## 1. Le principe

Il n'existe pas une protection DDoS unique. Une attaque peut saturer une ressource différente selon son type :

- bande passante ;
- réseau et paquets ;
- connexions TCP ;
- TLS ;
- serveur web ;
- API ;
- application ;
- cache ;
- base de données ;
- DNS ;
- ressources cloud et parfois budget.

La question fondamentale est :

> **Quelle ressource l'activité malveillante cherche-t-elle à saturer ?**

La protection doit ensuite agir le plus tôt possible, idéalement avant que le trafic atteigne l'origine.

## 2. Défense en profondeur

Architecture de référence :

```text
Internet
   ↓
DDoS / Edge
   ↓
DNS / Anycast
   ↓
CDN / Cache
   ↓
WAF / Bot Management
   ↓
Rate Limiting / Quotas
   ↓
Load Balancer
   ↓
Reverse Proxy
   ↓
Application
   ↓
Cache / Queue
   ↓
Database
   ↓
Monitoring / SIEM / Alerting
```

Chaque couche a un rôle différent. Une protection efficace combine plusieurs contrôles.

## 3. Réduire la surface exposée

Avant même de parler de DDoS :

- fermer les ports inutiles ;
- désactiver les services inutiles ;
- ne pas exposer directement les interfaces d'administration ;
- utiliser des réseaux privés lorsque possible ;
- segmenter les systèmes ;
- limiter les services accessibles depuis Internet.

**Idée simple :** moins un système expose de portes, moins il possède de points directement attaquables.

## 4. Mitigation DDoS en amont

Pour un trafic volumétrique important, le serveur ne doit pas essayer d'absorber seul l'attaque.

On peut utiliser :

- protection DDoS du cloud provider ;
- protection de l'ISP ;
- fournisseur spécialisé de mitigation ;
- réseau edge ;
- scrubbing center.

```text
Internet → Mitigation → Trafic filtré → Application
```

Le filtrage en amont est essentiel lorsque le lien réseau vers l'origine risque lui-même d'être saturé.

## 5. Scrubbing

Un **scrubbing center** reçoit le trafic, analyse les flux et tente de laisser passer le trafic légitime vers l'origine.

```text
Internet
   ↓
Scrubbing
   ↓
Trafic filtré
   ↓
Origine
```

Il est particulièrement utile pour les attaques importantes.

## 6. CDN

Un **CDN (Content Delivery Network)** distribue des contenus depuis plusieurs points de présence.

Il peut :

- mettre des fichiers en cache ;
- servir certaines réponses sans atteindre l'origine ;
- répartir la charge ;
- rapprocher les utilisateurs du réseau edge ;
- absorber une partie des pics.

**Limite :** un CDN ne remplace pas toutes les protections applicatives et ne rend pas une application automatiquement résistante à toutes les attaques.

## 7. Anycast

Avec **Anycast**, plusieurs points du réseau annoncent le même service.

Le trafic peut ainsi être distribué entre plusieurs emplacements.

Cela est particulièrement utile pour les infrastructures DNS, CDN et certaines protections DDoS.

## 8. Protection DNS

Le DNS doit être résilient :

- serveurs DNS distribués ;
- redondance ;
- protection contre les attaques DNS ;
- monitoring ;
- plusieurs points de présence lorsque nécessaire.

Si le DNS est indisponible, un service web peut devenir inaccessible même si ses serveurs fonctionnent.

## 9. WAF

Un **WAF (Web Application Firewall)** analyse les requêtes web et applique des règles.

Il peut contrôler notamment :

- URL ;
- méthode HTTP ;
- paramètres ;
- en-têtes ;
- fréquence ;
- réputation ;
- comportement ;
- signatures d'attaques.

Le WAF est surtout pertinent pour les attaques de couche application.

## 10. Rate limiting

Le **rate limiting** limite la fréquence des requêtes.

Il peut être appliqué :

- par IP ;
- utilisateur ;
- session ;
- API key ;
- endpoint ;
- région ;
- type d'opération.

**Rate limit = contrôler la vitesse.**

Une limite trop agressive peut toutefois bloquer des utilisateurs légitimes.

## 11. Quotas

Un quota limite la quantité totale consommée sur une période.

Exemples :

- appels API par heure ;
- uploads par jour ;
- génération de rapports par utilisateur ;
- opérations coûteuses par minute.

**Rate limiting = vitesse.**

**Quota = quantité autorisée sur une période.**

## 12. CAPTCHA et challenges

Un CAPTCHA ou un challenge peut ralentir certaines automatisations et aider à distinguer certains utilisateurs humains des bots.

Mais :

> **Un CAPTCHA ne protège pas à lui seul contre un DDoS volumétrique.**

Il intervient surtout au niveau applicatif.

## 13. Bot management

Les systèmes de **bot management** analysent les comportements automatisés.

Ils peuvent utiliser :

- fréquence ;
- séquence de navigation ;
- réputation ;
- caractéristiques du client ;
- anomalies comportementales.

L'objectif est de traiter différemment :

**utilisateur légitime ↔ automatisation suspecte.**

## 14. Firewall

Un firewall peut filtrer :

- IP ;
- protocole ;
- port ;
- réseau source ;
- réseau destination ;
- état de connexion.

**Limite importante :** si le lien Internet est déjà saturé, un firewall placé derrière ce lien reçoit le problème trop tard.

## 15. ACL

Les **ACL (Access Control Lists)** sont des règles permettant d'autoriser ou refuser certains flux.

Elles peuvent être utilisées au niveau :

- réseau ;
- cloud ;
- firewall ;
- infrastructure interne.

## 16. Protection TCP

Certaines attaques ciblent les connexions TCP.

Les défenses peuvent inclure :

- SYN cookies ;
- limites de connexions ;
- timeouts ;
- filtrage ;
- protection L4 ;
- mitigation fournie par l'edge ou le réseau.

**SYN cookie :** mécanisme permettant de réduire certaines consommations de ressources lors d'un grand nombre de demandes de connexion TCP.

## 17. Protection UDP

Les services UDP peuvent nécessiter des contrôles spécifiques :

- filtrage ;
- limitation ;
- protection edge ;
- règles réseau ;
- mitigation spécialisée ;
- réduction des ports UDP exposés.

La fréquence seule ne détermine pas la sécurité : le protocole et le service comptent.

## 18. Protection TLS

HTTPS consomme également des ressources.

Il faut surveiller :

- connexions ;
- négociations TLS ;
- CPU ;
- sessions ;
- latence.

Une protection edge peut absorber une partie de cette charge avant l'origine.

## 19. Reverse proxy

Un **reverse proxy** est une passerelle placée devant l'application.

Il peut gérer :

- TLS ;
- routage ;
- cache ;
- timeouts ;
- limites ;
- filtrage ;
- logs.

Exemples connus : NGINX, HAProxy, Traefik, Envoy.

## 20. Connection limits

On peut limiter le nombre de connexions simultanées afin d'éviter qu'un petit nombre de clients immobilise toutes les ressources disponibles.

Cela doit être dimensionné selon l'application.

## 21. Timeouts

Un timeout fixe une durée maximale pour une opération.

Il peut exister entre :

- client et edge ;
- edge et load balancer ;
- proxy et application ;
- application et base de données.

Il évite qu'une opération bloque indéfiniment une ressource.

## 22. Limites de taille

Limiter la taille des données reçues :

- requête ;
- payload ;
- upload ;
- headers ;
- paramètres ;
- profondeur de traitement.

Principe :

> Une petite quantité de trafic ne doit pas pouvoir déclencher une consommation disproportionnée de ressources.

## 23. Cache

Le cache évite de recalculer ou récupérer plusieurs fois la même information.

Sans cache :

```text
Client → Application → Database
```

Avec cache :

```text
Client → Cache → Réponse
```

Le cache peut réduire la pression sur l'application et la base de données.

## 24. Protection des API

Les API sont sensibles à l'automatisation.

Mesures :

- API Gateway ;
- authentification ;
- quotas ;
- rate limiting ;
- limites de payload ;
- timeouts ;
- validation ;
- cache ;
- protection des opérations coûteuses ;
- monitoring par endpoint.

## 25. Protéger les fonctions coûteuses

Toutes les requêtes ne coûtent pas la même chose.

Exemple :

```text
GET /homepage       → coût faible
GET /search         → coût moyen
POST /report        → coût élevé
POST /heavy-job     → coût très élevé
```

Les limites doivent donc tenir compte du coût réel de chaque opération.

## 26. Base de données

Une attaque web peut surcharger une base de données indirectement.

Protections :

- cache ;
- indexation ;
- requêtes optimisées ;
- limites de connexions ;
- pool de connexions correctement dimensionné ;
- timeouts ;
- quotas ;
- pagination ;
- traitement asynchrone.

Principe :

> Une requête externe ne doit pas pouvoir consommer indéfiniment les ressources internes.

## 27. Queues et traitement asynchrone

Une opération coûteuse peut être placée dans une file.

```text
Client → API → Queue → Worker → Résultat
```

La requête HTTP reste courte et le traitement lourd est effectué séparément.

Cela protège notamment contre certaines surcharges applicatives en cascade.

## 28. Backpressure

La **backpressure** empêche un système amont d'envoyer plus de travail que le système aval ne peut traiter.

C'est particulièrement important dans les architectures distribuées.

## 29. Circuit breaker

Un **circuit breaker** évite qu'un service continue à appeler un composant déjà surchargé ou indisponible.

Il empêche la surcharge de se propager à travers toute l'architecture.

## 30. Load balancing

Un **load balancer** distribue le trafic entre plusieurs instances.

```text
             Load Balancer
             /     |     \
            ↓      ↓      ↓
        Server 1 Server 2 Server 3
```

Il réduit le risque qu'un serveur unique soit le seul point de saturation.

**Limite :** si le trafic total dépasse la capacité globale, tous les serveurs peuvent être affectés.

## 31. Haute disponibilité

La **HA (High Availability)** consiste à éviter les points uniques de défaillance.

On peut utiliser :

- plusieurs instances ;
- plusieurs zones ;
- redondance réseau ;
- services distribués ;
- bascule automatique.

## 32. Autoscaling

L'autoscaling ajoute ou retire automatiquement des ressources selon la charge.

Il aide pour certains pics légitimes et certaines surcharges applicatives.

Mais :

> **Autoscaling ≠ protection DDoS.**

Une attaque peut faire augmenter les ressources et donc les coûts.

## 33. Protection contre l'explosion des coûts cloud

Prévoir :

- budgets ;
- alertes de coûts ;
- quotas ;
- limites d'autoscaling ;
- monitoring ;
- protection DDoS.

Le but est d'éviter :

**trafic → autoscaling → ressources supplémentaires → facture anormale.**

## 34. Isolation de l'origine

Lorsque l'application est derrière un CDN ou un edge, il faut éviter autant que possible que le serveur d'origine soit directement accessible depuis Internet.

Conceptuellement :

```text
Internet → CDN / Edge → Origin privé
```

Sinon un attaquant peut tenter de contourner la couche de protection en visant directement l'origine.

## 35. Segmentation réseau

Séparer :

- frontend ;
- backend ;
- bases de données ;
- administration ;
- services internes.

Une attaque sur une couche ne doit pas automatiquement donner accès aux autres.

## 36. Filtrage géographique

Dans certains services, une restriction géographique peut réduire une partie du trafic indésirable.

Mais elle n'est pas une preuve d'identité et ne doit pas être considérée comme une protection suffisante.

## 37. Réputation IP et Threat Intelligence

Des systèmes peuvent utiliser des informations de réputation pour appliquer des contrôles supplémentaires.

Une blacklist IP seule est insuffisante contre un DDoS distribué, car les sources peuvent être nombreuses et changer.

## 38. IDS / IPS

**IDS (Intrusion Detection System)** : détecte des activités suspectes.

**IPS (Intrusion Prevention System)** : peut également bloquer certains flux.

Ils complètent les protections réseau et applicatives.

## 39. Monitoring

Surveiller notamment :

- requêtes/seconde ;
- bande passante ;
- connexions ;
- CPU ;
- RAM ;
- latence ;
- erreurs HTTP ;
- connexions DB ;
- temps de réponse ;
- saturation réseau.

Le monitoring est le tableau de bord de la défense.

## 40. Baseline

Une **baseline** décrit le comportement normal.

```text
Trafic normal → référence
Pic légitime → comparaison
Trafic inhabituel → alerte possible
```

Sans baseline, il est difficile de distinguer un pic commercial normal d'une attaque.

## 41. SIEM

Un **SIEM (Security Information and Event Management)** centralise les événements de sécurité.

Il aide à corréler :

- logs réseau ;
- logs WAF ;
- événements serveur ;
- authentifications ;
- erreurs ;
- alertes de sécurité.

## 42. Alerting

Une alerte peut être déclenchée lorsque plusieurs indicateurs changent simultanément :

- trafic inhabituel ;
- latence élevée ;
- erreurs élevées ;
- connexions anormales ;
- saturation CPU ;
- saturation réseau.

Les seuils doivent être adaptés au comportement normal pour limiter les faux positifs.

## 43. Blackholing / Null routing

Dans certains cas extrêmes, une destination peut être temporairement dirigée vers une route nulle.

Avantage :

- protéger éventuellement le reste du réseau.

Inconvénient :

- la destination concernée devient également inaccessible.

C'est donc une mesure de confinement, pas une solution idéale pour maintenir le service.

## 44. Redondance géographique

Ne pas dépendre d'un seul :

- datacenter ;
- région cloud ;
- serveur ;
- fournisseur ;
- réseau.

Plusieurs zones peuvent améliorer la résilience.

## 45. Plan de réponse DDoS

Avant l'incident, définir :

1. qui détecte ;
2. qui confirme ;
3. qui active la mitigation ;
4. qui contacte l'ISP/cloud provider ;
5. qui analyse les logs ;
6. qui communique ;
7. quand basculer vers une autre infrastructure.

Cycle :

```text
Détecter
   ↓
Confirmer
   ↓
Mitiger
   ↓
Surveiller
   ↓
Récupérer
   ↓
Analyser
   ↓
Améliorer
```

## 46. Tests de résilience

Tester régulièrement :

- capacité ;
- load balancing ;
- failover ;
- récupération ;
- alertes ;
- procédures d'escalade.

Les tests de charge et de sécurité doivent être autorisés et contrôlés.

## 47. Sauvegarde et reprise

Une attaque DDoS vise principalement la disponibilité, mais un incident peut être accompagné d'autres problèmes.

Prévoir :

- sauvegardes ;
- restauration testée ;
- plan de continuité ;
- reprise après sinistre ;
- redondance.

## 48. Tableau de décision

| Symptôme | Protections à examiner |
|---|---|
| Bande passante saturée | mitigation amont, ISP, scrubbing, CDN, Anycast |
| Beaucoup de SYN | protection L4, SYN cookies, limites, mitigation |
| Beaucoup d'UDP | filtrage, limites, edge, mitigation spécialisée |
| HTTP flood | CDN, WAF, rate limiting, bot management |
| API abusive | API Gateway, quotas, authentification, limites |
| Connexions excessives | connection limits, timeouts, reverse proxy |
| Fonction coûteuse | cache, quotas, queue, optimisation |
| Base surchargée | cache, pool, limites, optimisation, queue |
| Origine exposée | firewall, allowlist edge, réseau privé |
| Pic applicatif légitime | cache, load balancing, autoscaling |
| Attaque volumétrique | mitigation en amont / scrubbing |
| Incident prolongé | HA, failover, monitoring, plan de réponse |
| Coût cloud anormal | budgets, alertes, quotas, limites d'autoscaling |

## 49. La méthode universelle

Pour analyser une attaque :

**1. Quelle ressource est ciblée ?**

**2. Où est le goulot d'étranglement ?**

**3. Où peut-on filtrer ?**

**4. Où peut-on absorber ?**

**5. Où peut-on limiter ?**

**6. Comment détecter ?**

**7. Que se passe-t-il si une protection échoue ?**

## 50. Phrase pour le live

> « Une bonne protection DDoS ne consiste pas simplement à mettre un firewall. On construit plusieurs couches : filtrage en amont, CDN, WAF, limitation, protection des API, architecture distribuée, monitoring et plan de réponse. Et avant de choisir une protection, il faut savoir quelle ressource l'attaque cherche réellement à saturer. »

## 51. Sources de référence

Cette fiche s'appuie notamment sur les recommandations publiques de CISA, du FBI, du Centre canadien pour la cybersécurité et les documentations de fournisseurs cloud sur la résilience DDoS.

**Utilisation : formation, analyse et défense. Les manipulations offensives doivent rester limitées à des systèmes explicitement autorisés.**
