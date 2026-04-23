# Jour 27 — RGB Prism Lens

> *Ta souris est un prisme — elle décompose la lumière blanche en RGB.*

---

## 👁️ Ce que tu vois

Une grille de points blancs sur fond sombre. Approche ta souris : les points dans la zone se séparent en trois couches — rouge, vert, bleu — légèrement décalées, imitant l'aberration chromatique d'un objectif photographique.

---

## 📐 Le concept mathématique

**L'aberration chromatique — chaque longueur d'onde se réfracte différemment.**

```javascript
// Trois positions calculées avec des intensités différentes
const rPos = getDistortedPos(intensity = 1.2)  // Rouge : plus repoussé
const gPos = getDistortedPos(intensity = 1.0)  // Vert  : référence
const bPos = getDistortedPos(intensity = 0.8)  // Bleu  : moins repoussé

// Le mode "screen" mélange les couleurs comme de la lumière réelle
ctx.globalCompositeOperation = "screen"
// Rouge + Vert = Jaune
// Rouge + Bleu = Magenta
// Vert  + Bleu = Cyan
// R + G + B   = Blanc (reconstitution)
```

---

## 🎨 Le principe UX

**Lumière = matière — la physique de l'optique comme esthétique.**

L'aberration chromatique est techniquement un *défaut* des objectifs. Mais utilisée intentionnellement, elle donne un sentiment de *réalité photographique*, de matérialité physique. Les outils de post-traitement photo et vidéo l'utilisent comme effet artistique.

> *Règle UX : Un défaut physique simulé peut communiquer l'authenticité.*

---

## 🌍 Dans la vraie vie

- **Post-processing dans les jeux** — Unreal Engine, Unity aberration chromatique
- **Effets cinématiques** — transitions dans les films de SF
- **Photographie créative** — objectifs à tilt-shift, vieux objectifs soviétiques
- **Motion design** — génériques de films, intros de marques tech

---

## 🎛️ Valeurs à modifier

```javascript
// Écart entre les couches RGB — 1.0/0.8 (subtil) ou 1.8/0.2 (extrême)
const rPos = getDistortedPos(1.2)
const bPos = getDistortedPos(0.8)

// Rayon de l'effet
const mouse = { radius: 180 }  // 80 (précis) ou 300 (large)

// Intensité de distorsion maximale
let distortion = Math.pow(force, 2) * 50 * intensity
// * 20 (subtil) ou * 100 (fort)
```

---

*MathxCanvas · Jour 27/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
