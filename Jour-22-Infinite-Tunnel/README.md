# Jour 22 — Infinite Tunnel

> *Un tunnel sans fond — la perspective mathématique crée l'illusion de profondeur.*

---

## 👁️ Ce que tu vois

Cinquante cercles colorés s'agrandissent continûment, donnant l'impression de foncer dans un tunnel à grande vitesse. Déplace ta souris : le tunnel se courbe vers ta direction — comme si tu changeais de trajectoire.

---

## 📐 Le concept mathématique

**La perspective linéaire — l'échelle comme profondeur.**

```javascript
// Plus le cercle est grand → plus il est "proche" → plus il suit la souris
const perspectiveScale = this.size / 200

// Position décalée selon la perspective
this.drawX = centerX + (mouse.x - centerX) * perspectiveScale
this.drawY = centerY + (mouse.y - centerY) * perspectiveScale
```

Un cercle petit (loin) est presque centré. Un cercle grand (proche) suit fortement la souris. C'est exactement comment fonctionne la parallaxe dans la vraie vie — les objets proches bougent plus que les objets lointains.

---

## 🎨 Le principe UX

**Profondeur = immersion — le sentiment d'espace infini.**

La troisième dimension simulée sur un écran 2D crée un sentiment d'espace qui dépasse les limites physiques de l'écran. Les interfaces qui utilisent la profondeur perçue semblent plus grandes, plus riches, plus immersives.

> *Règle UX : La profondeur simulée agrandit perceptuellement l'espace de l'interface.*

---

## 🌍 Dans la vraie vie

- **Intros de jeux vidéo** — effets de warp speed, hyperdrive (Star Wars)
- **Transitions de sites** — portails entre sections d'un site
- **WebGL / Three.js** — effets de tunnel dans les expériences 3D web
- **Économiseurs d'écran** — le classique tunnel de Windows

---

## 🎛️ Valeurs à modifier

```javascript
// Vitesse d'expansion — essaie 2 (lent) ou 10 (très rapide)
this.size += 5

// Nombre de cercles — 20 (espacé) ou 100 (dense)
for (let i = 0; i < 50; i++)

// Intensité de la déviation par la souris
const perspectiveScale = this.size / 200  // /50 (très réactif) ou /500 (subtil)

// Couleurs des cercles — pour un tunnel monochrome :
this.color = `hsl(200, 100%, 50%)`  // Fixe au lieu de random
```

---

*MathxCanvas · Jour 22/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
