# Jour 30 — Final Chaos

> *2000 particules, une loi de gravitation, ta souris comme étoile — et du chaos qui devient art.*

---

## 👁️ Ce que tu vois

2000 particules dérivent dans l'espace. Ta souris est un soleil : elle attire toutes les particules vers elle. Clique pour basculer l'attraction — les particules explosent en toutes directions puis reviennent. Des orbites se forment, des spirales apparaissent, le chaos prend une forme.

---

## 📐 Le concept mathématique

**La loi de gravitation universelle — simplifiée pour le canvas.**

```javascript
let dx = mouse.x - particle.x
let dy = mouse.y - particle.y
let distance = Math.sqrt(dx*dx + dy*dy)

// F = G·M·m / d²  →  simplifié : force = constante / distance
let force = 1000 / distance

// Accélération = Force / masse (masse = 1 ici)
particle.accX = (dx / distance) * force
particle.accY = (dy / distance) * force

particle.vx += particle.accX
particle.vy += particle.accY
particle.vx *= friction  // Friction pour stabiliser
```

---

## 🎨 Le principe UX

**Chaos contrôlé = art — l'ordre émergent.**

Le paradoxe final : des règles simples appliquées à de nombreuses entités produisent une complexité qu'aucun designer n'aurait pu planifier. C'est la définition des systèmes émergents — et c'est pourquoi ce genre d'animation est perçue comme vivante.

> *Règle UX ultime : Les meilleures interfaces ne sont pas dessinées — elles émergent de règles bien choisies.*

---

## 🌍 Dans la vraie vie

- **Simulations cosmologiques** — NASA, ESA modélisent la formation des galaxies
- **Algorithmes de flocking** — simulation de nuées d'oiseaux, bancs de poissons
- **Art génératif** — les œuvres qui s'auto-organisent
- **IA et systèmes complexes** — les comportements émergents des réseaux de neurones

---

## 🎛️ Valeurs à modifier

```javascript
// Nombre de particules — 500 (léger) ou 5000 (puissant)
for (let i = 0; i < 2000; i++)

// Constante gravitationnelle — 200 (faible) ou 3000 (très attractif)
let force = 1000 / distance

// Friction — 0.99 (orbites longues) ou 0.90 (stabilise vite)
this.friction = 0.96

// Traînée — 0.05 (trace longue, voir les orbites) ou 0.5 (trace courte)
ctx.fillStyle = 'rgba(0, 0, 0, 0.1)'
```

---

## 30 jours. 30 animations. 30 concepts.

Tu viens de traverser les trois actes :
- **Acte 1** : les maths comme outil de perception
- **Acte 2** : les maths comme simulation de la physique  
- **Acte 3** : les maths comme génération de complexité

Le Jour 31 attend. La galerie est complète.

---

*MathxCanvas · Jour 30/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
