# Jour 25 — Matrix Rain

> *Des caractères tombent — et ta souris les fait briller.*

---

## 👁️ Ce que tu vois

Des colonnes de caractères aléatoires tombent en vert sur fond noir — l'esthétique Matrix. Approche ta souris : les caractères proches deviennent blancs et tombent deux fois plus vite. Tu perturbes le flux d'information.

---

## 📐 Le concept mathématique

**Les colonnes indépendantes — chacune a son propre état.**

```javascript
const drops = Array(columns).fill(1)  // Position Y de chaque goutte

for (let i = 0; i < drops.length; i++) {
  const x = i * fontSize
  const y = drops[i] * fontSize

  // Distance avec la souris
  const dist = Math.sqrt((mouse.x-x)² + (mouse.y-y)²)

  // Vitesse différentielle selon la proximité
  drops[i] += (dist < 150) ? 2 : 1  // Double vitesse si proche

  // Reset aléatoire en haut
  if (y > canvas.height && Math.random() > 0.975) drops[i] = 0
}
```

---

## 🎨 Le principe UX

**Densité = urgence — la surcharge d'information comme signal.**

Un flux dense de données crée un sentiment d'urgence, de complexité, de volume. Les interfaces de monitoring (cybersécurité, data centers, finance) utilisent ce principe pour communiquer la *quantité* d'information traitée.

> *Règle UX : La densité visuelle communique la complexité du système sous-jacent.*

---

## 🌍 Dans la vraie vie

- **Interfaces de cybersécurité** — dashboards de détection d'intrusions
- **Salles de contrôle** — systèmes de monitoring en temps réel
- **Cinéma** — esthétique de hacking dans les films et séries
- **Trading algorithmique** — flux de données financières en temps réel

---

## 🎛️ Valeurs à modifier

```javascript
// Taille des caractères — 8 (fin, dense) ou 24 (gros, lisible)
const fontSize = 16

// Vitesse de fondu — 0.02 (très persistant) ou 0.15 (disparaît vite)
ctx.fillStyle = "rgba(0, 0, 0, 0.05)"

// Rayon d'influence — essaie 50 (précis) ou 250 (large)
if (dist < 100) { ctx.fillStyle = "#fff" }

// Changer les caractères — essaie des kanji :
const characters = "日本語漢字ひらがなカタカナ"
```

---

*MathxCanvas · Jour 25/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
