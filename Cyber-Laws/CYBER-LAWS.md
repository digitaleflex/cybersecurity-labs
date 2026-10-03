# Cyber Laws — Comprendre les règles du numérique

## Objectif

Cette fiche sert à comprendre, vulgariser et commenter les **règles juridiques qui encadrent les pratiques numériques**.

Le principe central est simple :

> **Une capacité technique n'est pas automatiquement un droit juridique.**

Savoir scanner un réseau, intercepter une communication, tester une vulnérabilité ou manipuler un outil de sécurité ne signifie pas que l'on peut le faire sur n'importe quel système.

Cette documentation est principalement centrée sur le **Bénin**, avec des ouvertures vers les cadres africain et international.

---

# 1. Le texte central au Bénin

Le texte de référence est la **loi n°2017-20 du 20 avril 2018 portant Code du numérique en République du Bénin**. Elle couvre notamment les communications électroniques, les services de confiance, le commerce électronique, les données personnelles, la cybercriminalité et la cybersécurité. citeturn0search0turn0search5

Le Code a ensuite été modifié par la **loi n°2020-35 du 6 janvier 2021**. Le Secrétariat général du Gouvernement référence actuellement ces deux textes dans sa documentation officielle. citeturn1search0turn1search2

### À retenir

**Code du numérique = cadre général.**

Il ne concerne donc pas uniquement les hackers : il encadre aussi les entreprises numériques, les données personnelles, les communications, le commerce électronique, les services de confiance et différentes pratiques en ligne.

---

# 2. Les grandes familles de règles

Pour comprendre rapidement le droit cyber, on peut le diviser en plusieurs blocs :

| Domaine | Question juridique |
|---|---|
| Accès aux systèmes | Ai-je le droit d'entrer dans ce système ? |
| Données | Ai-je le droit d'accéder, copier, modifier ou transférer ces données ? |
| Disponibilité | Ai-je le droit de perturber un service ? |
| Identité | Ai-je le droit d'utiliser l'identité ou les données d'une autre personne ? |
| Vie privée | Ai-je le droit de collecter ou publier ces informations ? |
| Contenus | Ce que je publie est-il licite ? |
| Propriété intellectuelle | Ai-je le droit de copier ou redistribuer cette œuvre/logiciel ? |
| Fraude | Une manipulation numérique sert-elle à obtenir illicitement un bien ou un avantage ? |
| Cryptologie | Le moyen ou service utilisé est-il soumis à une déclaration, autorisation ou agrément ? |
| Preuve électronique | Comment les données numériques peuvent-elles être collectées et utilisées dans une procédure ? |

---

# 3. La règle fondamentale pour un hacker éthique

### Autorisation + périmètre + finalité

Avant un test de sécurité professionnel, il faut pouvoir répondre à trois questions :

1. **Qui m'autorise ?**
2. **Quel système suis-je autorisé à tester ?**
3. **Quelles techniques et quelles limites sont autorisées ?**

Un accord vague du type « teste mon site » n'est pas une bonne pratique professionnelle.

Il faut idéalement documenter :

- la cible ;
- les domaines/IP concernés ;
- les dates ;
- les techniques autorisées ;
- les techniques interdites ;
- les comptes de test ;
- les limites de charge ;
- la procédure d'arrêt ;
- le contact d'urgence ;
- le traitement des données découvertes ;
- la restitution et la destruction des preuves.

### Phrase live

> « En cybersécurité, l'autorisation ne doit pas seulement dire oui : elle doit définir précisément ce que l'on a le droit de tester. »

---

# 4. Accès illégal à un système

L'article 507 du Code du numérique sanctionne l'accès ou le maintien intentionnel et sans droit dans tout ou partie d'un système informatique.

La peine prévue peut aller de **1 à 5 ans d'emprisonnement** et de **500 000 à 1 000 000 FCFA d'amende**, ou l'une de ces peines. Une intention frauduleuse entraîne une échelle plus élevée prévue par le même article. citeturn3search1

### Ce que cela signifie concrètement

