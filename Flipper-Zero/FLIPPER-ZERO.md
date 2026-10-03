# Flipper Zero — Fiche Live

## 1. Qu'est-ce que c'est ?

Le **Flipper Zero** est un appareil portable conçu pour l'expérimentation électronique, radio et numérique.

Il peut interagir avec certaines technologies de communication à courte portée, certains signaux radio et certains appareils.

Mais il ne faut pas le présenter comme une **« clé universelle de piratage »**.

## 2. Mythes et rumeurs

### « Le Flipper Zero peut ouvrir toutes les voitures »

**Faux.** Les systèmes automobiles utilisent des mécanismes de sécurité variés. Le résultat dépend de la technologie, du protocole, de l'authentification et parfois de codes dynamiques.

### « Le Flipper peut cloner n'importe quel badge »

**Faux.** Certains systèmes RFID ou NFC sont simples à reproduire ; d'autres utilisent une authentification et/ou un chiffrement.

### « Le Flipper peut voler n'importe quelle carte bancaire »

**Faux.** Lire certaines informations radio ne signifie pas pouvoir reproduire une transaction bancaire valide.

### « Il suffit de capter un signal une fois pour pouvoir le réutiliser »

**Pas toujours.** Certains systèmes utilisent des mécanismes où le code ou la valeur change au fil des utilisations. C'est notamment le cas des systèmes conçus contre le rejeu (**anti-replay**).

### « Le Flipper peut pirater un téléphone juste en passant à côté »

**Faux.** La proximité radio ne donne pas automatiquement un accès au téléphone.

### « Si le Flipper réussit une démonstration, le système est forcément totalement compromis »

**Faux.** Une démonstration peut montrer une faiblesse précise sans signifier que tout le système est compromis.

La question clé :

> **« Qu'est-ce qui a réellement été démontré ? »**

## 3. Comprendre les fonctions

### NFC

**NFC (Near Field Communication)** permet à des appareils proches d'échanger certaines informations.

À distinguer : **lecture**, communication et **émulation**.

### RFID

**RFID (Radio-Frequency Identification)** permet d'identifier certains objets ou badges grâce aux ondes radio.

Le **RFID 125 kHz** correspond à une famille de technologies basse fréquence. Tous les badges RFID ne sont pas équivalents.

### Sub-GHz

**Sub-GHz** signifie « sous 1 GHz ». Il s'agit de certaines communications radio utilisant des fréquences inférieures à 1 gigahertz.

La fréquence seule ne permet pas de déterminer la sécurité.

### Infrarouge

L'**IR (infrarouge)** est utilisé par de nombreuses télécommandes.

### GPIO

**GPIO (General-Purpose Input/Output)** désigne des broches permettant d'interagir avec des composants électroniques externes.

### BadUSB

**BadUSB** désigne notamment l'utilisation d'un périphérique USB qui se présente à l'ordinateur comme un autre type de périphérique, par exemple un clavier.

Le point de sécurité est la **confiance accordée aux périphériques physiques**.

## 4. La grille d'analyse pendant le live

Pour chaque démonstration, demander :

- Quelle technologie ?
- Quel protocole ?
- Authentification ?
- Chiffrement ?
- Code statique ou dynamique ?
- Lecture, émission ou émulation ?
- Accès physique nécessaire ?
- Quelle limite ?

**Authentification** = vérifier qu'un appareil ou utilisateur est autorisé.

**Chiffrement** = rendre les données illisibles sans la bonne clé.

## 5. Questions à poser

1. Quelle technologie utilise-t-on ?
2. Est-ce une lecture, une transmission ou une émulation ?
3. Quel protocole est utilisé ?
4. Y a-t-il une authentification ?
5. Les données sont-elles chiffrées ?
6. Le résultat fonctionnerait-il sur un système moderne correctement sécurisé ?
7. Quelle condition rend la démonstration possible ?
8. **Qu'est-ce qui a réellement été démontré ?**

## Phrase prête à dire

> « Le Flipper Zero est un outil d'expérimentation. Ses capacités dépendent énormément de la technologie ciblée et de ses mécanismes de sécurité. Une démonstration réussie montre une capacité précise, pas nécessairement une compromission complète du système. »

Utilisation uniquement sur des systèmes, appareils et signaux autorisés.
