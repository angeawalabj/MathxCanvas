# Jour 28 — Articulated Skeleton

> *Une créature qui te suit — construite à partir d'un seul principe de contrainte.*

---

## 👁️ Ce que tu vois

Une créature articulée suit ta souris. Sa tête est à ta position, et 24 segments suivent en chaîne — chacun contraint à rester à distance fixe du précédent. Le corps s'affine vers la queue. Elle ondule organiquement, comme un serpent ou une anguille.

---

## 📐 Le concept mathématique

**La cinématique inverse simplifiée — algorithme FABRIK.**

```javascript
// Segment 0 : suit la souris
points[0] = mouse

// Chaque segment suit le précédent
for (let i = 1; i < numSegments; i++) {
  const dx = points[i-1].x - points[i].x
  const dy = points[i-1].y - points[i].y
  const distance = Math.sqrt(dx*dx + dy*dy)
  const angle = Math.atan2(dy, dx)

  // Contrainte : reste à exactement segmentLength du précédent
  if (distance > segmentLength) {
    points[i].x = points[i-1].x - Math.cos(angle) * segmentLength
    points[i].y = points[i-1].y - Math.sin(angle) * segmentLength
  }
}
```

Le résultat : une chaîne de contraintes qui se propage — le mouvement de la tête se répercute jusqu'à la queue.

---

## 🎨 Le principe UX

**Corps = structure — la métaphore organique comme navigation.**

Une interface qui utilise des métaphores de corps articulé communique *connexion* et *hiérarchie*. Chaque partie est liée à la précédente. C'est une façon visuelle de montrer des dépendances, des chaînes de traitement, des workflows.

> *Règle UX : La métaphore organique rend les structures complexes intuitives.*

---

## 🌍 Dans la vraie vie

- **Animation de personnages** — rigging dans Blender, Maya, Unity
- **Robotique** — bras articulés, calcul de trajectoires
- **Jeux vidéo** — animation procédurale des queues, tentacules
- **Interfaces de workflow** — chaînes de traitement visualisées

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de segments — 10 (court) ou 50 (très long serpent)
const numSegments = 25

// Longueur de chaque segment — 10 (dense) ou 40 (espacé)
const segmentLength = 20

// Épaisseur de la tête — * 1.5 (mince) ou * 3 (épais)
ctx.lineWidth = (numSegments - i) * 1.5

// Couleur — essaie un dégradé chaud :
ctx.strokeStyle = `hsl(${i * 8}, 80%, 50%)`
```

---

*MathxCanvas · Jour 28/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