- tester son propre serveur : contexte autorisé ;
- tester un laboratoire volontairement exposé : contexte autorisé ;
- tester une plateforme avec autorisation écrite : contexte autorisé ;
- accéder à un serveur tiers sans droit : situation juridiquement différente et potentiellement pénale.

### Question live

> « Si une faille est visible publiquement, est-ce que j'ai automatiquement le droit de l'exploiter ? »

### Réponse

> « Non. La visibilité d'une faille ne constitue pas automatiquement une autorisation d'accès ou d'exploitation. »

---

# 5. Intercepter ou transférer des données

L'article 508 encadre notamment l'interception, la divulgation, l'utilisation, l'altération ou le détournement intentionnel et sans droit de données lors d'une transmission non publique.

Le Code prévoit également des sanctions plus lourdes lorsqu'une personne transfère sans autorisation des données provenant d'un système ou d'un support de stockage. citeturn3search1

### Application au pentest

Un pentester peut découvrir une donnée sensible sans avoir le droit de :

- la publier ;
- la vendre ;
- la transmettre à des tiers ;
- la conserver indéfiniment ;
- l'utiliser à une autre finalité.

### Bonne pratique

**Minimiser → documenter → protéger → restituer → détruire selon le cadre convenu.**

---

# 6. Perturber un système : DoS / DDoS

L'article 509 sanctionne les atteintes intentionnelles et sans droit au fonctionnement normal d'un système informatique.

Le Code prévoit notamment des peines allant jusqu'à **2 à 5 ans d'emprisonnement et 5 à 500 millions FCFA d'amende** pour l'interruption du fonctionnement normal, avec des niveaux plus sévères lorsque des dommages ou une perturbation grave sont provoqués. citeturn3search3

### Point important pour le live

> **« Faire tomber un serveur pour démontrer qu'il est vulnérable n'est pas une démonstration juridiquement neutre. »**

Pour un test de charge ou de résilience, il faut un environnement autorisé et un périmètre contrôlé.

---

# 7. Modifier ou supprimer des données

L'article 510 vise notamment le fait d'endommager, effacer, détériorer, altérer ou supprimer intentionnellement et sans droit des données informatiques.

Le texte prévoit une peine de **6 mois à 5 ans d'emprisonnement** et une amende de **500 000 à 2 millions FCFA**, avec des dispositions supplémentaires lorsque l'infraction est commise avec intention frauduleuse ou dans le but de nuire. citeturn3search3

### Exemple pédagogique

Modifier une base de données dans son propre laboratoire ≠ modifier la base de données d'une entreprise sans autorisation.

La technique peut être identique ; **le contexte juridique ne l'est pas**.

---

# 8. Usurpation d'identité

Le Code prévoit une infraction spécifique d'usurpation d'identité par système informatique.

L'article 562 prévoit notamment **1 à 5 ans d'emprisonnement** et **5 à 100 millions FCFA d'amende**, ou l'une de ces peines, dans les conditions définies par le texte. citeturn1search28

### Cela concerne notamment

- l'utilisation frauduleuse de l'identité d'une personne ;
- l'utilisation de données permettant de l'identifier ;
- certaines formes de faux profils ou d'utilisation malveillante d'identifiants.

### Attention

Un pseudonyme n'est pas automatiquement illégal.

C'est **l'utilisation frauduleuse et les circonstances** qui importent.

---

# 9. Harcèlement et fausses informations en ligne

Le Code prévoit également des infractions liées à certains comportements en ligne.

L'article 550 prévoit notamment des sanctions pour le harcèlement par communication électronique : **1 mois à 2 ans d'emprisonnement** et **500 000 à 10 millions FCFA d'amende**, ou l'une de ces peines, selon les conditions prévues par le texte.

Le même cadre prévoit aussi des sanctions pour certaines diffusions de fausses informations contre une personne via les réseaux sociaux ou supports électroniques. citeturn2search1

### Connexion avec le doxing

Une publication contenant des informations personnelles peut relever de plusieurs problématiques juridiques selon :

- la nature des données ;
- leur origine ;
- la manière dont elles ont été obtenues ;
- l'intention ;
- le contexte ;
- le préjudice ;
- les autres infractions éventuellement constituées.

**Doxing n'est donc pas synonyme d'une infraction juridique unique.**

