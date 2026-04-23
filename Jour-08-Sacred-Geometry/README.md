# Jour 08 — Sacred Geometry

> *Déplace ta souris et regarde une équation dessiner.*

---

## 👁️ Ce que tu vois

Une forme géométrique symétrique tourne lentement et change selon la position de ta souris. Axe horizontal : la complexité du motif. Axe vertical : son amplitude. Les couleurs cyclent en arc-en-ciel. La forme semble vivante — elle respire.

---

## 📐 Le concept mathématique

**L'équation polaire — décrire une forme par angle et distance.**

```
r = a · sin(k · θ)

où :
  r     = distance depuis le centre (rayon)
  a     = amplitude (taille de la forme) ← contrôlée par mouseY
  k     = complexité (nombre de pétales) ← contrôlée par mouseX
  θ     = angle courant (de 0 à 2π)
```

**Conversion polaire → cartésien :**
```javascript
x = r · cos(θ)
y = r · sin(θ)
```

Quand k = 2 : 2 pétales. k = 3 : 3 pétales. k = 5.5 : motif étoilé complexe. La beauté est dans la simplicité de l'équation.

---

## 🎨 Le principe UX

**Complexité depuis la simplicité — l'émerveillement par la révélation.**

Quand une interface révèle que quelque chose de visuellement riche vient d'une seule ligne d'équation, elle crée un moment de "ahh" — la compréhension soudaine. C'est le principe du *magic moment* en onboarding.

> *Règle UX : Montrer le résultat avant le mécanisme crée plus d'impact.*

---

## 🌍 Dans la vraie vie

- **Logos génératifs** — identités de marque créées algorithmiquement
- **Branding Spotify** — couvertures d'albums génératives
- **Art génératif NFT** — Art Blocks, Fidenza
- **Outils de design** — Figma Plugins génératifs

---

## 🎛️ Valeurs à modifier

```javascript
// Contrôle manuel de la complexité — remplace mouse.x / 50 par une valeur fixe
let k = 3;    // 3 pétales nets
let k = 5.5;  // étoile complexe

// Vitesse de rotation
angle += 0.02;  // Essaie 0.005 (lent/contemplatif) ou 0.1 (rapide)

// Vitesse du cycle de couleurs
ctx.strokeStyle = `hsl(${angle % 360}, 100%, 50%)`
// angle * 2 → cycle plus rapide
```

---

*MathxCanvas · Jour 08/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
