# LOIC — Guide de commentaire LIVE

> Fiche destinée à commenter une démonstration ou une présentation de LOIC sans transformer le live en mode d'emploi d'attaque.
>
> **Cadre :** toute manipulation technique doit rester dans un laboratoire isolé ou sur une infrastructure explicitement autorisée.

## 1. Présentation en 20 secondes

> « LOIC signifie *Low Orbit Ion Cannon*. C'est un outil historique de génération de trafic qui a été utilisé pour des tests de résistance mais qui est surtout connu pour son association avec des attaques DoS/DDoS. L'idée est de comprendre comment un volume de trafic peut perturber la disponibilité d'un service, et surtout comment un défenseur détecte et atténue ce phénomène. »

Cloudflare décrit LOIC comme un outil capable de générer du trafic TCP, UDP ou HTTP et rappelle qu'un seul utilisateur ne suffit généralement pas à produire les volumes associés aux attaques DDoS importantes. citehttps://www.cloudflare.com/fr-fr/learning/ddos/ddos-attack-tools/low-orbit-ion-cannon-loic/

## 2. La grille de lecture à utiliser à l'écran

Toujours commenter dans cet ordre :

**Cible → service/protocole → trafic généré → ressource sollicitée → impact → détection → mitigation → cadre légal**

Important : voir une cible ou un paramètre dans l'interface ne signifie pas que la machine est compromise.

## 3. Ce que LOIC fait réellement

- Il génère du trafic vers une destination choisie.
- Selon le mode et le contexte, ce trafic peut concerner TCP, UDP ou HTTP.
- L'effet recherché dans un scénario DoS/DDoS est une dégradation de la disponibilité.
- Le goulot d'étranglement peut se trouver au niveau du réseau, des connexions, du serveur, de l'application ou d'une dépendance en aval.

### À dire

> « Il faut séparer trois choses : générer du trafic, dégrader un service et compromettre un système. Ce ne sont pas des synonymes. »

## 4. DoS vs DDoS

| Concept | Idée simple |
|---|---|
| DoS | Déni de service provenant d'une source ou d'un nombre limité de sources |
| DDoS | Déni de service distribué entre de nombreuses sources |
| Intrusion | Accès non autorisé à un système |
| Exfiltration | Extraction de données |
| DDoS | Peut perturber un service sans obtenir un accès au système |

### Analogie

> « Une intrusion, c'est essayer d'entrer dans la maison. Un DDoS, c'est bloquer l'entrée avec tellement de monde que les occupants légitimes ne peuvent plus passer. »

## 5. Pourquoi LOIC est historiquement important

LOIC a été popularisé dans plusieurs campagnes hacktivistes. Cloudflare documente notamment son association avec Anonymous, l'utilisation d'IRC pour son mode Hivemind et des campagnes de 2008 et 2010. Ces éléments sont des faits historiques à distinguer de toute attribution d'une action contemporaine. citehttps://www.cloudflare.com/fr-fr/learning/ddos/ddos-attack-tools/low-orbit-ion-cannon-loic/

### Question à poser

> « Est-ce qu'un outil historiquement associé à Anonymous signifie que toute personne qui l'utilise appartient à Anonymous ? »

**Réponse : non.** Un outil ne suffit pas à établir une affiliation ou une attribution.

## 6. Le point juridique à expliquer

### Principe général

> **L'outil n'est pas l'autorisation.**

Un test de charge peut être légitime lorsqu'il est effectué dans un environnement contrôlé ou avec une autorisation explicite. Utiliser volontairement un outil de génération de trafic contre l'infrastructure d'un tiers sans autorisation peut engager la responsabilité de son auteur selon la législation applicable.

Cloudflare indique également que l'utilisation abusive de LOIC hors d'environnements contrôlés peut être illégale et rappelle que des poursuites ont eu lieu dans plusieurs pays. citehttps://developers.cloudflare.com/ddos-protection/frequently-asked-questions/

### 🇧🇯 Exemple : Bénin

Le Code du numérique béninois prévoit notamment des infractions relatives à l'accès non autorisé et aux atteintes au fonctionnement des systèmes informatiques. L'article 507 réprime l'accès ou le maintien intentionnel et sans droit dans tout ou partie d'un système informatique. citehttps://sgg.gouv.bj/doc/loi-2017-20/download

Pour un scénario de déni de service, il faut surtout vérifier la qualification juridique exacte au regard des faits, des dommages, de l'intention et des textes applicables ; ne pas présenter automatiquement toute utilisation de LOIC comme relevant d'un article unique.

### Phrase prête à dire

> « Au Bénin comme ailleurs, la question n'est pas seulement : est-ce que techniquement je peux générer ce trafic ? La question est aussi : ai-je l'autorisation de le faire, sur quelle infrastructure, dans quel cadre et avec quelles conséquences ? »

## 7. Peut-on être identifié ?

Oui, et il ne faut pas présenter LOIC comme un outil d'anonymat. Cloudflare indique que LOIC ne peut pas être utilisé via un proxy dans son fonctionnement documenté et que les adresses IP des utilisateurs peuvent donc être visibles par la cible. citehttps://www.cloudflare.com/fr-fr/learning/ddos/ddos-attack-tools/low-orbit-ion-cannon-loic/

