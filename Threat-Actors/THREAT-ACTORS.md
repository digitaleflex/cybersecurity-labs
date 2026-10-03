# Cyber Threat Actors — Fiche Live

Cette fiche sert à expliquer au public les principaux acteurs cyber cités pendant le live. Elle distingue **ransomware/cybercriminalité**, **hacktivisme** et **écosystèmes d'acteurs**.

> **Attention :** les noms, alias, désignations de chercheurs et affiliations évoluent. Un nom vu sur un réseau social ou une revendication ne constitue pas automatiquement une attribution confirmée.

## 1. Ransomware et cybercriminalité

| Acteur / alias | Catégorie | À retenir |
|---|---|---|
| **LockBit** | Ransomware / RaaS | Écosystème ransomware historiquement majeur, fonctionnant avec des affiliés. |
| **ALPHV / BlackCat** | Ransomware / RaaS | Opération connue pour chiffrement et extorsion de données. |
| **Cl0p / Clop** | Extorsion / cybercriminalité | Connu notamment pour des campagnes d'exploitation à grande échelle et de vol de données. |
| **Conti** | Ransomware | Ancien écosystème majeur ; plusieurs acteurs ont ensuite rejoint d'autres opérations. |
| **REvil / Sodinokibi** | Ransomware / RaaS | Ancien acteur majeur du modèle RaaS. |
| **DarkSide** | Ransomware | Connu notamment pour l'attaque contre Colonial Pipeline. |
| **Black Basta** | Ransomware / extorsion | Écosystème ciblant des organisations. |
| **BlackByte** | Ransomware | Groupe associé à des attaques contre des organisations. |
| **Hive** | Ransomware / RaaS | Ancienne opération importante de ransomware-as-a-service. |
| **Akira** | Ransomware / extorsion | Acteur encore observé dans les rapports récents. |
| **RansomHub** | Ransomware / RaaS | Écosystème d'affiliés et d'extorsion. |
| **Qilin** | Ransomware / RaaS | Acteur très visible dans les observations récentes. |
| **DragonForce** | Ransomware / RaaS | Écosystème ransomware actif dans les observations récentes. |
| **Vice Society** | Cybercriminalité | Acteur connu pour des campagnes contre différentes organisations. |
| **BianLian** | Extorsion | A évolué vers des opérations centrées notamment sur le vol de données et l'extorsion. |
| **AvosLocker** | Ransomware / RaaS | Modèle reposant sur des affiliés. |
| **Ragnar Locker** | Ransomware | Opération ransomware historiquement connue. |
| **Babuk** | Ransomware | Groupe historique associé à plusieurs opérations d'extorsion. |
| **DoppelPaymer** | Ransomware | Opération ransomware ayant ciblé des organisations. |
| **Maze** | Ransomware | Connu pour avoir popularisé le modèle de double extorsion. |
| **ShinyHunters** | Vol de données / extorsion | Nom associé à plusieurs campagnes de vol et d'extorsion de données. |

### RaaS en une phrase

**Ransomware-as-a-Service** signifie que des développeurs/opérateurs peuvent fournir malware ou infrastructure tandis que des **affiliés** réalisent certaines opérations.

Schéma pédagogique :

```
Accès initial → progression → vol de données → chiffrement éventuel
       ↓
   extorsion → pression → publication éventuelle
```

## 2. Acteurs hybrides / écosystèmes criminels

### LAPSUS$

Nom associé à des opérations de vol de données, compromission de comptes et extorsion. Il est particulièrement utile pour expliquer l'importance des identités, des comptes privilégiés et de l'ingénierie sociale.

### Scattered Spider / UNC3944

**Scattered Spider** est un nom utilisé dans la communauté de recherche pour un ensemble d'acteurs/activités. **UNC3944** est une désignation de suivi utilisée par certains chercheurs. Ces labels ne doivent pas être présentés comme une entreprise avec une structure officielle publique.

Les activités documentées incluent notamment la compromission d'identités, de comptes et d'environnements cloud.

### The Com / The Community

Plutôt qu'une organisation unique, **The Com** désigne un écosystème informel de communautés et d'individus cybercriminels avec des relations qui peuvent se chevaucher.

## 3. Hacktivisme

### Anonymous

