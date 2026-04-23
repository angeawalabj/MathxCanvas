# Jour 14 — Climbing Vine

> *Déplace ta souris lentement — une plante pousse derrière toi.*

---

## 👁️ Ce que tu vois

Chaque mouvement de souris génère une nouvelle "vigne" qui pousse organiquement — s'épaissit, s'affine, se ramifie. Les branches héritent de la direction parente. Le canvas accumule des plantes sans jamais s'effacer : une forêt apparaît progressivement.

---

## 📐 Le concept mathématique

**La marche aléatoire guidée — bruit angulaire.**

```javascript
// La direction change légèrement à chaque pas
this.angle += (Math.random() - 0.5) * 0.2  // Déviation aléatoire ± 0.1 rad

// La nouvelle position
this.x += Math.cos(this.angle) * this.size
this.y += Math.sin(this.angle) * this.size
```

**La ramification récursive :**
```javascript
// 5% de chance de créer une branche à chaque pas
if (Math.random() > 0.95 && this.width > 2) {
  vines.push(new Vine(x, y, angle + 0.5, size * 0.9))
  // La branche secondaire hérite position + direction légèrement déviée
}
```

---

## 🎨 Le principe UX

**Croissance organique — le temps rendu visible.**

Les interfaces qui "grandissent" donnent le sentiment que quelque chose est vivant, que l'utilisation laisse une trace durable. C'est le principe des *jardins numériques* — l'interaction accumule et construit plutôt que d'effacer.

> *Règle UX : Ce qui persiste et grandit crée de l'attachement.*

---

## 🌍 Dans la vraie vie

- **Visualisation d'arbres de données** — structures arborescentes, filesystems
- **Algorithmes de génération procédurale** — arbres dans les jeux vidéo (Minecraft)
- **Art génératif** — L-systems, fractales botaniques
- **Cartes mentales dynamiques** — Miro, Figma FigJam

---

## 🎛️ Valeurs à modifier

```javascript
// Aléatoire de direction — 0.05 (presque droit) ou 0.8 (très tortueux)
this.angle += (Math.random() - 0.5) * 0.2

// Probabilité de ramification — 0.99 (rare) ou 0.85 (forêt dense)
if (Math.random() > 0.95 ...)

// Couleurs de la vigne — essaie des tons automnaux :
this.color = `hsl(${20 + Math.random() * 30}, 80%, ${30 + Math.random() * 20}%)`

// Vitesse de croissance
this.speed = Math.random() * 2 + 0.5  // essaie * 5 pour rapide
```

---

*MathxCanvas · Jour 14/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
