# Jour 29 — Interactive Cloth

> *Un tissu numérique — qui se déforme sous ta souris et revient à sa forme.*

---

## 👁️ Ce que tu vois

Une grille de lignes cyan remplit l'écran comme un tissu tendu. Déplace ta souris : les fils proches sont repoussés. Clique et déplace : ils sont attirés. Relâche : le tissu reprend sa forme originale élastiquement.

---

## 📐 Le concept mathématique

**L'intégration de Verlet — simuler la physique sans accélération explicite.**

```javascript
// La vitesse est implicite : c'est la différence entre position actuelle et ancienne
let vx = (this.x - this.oldX) * friction
let vy = (this.y - this.oldY) * friction

this.oldX = this.x
this.oldY = this.y

this.x += vx  // La position précédente contient toute l'histoire du mouvement
this.y += vy
```

Verlet est élégant : pas besoin de stocker la vitesse séparément. Elle est *implicite* dans la différence de position. C'est l'algorithme utilisé dans les moteurs physiques professionnels (Havok, Bullet).

---

## 🎨 Le principe UX

**Résistance physique = réalisme — la matérialité du tissu.**

Une interface qui se déforme et revient élastiquement à sa forme crée une sensation de *matérialité*. L'utilisateur a l'impression de toucher quelque chose de physique. iOS utilise ce principe pour les rebonds aux limites du scroll.

> *Règle UX : La résistance élastique simule la matière et ancre l'interface dans le réel.*

---

## 🌍 Dans la vraie vie

- **Moteurs de jeux** — Havok, Bullet, simulation de vêtements (cloth simulation)
- **Animation 3D** — simulation de rideaux, drapeaux, cheveux dans Blender
- **iOS/Android** — le rebond élastique aux limites du scroll
- **Mode numérique** — simulation textile pour la conception vestimentaire

---

## 🎛️ Valeurs à modifier

```javascript
// Espacement de la grille — 15 (dense) ou 50 (espacé)
const spacing = 30

// Friction — 0.98 (glisse longtemps) ou 0.80 (freine vite)
const friction = 0.95

// Rappel élastique — 0.02 (mou) ou 0.2 (rigide)
this.x += (this.originalX - this.x) * 0.05

// Rayon de la souris
const mouse = { radius: 100 }  // 50 (fin) ou 200 (large déformation)
```

---

*MathxCanvas · Jour 29/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
