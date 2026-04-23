# Jour 15 — Audio Visualizer

> *Le son a une forme. La Transformée de Fourier la révèle.*

---

## 👁️ Ce que tu vois

Clique pour activer le micro (ou charge une musique). Des barres de fréquences s'animent en temps réel — les basses à gauche, les aigus à droite. Déplace ta souris pour changer les couleurs et l'intensité. Le son devient visible.

---

## 📐 Le concept mathématique

**La Transformée de Fourier Rapide (FFT) — décomposer un son en fréquences.**

Tout son est la somme de sinusoïdes de fréquences différentes. La FFT décompose ce mélange et dit : *"ce son contient X% de 100Hz, Y% de 500Hz, Z% de 2000Hz..."*

```javascript
const analyser = audioCtx.createAnalyser()
analyser.fftSize = 256  // Résolution de l'analyse

const dataArray = new Uint8Array(analyser.frequencyBinCount)
analyser.getByteFrequencyData(dataArray)
// dataArray[i] = énergie de la fréquence i (0 à 255)

// Dessin des barres
for (let i = 0; i < dataArray.length; i++) {
  const barHeight = dataArray[i] * 2
  ctx.fillRect(i * barWidth, canvas.height - barHeight, barWidth, barHeight)
}
```

**C'est la même maths que le Jour 26** (Fourier Circles) — mais en temps réel sur un vrai signal audio.

---

## 🎨 Le principe UX

**Son visible = information — la synesthésie comme design.**

Rendre le son visible réduit la charge cognitive de l'écoute. L'utilisateur comprend *ce qui se passe* même sans entendre. C'est un principe d'accessibilité et d'enrichissement sensoriel simultanément.

> *Règle UX : Croiser les sens (voir ce qu'on entend) amplifie la compréhension.*

---

## 🌍 Dans la vraie vie

- **Spotify** — visualiseurs d'équaliseur dans l'app
- **Interfaces DJ** — Serato, Ableton Live
- **Accessibilité** — visualisation des sons pour malentendants
- **Outils de montage audio/vidéo** — Adobe Premiere, DaVinci Resolve

---

## 🎛️ Valeurs à modifier

```javascript
// Résolution FFT — 64 (peu de barres) ou 1024 (très détaillé)
analyser.fftSize = 256

// Hauteur max des barres
const barHeight = dataArray[i] * 2  // * 1 (petit) ou * 4 (grands pics)

// Couleur selon la fréquence
const hue = (i / dataArray.length) * 360
ctx.fillStyle = `hsl(${hue}, 100%, 50%)`
// Ou une couleur fixe : '#00f2ff'
```

---

*MathxCanvas · Jour 15/30 · Jour pivot — la Transformée de Fourier en action · [github.com/angeawalabj](https://github.com/angeawalabj)*