**Anonymous** est principalement un label/mouvement hacktiviste décentralisé. Il ne faut pas le présenter comme une organisation classique avec un dirigeant et une liste officielle de membres.

Des opérations revendiquées sous ce nom ont historiquement utilisé notamment :

- DDoS ;
- défiguration ;
- publication de données ;
- campagnes de communication ;
- parfois compromissions et hack-and-leak.

**Règle essentielle :**

> Une revendication Anonymous n'est pas automatiquement une attribution technique à une organisation unique.

Toujours distinguer :

**revendication → affiliation → coordination → attribution.**

### Anonymous Sudan

Nom utilisé par un collectif hacktiviste connu notamment pour des campagnes DDoS et des revendications à dimension politique ou idéologique.

Le mot « Anonymous » dans le nom ne suffit pas à établir une affiliation organisationnelle avec Anonymous.

## 4. Hacktivisme pro-russe

### NoName057(16)

Collectif hacktiviste pro-russe principalement connu pour des campagnes DDoS. Des analyses publiques ont documenté son infrastructure **DDoSia**, ses canaux de coordination et la mobilisation de volontaires.

### Sector16

Acteur/collectif associé à l'écosystème hacktiviste pro-russe et cité dans des alertes publiques concernant des activités visant notamment des infrastructures critiques.

### Cyber Army of Russia Reborn (CARR)

Collectif hacktiviste pro-russe documenté par plusieurs agences de sécurité pour des opérations visant notamment des infrastructures critiques.

## 5. Noms à traiter avec prudence

### Bodys / DarkAngel

Pour ces noms, il faut vérifier la source, la période et le contexte avant de les présenter comme des organisations cyber établies.

Un nom observé sur Telegram, X, un forum ou une vidéo peut correspondre à :

- un alias ;
- un groupe temporaire ;
- une communauté ;
- un compte de propagande ;
- plusieurs acteurs utilisant le même nom ;
- ou une organisation réellement documentée.

**Ne pas transformer automatiquement un nom en attribution.**

## 6. Comment comprendre n'importe quel groupe

Pose six questions :

1. **Qui ?** — groupe, individus, affiliés, communauté ?
2. **Pourquoi ?** — argent, idéologie, espionnage, réputation ?
3. **Comment ?** — ransomware, DDoS, phishing, vol d'identifiants, intrusion, leak ?
4. **Organisation ?** — centralisée, décentralisée, affiliés, volontaires ?
5. **Infrastructure ?** — forums, messageries, serveurs, dépôts, sites ?
6. **Preuves ?** — revendication, rapport de chercheurs, éléments techniques, confirmation indépendante ?

## 7. Ne pas confondre

| Élément | Signification |
|---|---|
| **Outil** | Logiciel ou dispositif permettant une action |
| **Technique** | Méthode utilisée pour obtenir un effet |
| **Vulnérabilité** | Faiblesse exploitable |
| **Acteur** | Individu, groupe ou écosystème |
| **Revendi­cation** | Déclaration de responsabilité |
| **Attribution** | Établissement de l'acteur réellement responsable |
| **RaaS** | Modèle économique/organisationnel autour du ransomware |

### Exemple

**LOIC** → outil  
**DDoS** → technique  
**Anonymous** → label/mouvement  
**LockBit** → écosystème ransomware  
**Qilin** → opération/écosystème ransomware  
**NoName057(16)** → collectif hacktiviste  
**CARR** → collectif hacktiviste

## 8. Phrase prête pour le live

> « Le monde cyber n'est pas composé uniquement de hackers isolés. On trouve des groupes ransomware, des réseaux d'affiliés, des communautés criminelles et des collectifs hacktivistes. Et surtout, un nom ou une revendication ne suffit pas toujours à prouver qui est réellement derrière une opération. »

## 9. Question forte à poser à l'expert

> **« Parmi les noms que nous venons de citer, lesquels correspondent aujourd'hui à des organisations réellement structurées, lesquels sont des écosystèmes ou des labels, et quels éléments permettent de confirmer une attribution ? »**

## Cadre de sécurité

Cette fiche est destinée à l'information, à la sensibilisation, à la recherche et à la défense. Elle ne fournit pas de procédure opérationnelle pour attaquer des systèmes.
