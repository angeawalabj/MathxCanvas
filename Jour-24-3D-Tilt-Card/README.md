# Jour 24 — 3D Tilt Card

> *Une carte qui se penche vers ta souris — et un reflet qui suit la lumière.*

---

## 👁️ Ce que tu vois

Une carte noire au centre. Approche ta souris : la carte s'incline en 3D vers ta position — comme si tu la tenais dans la main et la tournais. Un reflet lumineux suit la souris sur la surface. Le texte "3D" sort visuellement de la carte.

---

## 📐 Le concept mathématique

**La projection 3D sur plan 2D — rotations X et Y.**

```javascript
const rect = card.getBoundingClientRect()

// Position relative au centre de la carte (de -1 à +1)
const x = mouseX - rect.left
const y = mouseY - rect.top
const centerX = rect.width / 2
const centerY = rect.height / 2

// Angle de rotation (entre -20° et +20°)
const rotateX = (centerY - y) / 10  // Souris en bas → incline vers l'avant
const rotateY = (x - centerX) / 10  // Souris à droite → incline à droite

card.style.transform = `rotateX(${rotateX}deg) rotateY(${rotateY}deg)`
```

`perspective: 1000px` sur le parent CSS est indispensable — c'est lui qui crée la distorsion 3D.

---

## 🎨 Le principe UX

**Tilt = profondeur perçue — la matérialité de l'objet.**

Une carte qui se penche semble avoir du poids, une surface, une épaisseur. Elle cesse d'être un rectangle plat pour devenir un *objet*. Ce principe transforme n'importe quel élément d'interface en quelque chose de tangible.

> *Règle UX : La simulation de matérialité crée de la valeur perçue.*

---

## 🌍 Dans la vraie vie

- **Cartes Pokémon numériques** — l'effet holographique qui suit la lumière
- **E-commerce premium** — cartes produit avec tilt sur les sites de luxe
- **Portfolios de designers** — cartes de projet avec effet 3D
- **Apple Wallet** — les cartes bancaires avec effet de profondeur

---

## 🎛️ Valeurs à modifier

```javascript
// Intensité du tilt — essaie 5 (subtil) ou 20 (exagéré)
const rotateX = (centerY - y) / 10

// Profondeur du texte en Z
// Dans CSS : transform: translateZ(50px)  → essaie 100px ou 20px

// Couleur du reflet
// Dans CSS : radial-gradient(circle ... rgba(255,255,255,0.15) ...)
// essaie rgba(100, 200, 255, 0.3) pour un reflet bleuté
```

---

*MathxCanvas · Jour 24/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
