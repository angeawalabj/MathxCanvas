# Jour 07 — Confetti Explosion

> *Clique n'importe où — et regarde les maths de Newton en action.*

---

## 👁️ Ce que tu vois

Un clic crée une explosion de 50 confettis multicolores. Ils jaillissent dans toutes les directions, ralentissent, retombent sous l'effet de la gravité, et disparaissent en bas de l'écran. Chaque confetti tourne sur lui-même pendant sa chute.

---

## 📐 Le concept mathématique

**La gravité et la friction — les deux forces fondamentales de la simulation.**

```javascript
const gravity = 0.5   // Accélération vers le bas (px/frame²)
const friction = 0.98 // Ralentissement de l'air (multiplicateur)

// Chaque frame :
velocityY += gravity      // La gravité accélère la chute
velocityX *= friction     // L'air freine le mouvement horizontal
velocityY *= friction     // L'air freine aussi la chute

x += velocityX
y += velocityY
```

**L'explosion initiale :**
```javascript
this.velocityX = (Math.random() - 0.5) * 15  // Entre -7.5 et +7.5
this.velocityY = (Math.random() - 0.5) * 15 - 10  // Pousse vers le HAUT
```

---

## 🎨 Le principe UX

**Célébration = émotion — récompense visuelle.**

Les animations de récompense sont l'une des techniques les plus puissantes pour créer une réponse émotionnelle positive. Stripe, Duolingo, et des centaines d'applications utilisent exactement ce pattern pour féliciter une action accomplie.

> *Règle UX : La récompense visuelle crée l'envie de recommencer.*

---

## 🌍 Dans la vraie vie

- **Stripe** — animation de confettis à la première transaction réussie
- **Duolingo** — explosion de particules après une leçon complétée
- **App Store** — animation lors d'un achat validé
- **LinkedIn** — réaction confettis sur les anniversaires de poste

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de confettis par clic — essaie 10 (discret) ou 200 (chaos)
for(let i = 0; i < 50; i++)

// Force de la gravité — essaie 0.1 (lune) ou 2.0 (Jupiter)
const gravity = 0.5;

// Friction de l'air — essaie 0.99 (presque sans air) ou 0.90 (très résistant)
const friction = 0.98;

// Force d'explosion — essaie 5 (faible) ou 25 (violent)
this.velocityX = (Math.random() - 0.5) * 15;
```

---

*MathxCanvas · Jour 07/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
