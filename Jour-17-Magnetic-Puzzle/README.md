# Jour 17 — Magnetic Puzzle

> *Une image éparpillée — ta souris l'assemble par attraction.*

---

## 👁️ Ce que tu vois

Les morceaux d'une image sont éparpillés aléatoirement sur l'écran. Approche ta souris de la zone : les morceaux proches sont attirés vers leur position finale dans l'image. Éloigne-toi : ils dérivent à nouveau. La souris est un aimant.

---

## 📐 Le concept mathématique

**L'attraction vectorielle pondérée — force vers une cible.**

```javascript
let dx = mouse.x - this.x
let dy = mouse.y - this.y
let distance = Math.sqrt(dx*dx + dy*dy)

if (distance < mouse.radius) {
  let force = (mouse.radius - distance) / mouse.radius

  // Accélération VERS la position cible (pas vers la souris)
  this.vx += (this.targetX - this.x) * force * 0.2
  this.vy += (this.targetY - this.y) * force * 0.2
} else {
  // Friction quand pas d'interaction
  this.vx *= 0.95
  this.vy *= 0.95
}
```

La souris n'attire pas les pièces vers elle — elle les *autorise* à aller vers leur cible.

---

## 🎨 Le principe UX

**Proximité → assemblage — le drive de complétion.**

Le cerveau humain ressent un inconfort devant l'incomplet (effet Zeigarnik). Une interface qui assemble visuellement sous l'action de l'utilisateur exploite ce drive naturel de completion. C'est addictif parce que ça résout un inconfort.

> *Règle UX : L'incomplet engage plus que le complet.*

---

## 🌍 Dans la vraie vie

- **Drag & drop** — interfaces de glisser-déposer avec snap to grid
- **Assemblage de données** — visualisations qui se construisent à l'interaction
- **Onboarding progressif** — éléments UI qui se mettent en place
- **Jeux de puzzle** — mécaniques d'assemblage par proximité

---

## 🎛️ Valeurs à modifier

```javascript
// Rayon magnétique — essaie 80 (précis) ou 300 (tout l'écran)
const mouse = { radius: 150 }

// Vitesse d'assemblage — essaie 0.05 (lent) ou 0.5 (snap immédiat)
this.vx += (this.targetX - this.x) * force * 0.2

// Friction — 0.99 (glisse) ou 0.80 (freine fort)
this.vx *= 0.95

// Taille des morceaux — essaie 10 (mosaïque) ou 60 (gros blocs)
const size = 30;
```

---

*MathxCanvas · Jour 17/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
