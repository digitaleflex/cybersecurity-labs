# LOIC — Fiche Live

## À retenir

**LOIC** signifie *Low Orbit Ion Cannon*. C'est un outil historique de génération de trafic/stress réseau, notamment associé à des campagnes de DoS.

### DoS vs DDoS

- **DoS** : déni de service depuis une ou plusieurs ressources contrôlées par une même source.
- **DDoS** : déni de service utilisant de nombreuses sources.

L'objectif est la **disponibilité** : ralentir ou rendre inaccessible un service.

### Ce qu'il faut observer

Trafic anormal
→ sollicitation des ressources
→ saturation possible
→ dégradation
→ indisponibilité.

Les ressources concernées peuvent être la bande passante, les connexions, le CPU, la mémoire ou les ressources applicatives.

### Défense

- Monitoring et détection d'anomalies
- Rate limiting
- Limites de connexions
- Firewall / WAF
- Load balancing
- CDN et protection DDoS
- Plan de réponse à incident

### Limite importante

LOIC est surtout utile pour comprendre historiquement le principe d'une génération de trafic. Il ne représente pas à lui seul les techniques DDoS modernes.

## 5 questions à poser à l'expert

1. Qu'est-ce qu'on est en train de voir ?
2. Quel mécanisme technique provoque cela ?
3. Quelle ressource est actuellement sollicitée ?
4. Comment un administrateur détecterait cette activité ?
5. Comment protéger une infrastructure réelle contre ce scénario ?

## Phrase de transition

> Une attaque par déni de service ne cherche pas nécessairement à entrer dans le système ; elle cherche à empêcher les utilisateurs légitimes d'utiliser normalement une ressource. La défense consiste donc à détecter l'anomalie, filtrer ou absorber le trafic et maintenir le service disponible.

**Lab : uniquement sur des systèmes autorisés et isolés.**
