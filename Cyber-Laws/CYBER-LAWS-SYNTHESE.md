# Cyber Laws — Fiche synthèse Live

> **Version : octobre 2026**
>
> Fiche de révision pour commenter les règles et sanctions qui encadrent les pratiques numériques.

---

# 1. Carte mentale

```
DROIT CYBER
│
├── INTERNATIONAL
│   ├── Convention de Budapest
│   ├── Convention ONU contre la cybercriminalité
│   └── Convention de Malabo — Afrique
│
├── UNION EUROPÉENNE
│   ├── RGPD — données
│   ├── NIS2 — cybersécurité
│   ├── DORA — finance
│   ├── CRA — produits numériques
│   ├── Cybersecurity Act — certification
│   ├── CER — entités critiques
│   ├── DSA — plateformes
│   └── AI Act — IA
│
├── FRANCE
│   ├── Code pénal — STAD
│   ├── RGPD + Informatique et Libertés
│   ├── SREN
│   └── ANSSI
│
└── BÉNIN
    ├── Code du numérique
    ├── APDP
    ├── Cryptologie
    ├── Budapest
    └── Malabo
```

---

# 2. La règle numéro 1

> **Une capacité technique n'est pas une autorisation juridique.**

Avant un pentest :

**AUTORISATION → PÉRIMÈTRE → TECHNIQUE → IMPACT → DONNÉES → RESTITUTION**

---

# 3. INTERNATIONAL

## Budapest

Cadre majeur pour :

- cybercriminalité ;
- coopération judiciaire ;
- preuves électroniques ;
- entraide ;
- réseau 24/7.

**Le Bénin est Partie.**

## ONU

Convention adoptée le **24 décembre 2024**.

Ouverte à la signature en octobre 2025.

À septembre 2026 :

**pas encore en vigueur**.

L'entrée en vigueur nécessite **40 instruments** de ratification, acceptation, approbation ou adhésion.

## Malabo

Cadre africain sur :

- cybersécurité ;
- cybercriminalité ;
- données ;
- commerce électronique.

Le Bénin a autorisé sa ratification en 2024.

---

# 4. UNION EUROPÉENNE

| Texte | Fonction |
|---|---|
| **RGPD** | Protection des données |
| **NIS2** | Cybersécurité des organisations |
| **DORA** | Résilience numérique financière |
| **CRA** | Sécurité des produits numériques |
| **Cybersecurity Act** | ENISA + certification |
| **CER** | Résilience des entités critiques |
| **DSA** | Plateformes et services numériques |
| **AI Act** | Gouvernance de l'IA |

### Chiffres à retenir

**RGPD :** jusqu'à **20 M€ ou 4 % du CA mondial** selon la violation.

**NIS2 — essentiel :** au moins **10 M€ ou 2 % du CA mondial** comme plafond minimal prévu.

**NIS2 — important :** au moins **7 M€ ou 1,4 % du CA mondial** comme plafond minimal prévu.

**DORA :** applicable depuis **17 janvier 2025**.

**CRA :** application générale **11 décembre 2027**.

Certaines obligations CRA de signalement sont déjà applicables depuis **11 septembre 2026**.

---

# 5. FRANCE

## Article 323-1 — accès frauduleux

**3 ans + 100 000 €**

Si modification/suppression de données ou altération :

**5 ans + 150 000 €**

Certains systèmes de l'État :

**jusqu'à 7 ans + 300 000 €**

## Article 323-2 — perturbation

**5 ans + 150 000 €**

Certains systèmes de l'État :

**jusqu'à 7 ans + 300 000 €**

## Article 323-3 — données

Introduction/extraction/transmission/suppression/modification frauduleuse :

**5 ans + 150 000 €**

### Autres piliers

**RGPD + Informatique et Libertés**

**SREN 2024**

**ANSSI**

---

# 6. BÉNIN

## Texte central

**Loi n°2017-20 du 20 avril 2018**

→ Code du numérique.

Modifiée par :

**Loi n°2020-35 du 6 janvier 2021**

Domaines :

- cybercriminalité ;
- cybersécurité ;
- données personnelles ;
- communications électroniques ;
- preuves électroniques ;
- commerce électronique ;
- cryptologie.

## Coopération

**Loi n°2024-05** → Malabo.

**Loi n°2024-06** → Budapest + protocoles.

**CNIN** → point focal béninois du réseau 24/7.

## Cryptologie

**Décret n°2025-366**

→ déclaration / autorisation / agrément de certains moyens et services de cryptologie.

> **Ne pas dire : « le chiffrement est interdit ».**

---

# 7. Même action, questions différentes

