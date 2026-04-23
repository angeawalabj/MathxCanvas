# Jour 12 — Ripple Effect

> *Un clic crée une onde — qui se propage et déplace tout sur son passage.*

---

## 👁️ Ce que tu vois

Clique n'importe où. Une onde circulaire se propage depuis le point de clic, poussant chaque point de la grille sur son passage. Les points reviennent élastiquement à leur position. L'onde traverse tout l'écran puis disparaît.

---

## 📐 Le concept mathématique

**Le front d'onde — une distance qui grandit dans le temps.**

```javascript
// L'onde s'étend à chaque frame
ripple.r += 10

// Un point est "touché" si sa distance au centre est proche de r
let diff = distance - ripple.r

if (diff < 50 && diff > -50) {
  let force = (50 - Math.abs(diff)) / 50  // Force max au centre de l'onde
  point.x += (dx/distance) * force * 20   // Déplacement radial
}
```

L'onde n'est pas un cercle solide — c'est une **bande annulaire** de largeur 100px qui se déplace.

---

## 🎨 Le principe UX

**Action → conséquence différée et spatiale.**

L'onde de ripple est l'une des animations les plus fondamentales du Material Design (Google). Elle communique visuellement que *quelque chose s'est passé ici* et que l'effet se propage. Elle confirme l'action tout en montrant son étendue.

> *Règle UX : La propagation visuelle d'une action rassure et informe.*

---

## 🌍 Dans la vraie vie

- **Material Design (Google)** — les boutons avec ripple effect
- **Android** — chaque tap crée un ripple de confirmation
- **Interfaces tactiles** — feedback visuel du toucher
- **Simulations physiques** — sonar, radar, propagation sismique

---

## 🎛️ Valeurs à modifier

```javascript
// Vitesse de propagation — essaie 3 (lent) ou 20 (explosion rapide)
ripple.r += 10

// Largeur de l'anneau d'onde — essaie 10 (fin) ou 100 (large)
if (diff < 50 && diff > -50)

// Intensité du déplacement — essaie 5 (subtil) ou 50 (violent)
point.x += (dx/distance) * force * 20

// Élasticité du retour — essaie 0.3 (rapide) ou 0.02 (très lent)
this.x += (this.baseX - this.x) * 0.1
```

---

*MathxCanvas · Jour 12/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
