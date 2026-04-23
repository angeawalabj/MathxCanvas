# Jour 23 — Timeline Scrub

> *Glisse de gauche à droite — une fleur éclot sous tes doigts.*

---

## 👁️ Ce que tu vois

Un canvas circulaire. Déplace ta souris horizontalement : une fleur s'ouvre progressivement, ses pétales s'écartent, leurs couleurs évoluent du violet à l'orange. Tu contrôles le temps — tu peux avancer, reculer, t'arrêter à mi-chemin.

---

## 📐 Le concept mathématique

**L'interpolation linéaire — relier deux états par un paramètre t.**

```javascript
// t (progress) va de 0 à 1 selon la position X de la souris
progress = mouseX / screenWidth

// Tous les paramètres évoluent linéairement avec t :
const distance = t * 200         // La fleur s'ouvre
const size = Math.sin(t * π) * 50 // Les pétales grandissent puis rétrécissent
const hue = 280 + (t * 100)      // La couleur évolue
```

`Math.sin(t * π)` crée une courbe qui monte de 0 à 1 puis redescend — parfaite pour un "gonflement" puis un "rétrécissement" des pétales.

---

## 🎨 Le principe UX

**Contrôle du temps = sentiment de pouvoir.**

Les interfaces qui permettent à l'utilisateur de *contrôler la progression* d'une animation créent un sentiment fort d'agentivité. Apple l'utilise massivement dans ses pages de présentation de produits — le scroll déclenche les animations.

> *Règle UX : Laisser l'utilisateur contrôler une animation la rend plus mémorable.*

---

## 🌍 Dans la vraie vie

- **Apple.com** — scroll storytelling (iPhone se démonte sous tes yeux)
- **Stripe** — animations de produit déclenchées par le scroll
- **Timeline interactives** — journalisme interactif (NYT, The Pudding)
- **Onboarding slidable** — tutoriels contrôlés par le swipe

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de pétales — 20 (fleur simple) ou 200 (mandala)
const petals = 80

// Taille maximale des pétales
const size = Math.sin(p * Math.PI) * 50  // * 20 (petit) ou * 100 (grand)

// Étendue de la couleur — 100 (petite gamme) ou 360 (arc-en-ciel complet)
const hue = 280 + (p * 100)

// Distance d'ouverture
const distance = p * 200  // * 100 (compact) ou * 400 (très ouvert)
```

---

*MathxCanvas · Jour 23/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