| Action | Question juridique |
|---|---|
| Scanner | Ai-je l'autorisation ? |
| Exploiter une faille | La cible est-elle dans le périmètre ? |
| DDoS | Le test est-il expressément autorisé ? |
| Copier une base | Ai-je le droit d'accéder aux données ? |
| Publier des données | Ai-je le droit de les diffuser ? |
| Doxer | Quel est le contexte et le préjudice ? |
| Phishing | Simulation autorisée ou fraude réelle ? |
| Malware | Lab autorisé ou système réel ? |
| Wi-Fi | Réseau possédé ou autorisé ? |
| Bug bounty | Les règles du programme l'autorisent-elles ? |

---

# 8. Cybersecurity ≠ Cybercrime

### CYBERSECURITY

**Protéger**

- audit ;
- pentest autorisé ;
- SOC ;
- CTF ;
- bug bounty ;
- réponse à incident ;
- laboratoire.

### CYBERCRIME

**Comportement potentiellement illicite**

- accès frauduleux ;
- vol ;
- fraude ;
- extorsion ;
- sabotage ;
- interception illégitime ;
- destruction ;
- perturbation sans droit.

> **Le même outil peut apparaître dans les deux contextes.**

---

# 9. Doxing

Le doxing n'est pas nécessairement une infraction unique portant ce nom.

Selon les faits, plusieurs règles peuvent intervenir :

- données personnelles ;
- vie privée ;
- harcèlement ;
- menaces ;
- usurpation ;
- fraude ;
- diffamation ;
- accès frauduleux ;
- divulgation illicite.

### Question clé

> **Comment l'information a-t-elle été obtenue, pourquoi a-t-elle été publiée et quelles conséquences produit-elle ?**

---

# 10. Les 6 questions du hacker éthique

> **1. Qui m'autorise ?**

> **2. Quelle cible ?**

> **3. Quelle période ?**

> **4. Quelles techniques ?**

> **5. Quelles données ?**

> **6. Quelle limite d'impact ?**

Une réponse manque ?

> **STOP — clarifier avant de tester.**

---

# 11. Questions fortes pour le live

### « Si une faille est publique, puis-je l'exploiter ? »

> Non. Une vulnérabilité visible n'est pas automatiquement une autorisation.

### « Un outil de hacking est-il illégal ? »

> L'outil et son utilisation sont deux questions différentes. Le contexte et l'autorisation comptent.

### « Hacker éthique = droit de tester ? »

> Non. Le statut professionnel ne remplace pas l'autorisation.

### « Une attaque depuis un autre pays est-elle impunie ? »

> Non. Les mécanismes de coopération internationale permettent notamment de traiter les infractions et les preuves transfrontalières.

### « Publier une donnée trouvée en ligne est-il toujours légal ? »

> Non. L'accessibilité d'une information ne supprime pas automatiquement les règles relatives à sa protection et à son utilisation.

### « Peut-on apprendre le hacking légalement ? »

> Oui : lab, CTF, bug bounty et missions autorisées permettent de pratiquer dans un cadre défini.

---

# 12. Phrase finale

> **« En cybersécurité, savoir faire ne suffit pas : il faut savoir ce qu'on a le droit de faire, sur quelle cible, dans quelles limites et avec quelles conséquences. »**

---

## Sources officielles

### International
- https://www.coe.int/fr/web/cybercrime/the-budapest-convention
- https://treaties.un.org/Pages/ViewDetails.aspx?chapter=18&clang=_fr&mtdsg_no=XVIII-16&src=IND

### UE
- https://eur-lex.europa.eu/legal-content/FR/TXT/?uri=CELEX:32016R0679
- https://eur-lex.europa.eu/eli/dir/2022/2555
- https://eur-lex.europa.eu/legal-content/FR/ALL/?uri=CELEX:32022R2554
- https://eur-lex.europa.eu/eli/reg/2024/2847/oj/fra
- https://eur-lex.europa.eu/eli/reg/2024/1689

### France
- https://www.legifrance.gouv.fr/codes/section_lc/LEGITEXT000006070719/LEGISCTA000006149839/
- https://www.legifrance.gouv.fr/eli/loi/2024/5/21/2024-449/jo/texte
- https://cyber.gouv.fr/reglementation/cybersecurite-systemes-dinformation/

### Bénin
- https://sgg.gouv.bj/recherche/?keywords=code+du+num%C3%A9rique&type=loi
- https://sgg.gouv.bj/documentheque/44/
- https://sgg.gouv.bj/doc/decret-2025-366/download

> **Fiche pédagogique. Vérifier les textes en vigueur avant toute décision juridique réelle.**
