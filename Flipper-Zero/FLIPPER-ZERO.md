# Flipper Zero — Fiche Live

## 1. Qu'est-ce que c'est ?

Le **Flipper Zero** est un appareil portable conçu pour l'expérimentation électronique, radio et numérique.

Il peut interagir avec certaines technologies de communication à courte portée, certains signaux radio et certains appareils.

Mais il ne faut pas le présenter comme une « clé universelle de piratage ».

## 2. Mythes et rumeurs à déconstruire

### « Le Flipper Zero peut ouvrir toutes les voitures »

**Faux.** Les systèmes automobiles modernes utilisent des mécanismes de sécurité variés. Le résultat dépend de la technologie, du protocole, de l'authentification et parfois de codes dynamiques.

### « Le Flipper peut cloner n'importe quel badge »

**Faux.** Certains systèmes RFID ou NFC sont simples à reproduire ; d'autres utilisent une authentification et/ou un chiffrement qui empêchent une simple copie.

### « Le Flipper peut voler n'importe quelle carte bancaire »

**Faux.** Lire certaines informations radio ne signifie pas pouvoir reproduire une transaction bancaire valide.

### « Il suffit de capter un signal une fois pour pouvoir le réutiliser »

**Pas toujours.** Certains systèmes utilisent des mécanismes où le code ou la valeur change au fil des utilisations. C'est notamment la différence entre un signal simple que l'on peut apprendre et un système utilisant des mécanismes anti-rejeu (**anti-replay**).

### « Le Flipper peut pirater un téléphone juste en passant à côté »

**Faux.** La proximité radio ne donne pas automatiquement un accès au téléphone.

### « Le Flipper fait tout ce que font les hackers »

**Faux.** C'est un outil spécialisé d'expérimentation. Un professionnel utilise également des ordinateurs, des systèmes d'analyse, des outils réseau et des environnements de test.

### « Si le Flipper réussit une démonstration, le système est forcément totalement compromis »

**Faux.** Une démonstration peut montrer une faiblesse précise sans signifier que tout le système est compromis.

Il faut demander : **qu'est-ce qui a réellement été démontré ?**

## 3. NFC

**NFC (Near Field Communication, communication en champ proche)** permet à des appareils proches d'échanger certaines informations.

Il faut distinguer **lecture**, communication et **émulation** (faire apparaître l'appareil comme un dispositif compatible).

## 4. RFID

**RFID (Radio-Frequency Identification, identification par radiofréquence)** permet d'identifier certains objets ou badges grâce aux ondes radio.

Le **RFID 125 kHz** correspond à une famille de technologies basse fréquence.

Tous les badges RFID ne sont pas équivalents : certains sont très simples, d'autres utilisent des mécanismes de sécurité plus avancés.

## 5. Sub-GHz

**Sub-GHz** signifie « sous 1 GHz ». Il s'agit de certaines communications radio utilisant des fréquences inférieures à 1 gigahertz.

La fréquence seule ne suffit pas à comprendre la sécurité.

## 6. Infrarouge

Le signal **IR (infrarouge)** est utilisé par de nombreuses télécommandes.

Une télécommande envoie une séquence lumineuse invisible à l'œil humain que le récepteur interprète.

## 7. GPIO

**GPIO (General-Purpose Input/Output)** désigne des broches électroniques permettant d'interagir avec des composants externes.

## 8. BadUSB

**BadUSB** désigne notamment l'utilisation d'un périphérique USB qui se présente à l'ordinateur comme un autre type de périphérique, par exemple un clavier.

Le point de sécurité est la **confiance accordée aux périphériques physiques**.

## 9. Le vrai sujet : protocole et authentification

Deux appareils utilisant la même famille de technologie peuvent avoir des niveaux de sécurité très différents.

Il faut donc demander :

- Quel protocole ?
- Authentification ?
- Chiffrement ?
- Code statique ou dynamique ?
- Lecture, émission ou émulation ?
- Quelle limite ?

**Authentification** = vérifier qu'un appareil ou utilisateur est autorisé.

**Chiffrement** = rendre les données illisibles sans la bonne clé.

## 10. Questions à poser

1. Quelle technologie utilise-t-on ?
2. Est-ce une lecture, une transmission ou une émulation ?
3. Quel protocole est utilisé ?
4. Y a-t-il une authentification ?
5. Les données sont-elles chiffrées ?
6. Le résultat fonctionnerait-il sur un système moderne correctement sécurisé ?
7. Qu'est-ce qui a réellement été démontré ?
8. Quelle est la limite de la démonstration ?

## Phrase prête à dire

> « Le Flipper n'est pas une baguette magique. Ce qu'il peut faire dépend surtout de la technologie ciblée et des mécanismes de sécurité utilisés. Une démonstration réussie montre une capacité précise, pas nécessairement une compromission complète du système. »

Utilisation uniquement sur des systèmes, appareils et signaux autorisés.
