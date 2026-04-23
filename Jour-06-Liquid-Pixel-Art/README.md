# Jour 06 — Liquid Pixel Art

> *Dessiner avec la souris — et regarder les couleurs fondre comme de la lave.*

---

## 👁️ Ce que tu vois

Déplace ta souris pour peindre. Chaque position colore une cellule de la grille avec une teinte différente selon ta progression. Les couleurs "fondent" lentement vers le noir — comme de la peinture chaude qui refroidit. Le résultat est liquide, organique, en perpétuelle disparition.

---

## 📐 Le concept mathématique

**La décroissance exponentielle par accumulation.**

```javascript
// L'astuce du "liquide" : on ne JAMAIS efface proprement
// On applique un voile noir semi-transparent en boucle
ctx.fillStyle = 'rgba(0, 0, 0, 0.05)'
ctx.fillRect(0, 0, width, height)

// À chaque frame, chaque pixel perd 5% de sa luminosité
// Après N frames : luminosité = valeur_initiale × (0.95)^N
// C'est une exponentielle décroissante
```

**La grille de pixels :**
```javascript
// Snap sur la grille : arrondir à la taille de cellule
const x = Math.floor(mouseX / cellSize) * cellSize
const y = Math.floor(mouseY / cellSize) * cellSize
```

---

## 🎨 Le principe UX

**Mémoire visuelle — le passé persiste mais s'efface.**

La durée de vie d'une trace visuelle communique son importance. Court = fugace = éphémère. Long = permanent = mémorable. Ici, ni l'un ni l'autre — la trace intermédiaire crée une tension entre création et disparition, ce qui rend l'expérience addictive.

> *Règle UX : La durée de persistance d'un feedback dit combien il compte.*

---

## 🌍 Dans la vraie vie

- **Adobe Photoshop** — les brosses avec opacité et fondu
- **Procreate** — l'outil aquarelle avec diffusion temporelle
- **Snapchat** — les dessins qui disparaissent (durée = valeur)
- **Outils de présentation** — laser pointer avec traînée

---

## 🎛️ Valeurs à modifier

```javascript
// Taille des pixels — essaie 5 (résolution haute) ou 50 (blocs Minecraft)
const cellSize = 20;

// Vitesse de fondu — essaie 0.01 (fondu très lent) ou 0.2 (disparition rapide)
ctx.fillStyle = 'rgba(0, 0, 0, 0.05)';

// Filtre CSS pour amplifier les couleurs — dans le style :
// filter: contrast(200%) brightness(150%)  → effet néon intense
filter: contrast(150%) brightness(120%);
```

---

*MathxCanvas · Jour 06/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
