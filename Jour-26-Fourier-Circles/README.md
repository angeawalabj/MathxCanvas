# Jour 26 — Fourier Circles

> *Des cercles dans des cercles — qui ensemble dessinent n'importe quelle forme.*

---

## 👁️ Ce que tu vois

Cinq cercles imbriqués tournent à des vitesses différentes. La pointe du dernier cercle trace une courbe rouge. Déplace ta souris : l'axe horizontal change la vitesse, l'axe vertical change l'amplitude. La forme tracée change en temps réel.

---

## 📐 Le concept mathématique

**Les séries de Fourier — décomposer toute forme en cercles.**

```javascript
for (let i = 0; i < 5; i++) {
  let n = i * 2 + 1          // 1, 3, 5, 7, 9 (harmoniques impaires)
  let radius = A * (4 / (n * π))  // Amplitude décroissante
  
  x += radius * Math.cos(n * time)  // Mouvement X
  y += radius * Math.sin(n * time)  // Mouvement Y
}
```

Théorème de Fourier : **toute forme périodique peut être recréée en superposant des cercles** (sinusoïdes). Avec suffisamment de cercles, on peut approximer n'importe quelle courbe — un carré, un triangle, un visage.

---

## 🎨 Le principe UX

**Ordre dans le chaos — la révélation de la structure cachée.**

Voir un mouvement complexe se décomposer en mouvements simples crée un moment de compréhension profonde — le "ahh" de la révélation. Les visualisations qui montrent la *structure sous-jacente* d'un phénomène ont une valeur pédagogique extraordinaire.

> *Règle UX : Révéler la structure cachée d'un système crée de la confiance.*

---

## 🌍 Dans la vraie vie

- **Compression MP3** — la FFT décompose l'audio pour le comprimer
- **Compression JPEG** — même principe pour les images
- **Analyse de signaux** — médecine (IRM, ECG), sismologie
- **Synthèse sonore** — synthétiseurs additifs (Ableton Live)

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de cercles — 3 (simple) ou 10 (complexe)
for (let i = 0; i < 5; i++)

// Longueur de la trace
if (path.length > 200) path.pop()  // 50 (courte) ou 500 (longue)

// Vitesse de rotation — contrôlée par mouse.x
time += 0.05 * (mouse.x || 1)
// Fixe la vitesse : time += 0.02
```

---

*MathxCanvas · Jour 26/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
