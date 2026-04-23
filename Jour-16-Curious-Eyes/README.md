# Jour 16 — Curious Eyes

> *Quarante yeux qui te regardent — peu importe où tu vas.*

---

## 👁️ Ce que tu vois

Une grille d'yeux blancs. Chaque pupille suit ta souris avec précision — elles savent exactement où tu es. L'effet est entre le fascinant et l'inquiétant. Déplace ta souris : elles te suivent toutes simultanément.

---

## 📐 Le concept mathématique

**`Math.atan2(y, x)` — la fonction qui connaît les directions.**

```javascript
// Calcul de l'angle entre le centre de l'œil et la souris
const angle = Math.atan2(
  mouseY - eyeCenterY,  // Δy
  mouseX - eyeCenterX   // Δx
)

// Conversion angle → position de la pupille
const x = Math.cos(angle) * maxDistance  // ± 15px
const y = Math.sin(angle) * maxDistance

pupil.style.transform = `translate(${x}px, ${y}px)`
```

`atan2` retourne l'angle en radians entre -π et +π. Combiné à `cos` et `sin`, il transforme une direction en déplacement (x, y). C'est le GPS des animations interactives.

---

## 🎨 Le principe UX

**Regard = connexion émotionnelle.**

Les yeux sont le signal social le plus puissant. Des éléments qui "regardent" l'utilisateur créent une connexion émotionnelle immédiate — et une légère tension entre confort et inquiétude. Les mascottes UI exploitent ce principe pour rendre les interfaces plus humaines.

> *Règle UX : Ce qui regarde l'utilisateur crée une présence — même sans visage.*

---

## 🌍 Dans la vraie vie

- **Mascottes UI** — Duolingo (Duo), Google Assistant animations
- **Personnages de jeux** — les PNJ qui suivent le joueur du regard
- **Installations artistiques** — art interactif en galerie
- **Chatbots visuels** — avatars d'IA qui "regardent" l'utilisateur

---

## 🎛️ Valeurs à modifier

```javascript
// Rayon de déplacement de la pupille — 5 (subtil) ou 25 (exagéré)
const distance = 15;

// Nombre d'yeux — change eyeCount
const eyeCount = 40;  // essaie 100 pour une horreur totale

// Taille des yeux — dans CSS
.eye { width: 80px; height: 80px; }  // essaie 40px ou 120px

// Réactivité — dans CSS transition
.pupil { transition: 0.1s ease-out; }  // 0s (instantané) ou 0.5s (paresseux)
```

---

*MathxCanvas · Jour 16/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
