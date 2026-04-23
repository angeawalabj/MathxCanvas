# Jour 11 — Gravity Bounce

> *Des balles qui rebondissent, fuient ta souris — et ont du poids.*

---

## 👁️ Ce que tu vois

Cinquante balles colorées rebondissent contre les murs. Ta souris les repousse dans un rayon de 200px. Chaque balle a un rayon différent — ce qui lui donne une personnalité propre. Une légère traînée montre leurs trajectoires.

---

## 📐 Le concept mathématique

**La loi de gravitation simplifiée appliquée à la répulsion.**

```javascript
let force = (200 - distance) / 200  // Entre 0 et 1

// Direction normalisée vers la souris
let dirX = dx / distance
let dirY = dy / distance

// Répulsion : on retire de la vitesse dans la direction de la souris
this.vx -= dirX * force * 1.5
this.vy -= dirY * force * 1.5

// Friction pour éviter l'accélération infinie
this.vx *= 0.99
this.vy *= 0.99
```

---

## 🎨 Le principe UX

**Poids = importance — les objets ont un sens physique.**

Les interfaces avec des objets qui ont du "poids" (résistance, inertie, rebond) semblent plus réelles. Le cerveau associe automatiquement la masse à l'importance. Un élément lourd est perçu comme plus sérieux, plus significatif.

> *Règle UX : L'inertie physique simulée rend une interface plus crédible.*

---

## 🌍 Dans la vraie vie

- **iOS** — les icônes qui rebondissent lors d'un dépôt
- **Jeux physiques** — Angry Birds, tout repose sur cette simulation
- **Interfaces de data** — bulles proportionnelles aux données (D3.js force)
- **Animations de chargement** — loaders avec rebond élastique

---

## 🎛️ Valeurs à modifier

```javascript
// Rayon d'influence — essaie 100 (petite zone) ou 400 (tout l'écran)
if (distance < 200)

// Changez la répulsion en ATTRACTION : remplace -= par +=
this.vx += dirX * force * 1.5

// Friction — 0.999 (glisse longtemps) ou 0.95 (freine vite)
this.vx *= 0.99

// Nombre de balles
for (let i = 0; i < 50; i++)
```

---

*MathxCanvas · Jour 11/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
