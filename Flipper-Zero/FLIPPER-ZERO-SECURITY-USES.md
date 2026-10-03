# Flipper Zero — Usages cybersécurité et limites

## 1. Comprendre le Flipper Zero

Le **Flipper Zero** est un appareil portable d'expérimentation électronique et radio. Il regroupe plusieurs interfaces permettant d'observer, analyser, enregistrer ou émuler certains signaux et technologies.

Ce n'est pas une « clé universelle de hacking ».

Ses capacités dépendent du **protocole**, du **matériel**, de l'authentification, du chiffrement, de la présence éventuelle de codes dynamiques et du contexte physique.

La documentation officielle décrit notamment les fonctions Sub-GHz, RFID 125 kHz, NFC, infrarouge, GPIO, iButton, Bad USB et U2F. citeturn0search0turn0search1

---

## 2. Le modèle mental à retenir

Pour analyser une démonstration :

**Signal / interface → protocole → authentification → données échangées → action possible → limites → défense**

Le point essentiel est de ne pas confondre :

- **lire** un signal ;
- **enregistrer** un signal ;
- **rejouer / émuler** un signal ;
- **authentifier** un utilisateur ;
- **obtenir un accès** à un système.

Une capacité d'émulation ne signifie donc pas automatiquement qu'un système sécurisé peut être contourné.

---

## 3. Les grandes fonctions

### NFC — 13,56 MHz

Le NFC est utilisé notamment pour certaines cartes, badges, transports et tags. Le Flipper possède un module NFC capable de lire, sauvegarder et émuler certaines cartes NFC. Les systèmes NFC peuvent intégrer authentification et chiffrement : le résultat dépend donc fortement de la technologie utilisée. citeturn0search3turn0search1

**À commenter :**
> « Le point important n'est pas seulement de savoir lire une carte : il faut comprendre comment le système authentifie réellement cette carte. »

### RFID 125 kHz

Le RFID basse fréquence est utilisé notamment dans certains systèmes de contrôle d'accès. Le Flipper peut lire, sauvegarder, émuler et écrire certains formats RFID 125 kHz. Ces technologies n'offrent pas toutes le même niveau de sécurité. citeturn0search10

**À retenir :**
Un badge ancien basé sur un identifiant statique peut présenter un risque différent d'un système utilisant une authentification cryptographique moderne.

### Sub-GHz

Le Flipper peut interagir avec certains systèmes radio sous 1 GHz, notamment des télécommandes et équipements utilisant des protocoles compatibles avec son matériel. Les bandes supportées dépendent notamment de la région. citeturn0search1

Le vrai sujet est :

**code fixe ou code dynamique ?**

Un signal enregistré n'est pas nécessairement réutilisable. Les mécanismes de rolling code, d'authentification ou d'anti-rejeu changent complètement le scénario.

### Infrarouge

Le Flipper peut apprendre et reproduire des commandes infrarouges utilisées par des téléviseurs, climatiseurs et équipements multimédias. citeturn0search6

Ici, la sécurité est souvent très différente d'un système d'accès : une télécommande infrarouge classique peut simplement transmettre une commande sans authentification forte.

### GPIO

Les broches GPIO permettent de connecter le Flipper à des circuits et modules électroniques. Elles sont utiles pour l'expérimentation, le débogage et l'apprentissage des interfaces matérielles. citeturn0search1turn0search8

### iButton / 1-Wire

Le Flipper supporte certains systèmes iButton utilisant le bus 1-Wire et peut lire, émuler et écrire certains types de clés compatibles. citeturn0search0turn0search1

### USB / Bad USB

Le mode Bad USB permet d'émuler un clavier USB afin d'envoyer des frappes à un ordinateur. Cela peut servir aux tests de sécurité autorisés, mais l'idée importante est simple :

**le Flipper n'exploite pas magiquement l'ordinateur ; il se présente comme un périphérique d'entrée et exécute une séquence de frappes.** citeturn0search0

### U2F

Le Flipper peut également servir de clé de second facteur U2F pour certains services compatibles. C'est un bon rappel qu'un même appareil peut avoir des usages offensifs de laboratoire et des usages défensifs ou d'authentification. citeturn0search0

---

## 4. Pourquoi certaines démonstrations fonctionnent

Une démonstration réussie peut dépendre de :

1. technologie ancienne ou faible ;
2. identifiant statique ;
3. absence d'authentification forte ;
4. protocole mal configuré ;
5. système prévu pour accepter un signal rejouable ;
6. accès physique au badge, à la télécommande ou au périphérique ;
7. matériel compatible ;
8. environnement de laboratoire spécialement préparé.

Il faut toujours identifier la condition qui rend la démonstration possible.

---

## 5. Ce que le Flipper ne signifie PAS

