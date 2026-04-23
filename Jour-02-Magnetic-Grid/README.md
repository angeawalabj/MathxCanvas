# Jour 02 — Magnetic Grid

> *La première formule vraiment utile : mesurer une distance.*

---

## 👁️ Ce que tu vois

Une grille de carrés qui fuient ta souris. Plus tu t'approches, plus ils s'écartent violemment. Dès que tu t'éloignes, ils reviennent doucement à leur place. Chaque carré devient rouge vif dans la zone d'influence.

---

## 📐 Le concept mathématique

**La distance euclidienne — ou le théorème de Pythagore appliqué.**

```
distance = √(Δx² + Δy²)

où :
  Δx = mouseX - squareCenterX
  Δy = mouseY - squareCenterY
```

C'est la formule des formules. Elle mesure la distance *en ligne droite* entre deux points dans un plan 2D. Tu la retrouveras dans **chaque animation interactive** à partir d'aujourd'hui.

**La force de répulsion :**
```
force = (triggerDistance - distance) / triggerDistance

→ Quand distance = 0   : force = 1.0 (répulsion maximale)
→ Quand distance = 100 : force = 0.0 (aucune répulsion)
```

La force est proportionnelle à la proximité. C'est une relation *linéaire inverse*.

---

## 🎨 Le principe UX

**Répulsion = espace personnel.**

En psychologie de l'espace (proxémique), chaque individu possède une "bulle" personnelle. Les interfaces qui respectent ce principe — en donnant de l'espace aux éléments quand l'utilisateur approche — semblent plus *respirantes* et moins agressives.

> *Règle UX : Ce qui résiste à notre passage retient notre attention.*

La résistance crée de l'engagement. Un bouton qui fuit légèrement la souris est plus mémorable qu'un bouton statique.

---

## 🌍 Dans la vraie vie

- **Portfolios de développeurs** — effets de répulsion sur les cartes de projet
- **Cursor effects** sur les sites d'agences créatives
- **Apple Vision Pro** — les icônes qui "gonflent" quand on les regarde
- **Dock macOS** — les icônes qui s'agrandissent à la proximité du curseur

---

## 🎛️ Valeurs à modifier

```javascript
// Distance de déclenchement — essaie 50 pour une bulle petite, 200 pour large
const triggerDistance = 100;

// Force de déplacement — essaie 1.0 pour violent, 0.2 pour subtil
const moveX = deltaX * force * -0.5;  // Change -0.5

// ATTRACTION au lieu de répulsion : change -0.5 par +0.5
const moveX = deltaX * force * +0.5;

// Vitesse de retour — dans CSS, essaie 0.05s (nerveux) ou 0.8s (mou)
transition: transform 0.2s ease-out;
```

---

## 💡 Ce qu'on vient d'apprendre

`√(Δx² + Δy²)` mesure une distance.  
Mais comment trouver *la direction* vers un point ? → Jour 16 : `Math.atan2()`

---

*MathxCanvas · Jour 02/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