---

# 10. Données personnelles

Le Code du numérique encadre également les traitements de données personnelles.

L'APDP dispose notamment de pouvoirs de contrôle et de sanction. Elle peut adresser des avertissements ou mises en demeure, ordonner la cessation d'un traitement, retirer une autorisation, interrompre un traitement ou verrouiller certaines données, et prononcer des sanctions pécuniaires dans les conditions prévues par la loi. citeturn1search12

L'APDP rappelle également l'existence de sanctions administratives, civiles et pénales pour certaines violations des règles relatives aux données personnelles. citeturn1search27

### Question live

> « Si une donnée est techniquement accessible, cela signifie-t-il que je peux la réutiliser librement ? »

### Réponse

> « Non. L'accessibilité technique d'une donnée ne supprime pas les obligations liées à sa protection, à sa finalité et à son utilisation. »

---

# 11. Propriété intellectuelle et logiciels

Le numérique ne supprime pas le droit d'auteur.

Le Code prévoit notamment des sanctions pour certaines atteintes à la propriété intellectuelle commises au moyen d'un réseau ou d'un système informatique. L'article 531 prévoit **3 mois à 2 ans d'emprisonnement** et **500 000 à 10 millions FCFA d'amende** pour les atteintes visées par le texte. citeturn2search2

### Exemples

- redistribuer un logiciel sans autorisation ;
- publier une œuvre protégée sans droit ;
- contourner certaines mesures techniques de protection ;
- mettre à disposition certains contenus protégés.

---

# 12. Escroquerie numérique

Le Code prévoit également l'application d'infractions de droit commun lorsqu'elles sont commises au moyen d'un système informatique.

L'article 566 prévoit notamment, pour l'escroquerie commise par système informatique, **2 à 7 ans d'emprisonnement** et une amende égale au quintuple de la valeur mise en cause, avec un minimum de **1 million FCFA**, dans les conditions prévues par le texte. citeturn3search5

### Cela permet de comprendre

Phishing, faux support technique, faux vendeur, faux investissement ou manipulation d'une victime peuvent relever de plusieurs qualifications selon les faits précis.

---

# 13. Cryptologie : un domaine désormais encadré par des textes d'application

Le Conseil des ministres du Bénin a adopté en juillet 2025 plusieurs textes d'application du Code du numérique.

Le **décret n°2025-366 du 2 juillet 2025** fixe notamment les modalités de déclaration, d'autorisation et d'agrément des moyens et services de cryptologie, ainsi que des modalités de règlement transactionnel liées à certaines infractions. citeturn1search25turn0search1

### Question live

> « Est-ce que le chiffrement est interdit ? »

### Réponse

> « Non. Le sujet juridique est plus précis : certains moyens et services de cryptologie sont encadrés par des règles de déclaration, d'autorisation ou d'agrément selon leur nature et leur usage. »

---

# 14. Enquêtes et preuves électroniques

Le Code prévoit un cadre spécifique pour les enquêtes cyber et la collecte de preuves électroniques.

Son Livre VI couvre notamment les infractions commises sur ou au moyen de systèmes informatiques ainsi que la collecte de preuves électroniques. Le texte prévoit également des garanties liées aux droits fondamentaux et au principe de proportionnalité. citeturn3search0

Le Bénin a en outre adhéré en 2024 à la **Convention de Budapest sur la cybercriminalité**, à son protocole additionnel sur les actes racistes et xénophobes et au deuxième protocole additionnel relatif notamment à la coopération et à la divulgation de preuves électroniques. citeturn0search2

---

# 15. Une erreur fréquente : « Je suis hacker éthique donc je peux tout tester »

Faux.

Le terme **ethical hacker** décrit une finalité professionnelle ; il ne remplace pas une autorisation juridique.

### La bonne formule

**Autorisation + périmètre + règles d'engagement + preuve de l'autorisation.**

---

# 16. Tableau pratique pour le live

