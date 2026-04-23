# Jour 04 — Spotlight Effect

> *Un canvas noir qui cache un secret — et une lampe torche pour le révéler.*

---

## 👁️ Ce que tu vois

L'écran est entièrement noir. Derrière, un texte "Secret Information" est presque invisible. Ta souris devient une lampe torche : elle perce l'obscurité avec un halo lumineux aux bords flous. Le texte se révèle progressivement là où tu passes.

---

## 📐 Le concept mathématique

**Le gradient radial et la composition de couches.**

```javascript
const gradient = ctx.createRadialGradient(
  mouse.x, mouse.y, 0,      // Centre : complètement transparent
  mouse.x, mouse.y, radius  // Bords : complètement opaque
)
gradient.addColorStop(0, 'rgba(255,255,255,1)')  // Trou dans le noir
gradient.addColorStop(1, 'rgba(255,255,255,0)')  // Fondu vers l'obscurité
```

**Le mode de composition `destination-out` :**
```
source-over    → dessine par-dessus (normal)
destination-out → là où je dessine, EFFACE ce qui existe

→ On remplit d'abord tout en noir opaque
→ On "perce" le noir avec le cercle de lumière
→ Le texte HTML en dessous devient visible
```

---

## 🎨 Le principe UX

**Révélation progressive — l'inconnu attire.**

Le mystère engage. Une interface qui cache de l'information et demande à l'utilisateur de l'explorer activement crée une expérience mémorable. C'est le principe du *progressive disclosure* poussé à l'extrême.

> *Règle UX : Ce qu'on doit découvrir vaut plus que ce qui est donné.*

---

## 🌍 Dans la vraie vie

- **Onboarding interactif** — révéler les fonctionnalités progressivement
- **Expériences de storytelling web** — The New York Times interactive stories
- **Jeux d'exploration** — fog of war dans les jeux de stratégie
- **Présentations créatives** — slides avec révélation par interaction

---

## 🎛️ Valeurs à modifier

```javascript
// Taille de la lampe — essaie 80 (petite lanterne) ou 300 (grande zone)
let radius = 150;

// Changer la couleur de la lumière — essaie une lumière chaude :
gradient.addColorStop(0, 'rgba(255, 200, 100, 1)')

// Rendre le fondu plus brutal (bord net) :
gradient.addColorStop(0.8, 'rgba(255,255,255,1)') // ajoute cette ligne
gradient.addColorStop(1,   'rgba(255,255,255,0)')

// Couleur du fond caché — dans CSS, change #333 pour rendre le texte plus visible
color: #666;
```

---

*MathxCanvas · Jour 04/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
