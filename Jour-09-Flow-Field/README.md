# Jour 09 — Flow Field

> *1000 particules qui suivent un vent invisible — créé par deux fonctions trigonométriques.*

---

## 👁️ Ce que tu vois

Mille particules bleues dérivent sur l'écran, chacune suivant un "vent" invisible mais cohérent. Des courants se forment, des tourbillons apparaissent. Approche ta souris : elle crée un vortex qui dévie tous les flux environnants.

---

## 📐 Le concept mathématique

**Le champ vectoriel — une direction différente en chaque point de l'espace.**

```javascript
// En chaque point (x, y), l'angle est défini par :
let angle = (Math.cos(x * 0.01) + Math.sin(y * 0.01)) * 2

// Le déplacement de chaque particule :
particle.x += Math.cos(angle) * speed
particle.y += Math.sin(angle) * speed
```

`cos` et `sin` oscillent entre -1 et +1. Combinés avec des coordonnées spatiales, ils créent un champ cohérent où chaque point a une direction qui varie *progressivement* — créant des flux naturels.

**Le tourbillon de souris :**
```javascript
if (dist < 100) angle += 1.5  // Déviation angulaire brusque
```

---

## 🎨 Le principe UX

**Flux naturel — le mouvement suit une logique invisible.**

Les interfaces qui imitent les flux naturels (eau, vent, oiseaux) sont perçues comme plus organiques et moins mécaniques. Le cerveau interprète la cohérence du mouvement comme une *intelligence*.

> *Règle UX : Un mouvement cohérent suggère une intention — même sans en avoir.*

---

## 🌍 Dans la vraie vie

- **Navigation de drones** — algorithmes de pathfinding basés sur des champs vectoriels
- **IA de foules** — simulation de mouvement de personnages dans les jeux
- **Météorologie** — visualisation des vents (earth.nullschool.net)
- **Océanographie** — cartes de courants marins en temps réel

---

## 🎛️ Valeurs à modifier

```javascript
// Échelle du champ — essaie 0.005 (grands tourbillons) ou 0.05 (chaos)
let angle = (Math.cos(x * 0.01) + Math.sin(y * 0.01)) * 2

// Intensité du tourbillon souris — essaie 0.5 (subtil) ou 3.0 (violent)
if (dist < 100) angle += 1.5

// Longueur des traînées — essaie 5 (points) ou 40 (longues traînes)
this.maxLength = Math.floor(Math.random() * 20 + 5)

// Vitesse des particules
this.speed = Math.random() * 2 + 1  // essaie * 4 + 2 pour rapide
```

---

*MathxCanvas · Jour 09/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
