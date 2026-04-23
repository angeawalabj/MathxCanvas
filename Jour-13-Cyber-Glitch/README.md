# Jour 13 — Cyber Glitch

> *Un texte qui se déchire — l'erreur comme esthétique.*

---

## 👁️ Ce que tu vois

Le mot "GLITCH" sur fond noir. Passe ta souris dessus : il tremble, se découpe en tranches décalées en cyan et magenta. L'effet imite un signal vidéo corrompu ou un écran en train de lâcher. C'est volontairement instable.

---

## 📐 Le concept mathématique

**Le `clip-path` — découper un élément en zone visible.**

```css
clip-path: inset(10% 0 30% 0)
/* Affiche uniquement : de 10% en haut à 30% en bas */

/* Animation : découpe aléatoire à chaque keyframe */
@keyframes glitch-anim {
  0%  { transform: translate(0);      clip-path: inset(10% 0 30% 0); }
  20% { transform: translate(-5px, 5px); clip-path: inset(40% 0 10% 0); }
  40% { transform: translate(-5px,-5px); clip-path: inset(80% 0  5% 0); }
}
```

Trois couches du même texte, décalées en X et Y, chacune avec une zone visible différente. L'œil perçoit un seul texte fragmenté.

---

## 🎨 Le principe UX

**Rupture = attention — l'inattendu capte le regard.**

Le glitch est l'anti-pattern de la cohérence visuelle — et c'est précisément ce qui le rend efficace. Une erreur dans un contexte parfait attire 100% de l'attention. Les designers l'utilisent intentionnellement pour créer des moments mémorables.

> *Règle UX : Une rupture contrôlée dans l'ordre visuel force l'attention.*

---

## 🌍 Dans la vraie vie

- **Identités visuelles cyberpunk** — Cyberpunk 2077, Watch Dogs
- **Titres de films et séries** — Mr. Robot, Tron
- **Sites d'agences tech** — glitch hover sur les titres principaux
- **Art génératif** — l'esthétique de l'erreur numérique

---

## 🎛️ Valeurs à modifier

```css
/* Vitesse du glitch — essaie 0.1s (très nerveux) ou 1s (lent et perturbant) */
animation: glitch-anim 0.3s ... infinite;

/* Intensité du décalage — essaie 2px (subtil) ou 20px (cassé) */
transform: translate(-5px, 5px);

/* Couleurs des couches — essaie rouge/vert pour un effet Matrix */
.glitch::before { color: #ff0000; }
.glitch::after  { color: #00ff00; }
```

---

*MathxCanvas · Jour 13/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
