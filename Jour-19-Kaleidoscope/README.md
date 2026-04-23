# Jour 19 — Kaleidoscope

> *Clique et dessine — ta souris crée 36 copies symétriques simultanément.*

---

## 👁️ Ce que tu vois

Maintiens le clic et déplace ta souris. Chaque point que tu traces est instantanément reproduit 36 fois en symétrie rotative, créant un kaléidoscope en temps réel. Clic droit pour effacer et recommencer.

---

## 📐 Le concept mathématique

**La symétrie rotative — diviser le cercle en parts égales.**

```javascript
const slices = 36

for (let i = 0; i < slices; i++) {
  ctx.rotate((Math.PI * 2) / slices)  // Rotation de 360°/36 = 10° à chaque fois

  // Dessine le point à la position relative au centre
  ctx.arc(x - centerX, y - centerY, 5, 0, Math.PI * 2)

  // Effet miroir dans chaque tranche
  ctx.save()
  ctx.scale(1, -1)  // Retournement vertical
  ctx.arc(x - centerX, y - centerY, 5, 0, Math.PI * 2)
  ctx.restore()
}
```

`2π / n` = l'angle d'une rotation pour n symétries. C'est la base de toute géométrie régulière.

---

## 🎨 Le principe UX

**Symétrie = beauté universelle — l'harmonie perçue.**

La symétrie est un signal d'ordre et d'intention. Le cerveau la reconnaît en moins de 100ms. Les interfaces symétriques sont perçues comme plus professionnelles, plus fiables, plus "propres". Mais la symétrie parfaite peut aussi paraître froide — l'asymétrie contrôlée crée de la tension.

> *Règle UX : La symétrie rassure. L'asymétrie surprend. Les deux ensemble captivent.*

---

## 🌍 Dans la vraie vie

- **Générateurs de mandalas** — apps de méditation et relaxation
- **Design de tissus** — motifs répétés en industrie textile
- **Architecture** — plans symétriques des bâtiments classiques
- **Logos** — la majorité des grands logos sont symétriques (BMW, Audi, Mercedes)

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de sections — 6 (étoile de David) ou 72 (quasi-continu)
const slices = 36

// Taille des points
ctx.arc(x - centerX, y - centerY, 5, 0, Math.PI * 2)
// essaie 2 (poussière) ou 15 (blobs)

// Désactiver le miroir pour une symétrie pure (sans retournement)
// Supprime le bloc ctx.save() ... ctx.scale(1,-1) ... ctx.restore()
```

---

*MathxCanvas · Jour 19/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