### Question forte

> « Si quelqu'un lance LOIC depuis sa propre connexion, est-ce que son activité est automatiquement anonyme ? »

**Réponse : non.** Il faut distinguer l'identification réseau, l'attribution technique et l'identification judiciaire d'une personne.

## 8. Côté défenseur : que voit-on ?

Observer notamment :

- volume et évolution du trafic ;
- nombre de connexions ;
- répartition des sources ;
- protocoles et services concernés ;
- latence ;
- taux d'erreur ;
- saturation réseau ;
- CPU et mémoire ;
- files d'attente et ressources applicatives ;
- logs et alertes ;
- comportement par rapport à la baseline habituelle.

### Question de transition

> « Si je suis administrateur, quelle métrique me permet de savoir que je suis réellement sous attaque plutôt que simplement face à un pic de trafic légitime ? »

## 9. Défense : expliquer par couches

**Internet → mitigation DDoS/edge → CDN/Anycast → WAF → rate limiting → load balancing → reverse proxy → application → cache/queue → base de données → monitoring**

La bonne protection dépend du goulot d'étranglement. Un WAF est pertinent pour certaines attaques HTTP, tandis qu'une mitigation réseau dédiée est nécessaire pour certains volumes TCP/UDP. Cloudflare décrit cette distinction dans sa documentation de mitigation LOIC/DDoS. citehttps://www.cloudflare.com/fr-fr/learning/ddos/ddos-attack-tools/low-orbit-ion-cannon-loic/

## 10. Questions de secours pour le live

1. « Quelle différence entre DoS et DDoS ? »
2. « LOIC donne-t-il accès au serveur ? »
3. « Quelle ressource est réellement saturée ? »
4. « Pourquoi un serveur puissant peut-il quand même subir un déni de service ? »
5. « Comment distinguer un pic légitime d'une attaque ? »
6. « Pourquoi une protection unique ne suffit-elle pas toujours ? »
7. « Pourquoi LOIC n'est-il pas un outil d'anonymat ? »
8. « Quel est le rôle d'un WAF ? »
9. « Quand faut-il une mitigation DDoS en amont ? »
10. « Est-ce qu'utiliser un outil connu d'Anonymous prouve une affiliation à Anonymous ? »
11. « Où se situe la limite entre test de sécurité et attaque ? »
12. « Qu'est-ce qui a réellement été démontré par cette démo ? »

## 11. Réponses ultra-courtes

**LOIC pirate-t-il un serveur ?**
> Non. Il génère du trafic ; cela ne signifie pas qu'il obtient un accès au système.

**Un seul ordinateur peut-il faire tomber n'importe quel site ?**
> Non. L'effet dépend de la cible, du trafic, de l'architecture et des protections.

**DDoS signifie-t-il qu'un serveur est piraté ?**
> Non. Une attaque peut perturber la disponibilité sans compromettre le système.

**LOIC rend-il anonyme ?**
> Non. Il ne faut pas le présenter comme un outil d'anonymat.

**Est-ce légal ?**
> Un test autorisé peut être légitime ; attaquer l'infrastructure d'un tiers sans autorisation peut avoir des conséquences juridiques.

**Comment se défendre ?**
> Identifier le goulot d'étranglement puis combiner filtrage, rate limiting, WAF/CDN, mitigation DDoS et monitoring selon le scénario.

## 12. Questions qui donnent une posture d'expert

> **« Quelle capacité est démontrée, et quelle capacité ne l'est pas ? »**

> **« Quel est le goulot d'étranglement : réseau, transport, application ou dépendance ? »**

> **« Quelles données permettent de confirmer l'incident plutôt que de simplement l'affirmer ? »**

> **« Quelle mesure de défense agit avant que le trafic atteigne l'origine ? »**

> **« Quelle est la base légale ou l'autorisation qui encadre le test ? »**

## 13. À ne pas dire pendant le live

Éviter :

- « Avec LOIC, tu peux pirater n'importe quel serveur. »
- « Un clic et n'importe quel site tombe. »
- « LOIC rend anonyme. »
- « Utiliser LOIC signifie être Anonymous. »
- « Un DDoS signifie que le serveur a été compromis. »
- « Tester le serveur de quelqu'un sans lui demander est juste un test. »

## 14. Cadre de démonstration

Pour une démonstration technique :

- utiliser uniquement une cible de laboratoire ou une infrastructure explicitement autorisée ;
- privilégier un environnement isolé ;
- mesurer l'effet côté défenseur ;
- arrêter la génération dès que l'objectif pédagogique est atteint ;
- ne pas transformer le live en procédure d'attaque contre une cible réelle.

## 15. Signature du commentaire

> **« En cybersécurité, la vraie question n'est pas seulement : est-ce que je peux le faire ? La question est : est-ce que j'ai le droit de le faire, dans quel environnement, avec quel impact, et comment le défenseur peut-il le détecter et le contenir ? »**
