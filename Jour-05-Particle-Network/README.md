# Jour 05 — Particle Network

> *Des points qui se connectent — quand la proximité crée du lien.*

---

## 👁️ Ce que tu vois

Des centaines de particules violettes flottent et rebondissent. Quand deux particules sont proches, une ligne les relie — plus elles sont proches, plus la ligne est visible. Ta souris repousse les particules à son passage, brisant et recréant les connexions.

---

## 📐 Le concept mathématique

**Le seuil de connexion — distance comme critère de relation.**

```javascript
// Pour chaque paire de particules :
let distance = Math.sqrt(dx*dx + dy*dy)

if (distance < maxDistance) {
  // Opacité proportionnelle à la proximité
  opacity = 1 - (distance / 150)
  // Plus c'est proche → plus c'est visible
}
```

**Complexité algorithmique O(n²) :**
```
Pour 200 particules → 200 × 200 = 40 000 comparaisons par frame
C'est pourquoi le nombre de particules doit rester raisonnable
```

---

## 🎨 Le principe UX

**Le réseau visualisé — la proximité crée du lien.**

Ce principe visuel est une métaphore puissante : les éléments proches sont perçus comme *liés* (loi de proximité de la Gestalt). Les interfaces de réseaux sociaux, de knowledge graphs, et de data visualization exploitent exactement cette perception.

> *Règle UX : La proximité spatiale implique une relation logique.*

---

## 🌍 Dans la vraie vie

- **Visualisation de réseaux sociaux** — LinkedIn, graphes de connexions
- **Knowledge graphs** — Google Knowledge Panel, Obsidian
- **Interfaces de cybersécurité** — cartes de menaces en temps réel
- **Présentations de données** — relations entre entités dans les dashboards

---

## 🎛️ Valeurs à modifier

```javascript
// Distance de connexion — essaie 80 (réseau clairsemé) ou 200 (dense)
if (distance < (canvas.width/7) * (canvas.height/7))

// Changer la couleur du réseau — essaie du cyan :
ctx.strokeStyle = `rgba(0, 242, 255, ${opacityValue})`

// Nombre de particules — la densité change l'ambiance
let numberOfParticles = (canvas.height * canvas.width) / 9000
// Divise par 5000 pour plus dense, 15000 pour épars

// Rayon de répulsion souris
const mouse = { radius: 150 }  // essaie 50 ou 300
```

---

*MathxCanvas · Jour 05/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
