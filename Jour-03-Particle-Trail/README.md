# Jour 03 — Particle Trail

> *Quand la souris laisse une traînée de lumière — introduction aux vecteurs de vitesse.*

---

## 👁️ Ce que tu vois

Chaque mouvement de souris génère 5 particules lumineuses colorées. Elles se dispersent dans des directions aléatoires, rétrécissent progressivement, puis disparaissent. Les couleurs changent en arc-en-ciel continu. Le fond s'efface lentement — créant un effet de traînée lumineuse.

---

## 📐 Le concept mathématique

**Les vecteurs de vitesse.**

Chaque particule a une position `(x, y)` et une vitesse `(vx, vy)`. À chaque frame :

```
x = x + vx
y = y + vy
```

C'est tout. Un vecteur, c'est juste deux nombres qui décrivent *combien* et *dans quelle direction* quelque chose se déplace.

**La couleur arc-en-ciel :**
```
hsl(hue, 100%, 50%)

hue augmente de 2 à chaque frame  →  cycle de couleur continu
```

**L'effet de traînée :**
```
ctx.fillStyle = 'rgba(0, 0, 0, 0.1)'
ctx.fillRect(0, 0, width, height)

→ On ne *efface* pas le canvas, on le *recouvre* à 10% de noir
→ Les anciennes frames "fanent" progressivement
```

---

## 🎨 Le principe UX

**Persistance visuelle — la trace guide le regard.**

L'œil humain suit naturellement les traînées lumineuses. C'est un réflexe évolutif (suivre le mouvement = survivre). Les interfaces qui laissent une trace temporaire de l'action passée aident l'utilisateur à comprendre *ce qu'il vient de faire*.

> *Règle UX : Le passé visible réduit la charge cognitive du présent.*

---

## 🌍 Dans la vraie vie

- **Curseurs custom** sur les sites de luxe et d'agences créatives
- **After Effects** — les effets de particules sur les titres de films
- **Jeux vidéo** — traînées de balles, sillages de vaisseaux
- **Présentations Apple** — les keynotes avec particules et traînées

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de particules par mouvement — essaie 1 (discret) ou 20 (explosif)
for(let i = 0; i < 5; i++)

// Taille max des particules — essaie 5 (pluie fine) ou 30 (boules)
this.size = Math.random() * 15 + 1;

// Vitesse de dispersion — essaie 1 (lent) ou 8 (explosif)
this.speedX = Math.random() * 3 - 1.5;

// Transparence du fondu — 0.02 (trace longue) ou 0.3 (trace courte)
ctx.fillStyle = 'rgba(0, 0, 0, 0.1)';

// Vitesse de changement de couleur — essaie 0.5 (lent) ou 10 (arc-en-ciel rapide)
hue += 2;
```

---

*MathxCanvas · Jour 03/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
