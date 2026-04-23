# Jour 20 — Interactive Snow

> *300 flocons tombent — et ta souris crée le vent.*

---

## 👁️ Ce que tu vois

Des flocons tombent doucement sur fond bleu nuit. Approche ta souris : les flocons proches sont repoussés sur le côté, comme si ta main créait un courant d'air. Éloigne-toi : ils reprennent leur chute naturelle.

---

## 📐 Le concept mathématique

**Le champ de force radial avec oscillation naturelle.**

```javascript
// Chute constante
this.y += this.speedY    // Vitesse verticale de base
this.x += this.speedX    // Oscillation horizontale naturelle

// Vent de la souris
let dx = mouse.x - this.x
let dy = mouse.y - this.y
let distance = Math.sqrt(dx*dx + dy*dy)

if (distance < mouse.radius) {
  let force = (mouse.radius - distance) / mouse.radius
  // Pousse sur le côté (pas vers le haut ni le bas)
  this.x -= (dx / distance) * force * 5
}
```

Chaque flocon a sa propre vitesse — la simulation paraît naturelle parce qu'elle est *irrégulière*.

---

## 🎨 Le principe UX

**Environnement réactif — présence dans l'espace.**

Un fond qui réagit à la présence de l'utilisateur transforme une page statique en espace habité. L'utilisateur a le sentiment d'*être dans* l'interface plutôt que de la *regarder*. C'est le principe des "living backgrounds".

> *Règle UX : Un environnement réactif crée le sentiment de présence.*

---

## 🌍 Dans la vraie vie

- **Sites saisonniers** — effets météo sur les pages de vœux ou d'événements
- **Jeux vidéo** — systèmes météo dynamiques (The Legend of Zelda: BotW)
- **Apps de méditation** — Calm, Headspace avec fonds animés réactifs
- **Fond d'écran vivants** — Wallpaper Engine, macOS Sonoma

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de flocons — 100 (légère neige) ou 600 (blizzard)
for (let i = 0; i < 300; i++)

// Vitesse de chute — essaie 0.2 (quasi immobile) ou 3 (pluie)
this.speedY = Math.random() * 1 + 0.5

// Rayon d'influence souris
const mouse = { radius: 150 }  // 50 (discret) ou 300 (vent fort)

// Intensité de la déviation — 1 (légère brise) ou 15 (tempête)
this.x -= (dx / distance) * force * 5
```

---

*MathxCanvas · Jour 20/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
