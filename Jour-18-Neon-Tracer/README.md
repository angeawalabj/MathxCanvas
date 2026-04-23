# Jour 18 — Neon Tracer

> *Dessine vite : le trait s'affine. Dessine lentement : il s'épaissit.*

---

## 👁️ Ce que tu vois

Déplace ta souris pour tracer des lignes néon bleu électrique. La particularité : plus tu bouges vite, plus le trait est fin. Plus tu es lent et précis, plus il est épais. Comme un vrai crayon ou un pinceau.

---

## 📐 Le concept mathématique

**La vitesse instantanée — distance parcourue entre deux frames.**

```javascript
// À chaque mouvement de souris :
const dx = currentX - lastX  // Déplacement en X depuis le dernier point
const dy = currentY - lastY  // Déplacement en Y

// La vitesse = distance parcourue en un intervalle de temps
speed = Math.sqrt(dx*dx + dy*dy)

// L'épaisseur est inversement proportionnelle à la vitesse
const width = Math.max(2, 25 - velocity)
// Rapide (vel=20) → width = 5 (fin)
// Lent  (vel=2)  → width = 23 (épais)
```

---

## 🎨 Le principe UX

**Vitesse perçue = expressivité — l'interface comprend l'intention.**

Un trait épais = lent = délibéré = important. Un trait fin = rapide = fluide = léger. L'outil comprend *comment* tu dessines, pas seulement *où*. C'est la différence entre un outil passif et un outil expressif.

> *Règle UX : Lire la vélocité d'une interaction révèle son intention.*

---

## 🌍 Dans la vraie vie

- **Apple Pencil** — la pression et la vitesse changent l'épaisseur du trait
- **Signature digitale** — les apps de signature lisent la vitesse pour authentifier
- **Calligraphie numérique** — Procreate, Adobe Fresco
- **Reconnaissance gestuelle** — les gestes rapides vs lents signifient des choses différentes

---

## 🎛️ Valeurs à modifier

```javascript
// Formule d'épaisseur — inverse la relation (rapide = épais) :
const width = Math.min(20, velocity * 0.5)

// Couleur du néon — essaie du rose :
ctx.shadowColor = '#ff00aa'
ctx.strokeStyle = '#fff'

// Intensité du halo
ctx.shadowBlur = 15  // 5 (discret) ou 40 (très lumineux)

// Vitesse de fondu — 0.02 (trace longue) ou 0.4 (disparaît vite)
ctx.fillStyle = 'rgba(0, 0, 0, 0.1)'
```

---

*MathxCanvas · Jour 18/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
