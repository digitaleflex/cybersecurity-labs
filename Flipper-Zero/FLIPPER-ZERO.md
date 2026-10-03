# Flipper Zero — Fiche Live

## 1. Qu'est-ce que c'est ?

Le **Flipper Zero** est un petit appareil portable conçu pour l'expérimentation électronique, radio et numérique.

Il peut interagir avec certaines technologies de communication à courte portée, certains signaux radio et certains appareils.

Le point essentiel est le suivant :

> **Le Flipper Zero n'est pas une « clé magique » capable d'ouvrir ou de pirater n'importe quoi.**

Ses capacités dépendent de la technologie utilisée, du protocole et surtout des mécanismes de sécurité présents.

## 2. NFC

**NFC (Near Field Communication, communication en champ proche)** permet à deux appareils proches d'échanger certaines informations.

Exemple simple : le paiement sans contact ou certains systèmes de cartes.

Analogie : imagine deux appareils qui se parlent uniquement lorsqu'ils sont presque côte à côte.

Pendant une démonstration NFC, il faut distinguer :

- lecture d'informations ;
- communication avec une carte ou un appareil ;
- émulation (faire apparaître l'appareil comme un autre dispositif compatible).

La possibilité de reproduire quelque chose dépend de la technologie et de son authentification.

## 3. RFID

**RFID (Radio-Frequency Identification, identification par radiofréquence)** permet d'identifier certains objets ou badges grâce aux ondes radio.

Le **RFID 125 kHz** correspond notamment à une famille de technologies basse fréquence.

Analogie : c'est comme un badge qui « répond » lorsqu'un lecteur lui parle avec des ondes radio.

Attention : tous les badges RFID ne sont pas équivalents. Certains systèmes sont très simples ; d'autres utilisent des mécanismes d'authentification qui empêchent une simple copie.

## 4. Sub-GHz

**Sub-GHz** signifie « sous 1 GHz » : il s'agit de certaines communications radio utilisant des fréquences inférieures à 1 gigahertz.

On peut rencontrer cette technologie dans certains appareils sans fil, télécommandes ou systèmes IoT.

Analogie : c'est comme une langue radio. Le fait de posséder un microphone ne signifie pas qu'on comprend toutes les langues : il faut connaître le protocole et le système utilisé.

La fréquence seule ne suffit donc pas à déterminer ce qu'un appareil peut faire.

## 5. Infrarouge

Le **signal infrarouge (IR)** est utilisé par de nombreuses télécommandes.

Le principe est relativement simple : la télécommande envoie une séquence lumineuse invisible à l'œil humain et l'appareil la reconnaît.

Analogie : c'est un peu comme envoyer un message avec une lampe que seul le destinataire peut « voir ».

Le Flipper peut apprendre et reproduire certains signaux infrarouges compatibles.

## 6. GPIO

**GPIO (General-Purpose Input/Output)** désigne des broches électroniques permettant à un ordinateur ou microcontrôleur d'interagir avec des composants externes.

Cela permet de faire de l'expérimentation matérielle : capteurs, LED, boutons, circuits, etc.

Analogie : les GPIO sont comme des prises permettant au petit ordinateur de « toucher » le monde physique.

## 7. BadUSB

**BadUSB** désigne une technique où un périphérique USB se présente à l'ordinateur comme un autre type d'appareil, par exemple un clavier.

Pourquoi est-ce intéressant en sécurité ?

Parce qu'un ordinateur fait généralement confiance à un clavier USB pour envoyer des touches.

Analogie : imagine quelqu'un qui entre dans un bâtiment avec un badge parfaitement reconnu par le gardien. Le problème n'est pas forcément le badge lui-même, mais le fait que le système lui fait confiance.

C'est pourquoi la sécurité physique, le contrôle des périphériques USB et les politiques de poste de travail sont importants.

## 8. Le point central : protocole et authentification

Deux appareils peuvent utiliser la même famille de technologie tout en ayant des niveaux de sécurité très différents.

Il faut donc demander :

- Quel protocole est utilisé ?
- Les données sont-elles chiffrées ?
- Y a-t-il une authentification ?
- Le système utilise-t-il des codes qui changent ?
- Est-ce une lecture, une émission ou une émulation ?
- Quelle est la limite de la démonstration ?

**Authentification** = mécanisme permettant de vérifier qu'un appareil ou utilisateur est bien autorisé.

**Chiffrement** = transformation des données pour qu'elles ne soient pas lisibles sans la bonne clé.

Analogie : une serrure simple peut être copiée plus facilement qu'une serrure associée à une clé différente à chaque utilisation.

## 9. Ce qu'il faut observer pendant le live

Ne vous concentrez pas uniquement sur « le Flipper fait quelque chose ».

Essayez de comprendre :

**Technologie → protocole → échange d'information → mécanisme de sécurité → résultat.**

C'est cette chaîne qui explique pourquoi une démonstration fonctionne ou échoue.

## 10. Questions simples à poser à l'expert

1. Quelle technologie sommes-nous en train d'utiliser ?
2. Est-ce une lecture, une transmission ou une émulation ?
3. Quel protocole est utilisé ?
4. Y a-t-il une authentification ?
5. Les données sont-elles chiffrées ?
6. Est-ce que le résultat fonctionnerait sur un système moderne correctement sécurisé ?
7. Quelle est la limite de cette démonstration ?
8. Comment protéger le système concerné ?

## Phrase prête à dire

> « Le plus important ici n'est pas de croire que le Flipper peut tout faire. Il faut regarder la technologie ciblée et surtout les mécanismes de sécurité qui déterminent ce qui est réellement possible. »

Utilisation uniquement sur des systèmes, appareils et signaux autorisés.