| Action | Situation autorisée | Situation à risque |
|---|---|---|
| Scanner | Son propre réseau / cible autorisée | Réseau tiers sans autorisation |
| Pentest | Contrat + périmètre défini | Test sauvage |
| Exploitation | Lab ou cible explicitement autorisée | Exploitation d'un tiers |
| DDoS/charge test | Environnement prévu et contrôlé | Service public réel |
| Analyse de données | Données auxquelles on a droit | Données personnelles d'un tiers |
| OSINT | Recherche légitime et proportionnée | Collecte destinée à nuire |
| Doxing | — | Exposition malveillante de données personnelles |
| Phishing | Simulation autorisée | Tromper de vraies personnes |
| Malware | Lab isolé et autorisé | Déploiement sur des tiers |
| Wi-Fi | Réseau possédé ou autorisé | Réseau voisin |
| Exploitation d'une vulnérabilité | Programme/contrat autorisé | Système découvert au hasard |
| Publication d'une faille | Coordination responsable | Publication de secrets ou données volées |

---

# 17. La règle universelle

Avant toute action cyber, poser :

> **Ai-je l'autorisation ?**

Puis :

> **Quel est le périmètre ?**

Puis :

> **Quelle technique est autorisée ?**

Puis :

> **Quelles données puis-je voir ou conserver ?**

Puis :

> **Quel est le risque pour les personnes et les systèmes ?**

---

# 18. Questions fortes pour le live

### « Si je trouve une faille par hasard, puis-je l'exploiter ? »

> « Découvrir une vulnérabilité et avoir le droit de l'exploiter sont deux choses différentes. »

### « Un hacker éthique peut-il tester Google, Facebook ou TikTok ? »

> « Pas simplement parce qu'il est hacker éthique : il lui faut un cadre d'autorisation ou un programme permettant précisément le type de test envisagé. »

### « Si je ne vole rien, est-ce que l'accès reste illégal ? »

> « Potentiellement oui : le Code distingue notamment l'accès ou le maintien sans droit de la question du vol ou du dommage causé. »

### « Publier des données personnelles trouvées en ligne est-il sans risque ? »

> « Non. La disponibilité publique d'une information ne supprime pas automatiquement les règles relatives à son utilisation et à la protection des personnes. »

### « Est-ce qu'un outil de hacking est illégal ? »

> « Un outil et son utilisation sont deux questions différentes. Le contexte, la finalité et l'usage concret sont essentiels. »

### « Peut-on apprendre le hacking légalement ? »

> « Oui : laboratoire personnel, CTF, machines volontairement vulnérables, programmes de bug bounty et missions contractuelles sont des cadres permettant de pratiquer avec des règles définies. »

---

# 19. Les trois niveaux à ne jamais confondre

**TECHNIQUE**

> « Est-ce techniquement possible ? »

**AUTORISATION**

> « Ai-je le droit de le faire sur cette cible ? »

**RESPONSABILITÉ**

> « Quelles conséquences mon action peut-elle produire ? »

Une action peut être techniquement possible sans être autorisée.

Une action peut être autorisée mais rester dangereuse si elle dépasse le périmètre convenu.

---

# 20. Résumé de 30 secondes

> « Le droit cyber ne dit pas seulement ce qui est interdit. Il définit aussi les responsabilités autour des systèmes, des données, des communications, des contenus et des preuves numériques. Au Bénin, le Code du numérique constitue le cadre central, complété par des textes d'application. Pour un hacker éthique, la règle fondamentale reste l'autorisation, le périmètre et la maîtrise de l'impact. »

---

## Sources officielles principales

- Secrétariat général du Gouvernement du Bénin — Code du numérique.
- Loi n°2017-20 du 20 avril 2018.
- Loi n°2020-35 du 6 janvier 2021.
- APDP — Autorité de Protection des Données à caractère Personnel.
- Décret n°2025-366 du 2 juillet 2025 sur la cryptologie.
- Décret n°2024-733 sur l'adhésion à la Convention de Budapest.
- Décret n°2024-772 sur la Convention de Malabo.

**Usage : sensibilisation, formation, conformité et cybersécurité défensive.**

> Cette fiche est pédagogique et ne constitue pas un avis juridique. Pour une situation réelle, il faut vérifier le texte applicable, sa version en vigueur et, si nécessaire, consulter un professionnel du droit.