### « Il ouvre toutes les voitures »

Faux.

Les systèmes automobiles modernes utilisent différents mécanismes d'authentification, de chiffrement et de protection. La compatibilité radio ne signifie pas capacité universelle de déverrouillage.

### « Il clone tous les badges »

Faux.

Certains badges et protocoles sont beaucoup plus résistants à la lecture, à l'émulation et au rejeu que d'autres.

### « Il pirate un téléphone juste en passant à côté »

Faux.

La proximité radio seule ne constitue pas automatiquement une compromission.

### « Il peut pirater n'importe quel ordinateur avec Bad USB »

Faux.

Bad USB émule une entrée clavier. Le résultat dépend du système, des politiques de sécurité, du verrouillage de session, des contrôles USB et de ce que l'utilisateur ou l'environnement autorise.

### « S'il reproduit un signal, le système est compromis »

Pas nécessairement.

La reproduction d'un signal et la compromission d'un système sont deux choses différentes.

---

## 6. Comment analyser une attaque ou une démonstration

Utiliser cette grille :

| Question | Ce qu'il faut chercher |
|---|---|
| Quoi ? | Technologie utilisée |
| Où ? | Système ou périphérique ciblé |
| Comment ? | Lecture, émission, émulation ou entrée USB |
| Authentification ? | Oui / non / inconnue |
| Chiffrement ? | Oui / non / inconnu |
| Code statique ? | Oui / non |
| Code dynamique ? | Oui / non |
| Accès physique ? | Nécessaire ou non |
| Limite ? | Distance, protocole, matériel, configuration |
| Défense ? | Authentification, chiffrement, contrôle d'accès, surveillance |

---

## 7. Défense

### Contrôle d'accès

- privilégier les technologies avec authentification forte ;
- éviter les identifiants statiques lorsque le contexte exige davantage de sécurité ;
- révoquer rapidement les badges perdus ;
- journaliser les accès ;
- segmenter les systèmes critiques ;
- protéger physiquement les lecteurs et contrôleurs.

### Radio

- utiliser des protocoles modernes lorsque disponibles ;
- préférer les mécanismes résistants au rejeu ;
- surveiller les comportements anormaux ;
- limiter les fonctions radio inutiles.

### USB

- contrôler les périphériques USB ;
- limiter les périphériques HID non autorisés ;
- verrouiller les sessions ;
- appliquer le principe du moindre privilège ;
- utiliser les contrôles endpoint adaptés.

### Appareil Flipper lui-même

- verrouillage/PIN ;
- firmware à jour ;
- contrôle physique ;
- protection de la carte microSD et des données enregistrées ;
- ne conserver que les données nécessaires.

La documentation officielle indique notamment que le Flipper peut être verrouillé par PIN et possède un mode Dummy Mode réduisant ses fonctions. citeturn0search7

---

## 8. Le vrai enseignement cybersécurité

Le Flipper Zero est intéressant parce qu'il rend visibles des concepts normalement abstraits :

**radio → protocole → authentification → confiance → accès**

Il permet donc de montrer qu'une sécurité physique ou radio dépend moins de « l'appareil magique » que de la qualité du protocole et du modèle de sécurité.

---

## 9. Questions fortes à poser pendant le live

1. Quelle technologie est utilisée ici ?
2. Est-ce du NFC, du RFID, du Sub-GHz, de l'infrarouge ou de l'USB ?
3. Le système utilise-t-il une authentification ?
4. Le code est-il statique ou dynamique ?
5. Le signal est-il chiffré ?
6. La démonstration nécessite-t-elle un accès physique ?
7. Qu'est-ce qui rend cette démonstration possible ?
8. Est-ce une lecture, une émulation ou une véritable compromission ?
9. Quelle protection empêcherait cette attaque ?
10. **Qu'est-ce qui a réellement été démontré ?**

---

## 10. Phrase prête à dire

> « Le Flipper Zero n'est pas une baguette magique. Il permet surtout d'expérimenter plusieurs technologies — radio, RFID, NFC, infrarouge, USB et électronique. La vraie question de sécurité est de savoir comment le système authentifie ce qu'il reçoit et s'il résiste à la copie ou au rejeu. »

## 11. Règle de sécurité

Toutes les expérimentations doivent être réalisées sur du matériel possédé, explicitement autorisé ou placé dans un laboratoire isolé.

## Sources

- Documentation officielle Flipper Zero : https://docs.flipper.net/zero
- NFC : https://docs.flipper.net/zero/nfc
- RFID 125 kHz : https://docs.flipper.net/zero/rfid
- Infrarouge : https://docs.flipper.net/zero/infrared
- Spécifications matérielles : https://docs.flipper.net/zero/development/hardware/tech-specs
