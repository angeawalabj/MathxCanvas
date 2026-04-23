# Jour 10 — Magnetic Text

> *Des lettres qui fuient ta souris — et reviennent quand tu t'éloignes.*

---

## 👁️ Ce que tu vois

Le mot "MAGNETIC" flotte au centre. Approche ta souris : les lettres se dispersent. Éloigne-toi : elles reviennent lentement à leur place. Chaque lettre a un "poids" différent — certaines fuient plus vite que d'autres.

---

## 📐 Le concept mathématique

**Répulsion normalisée — séparer direction et intensité.**

```javascript
// Vecteur direction (normalisé : longueur = 1)
let forceDirectionX = dx / distance
let forceDirectionY = dy / distance

// Intensité de la force
let force = (mouse.radius - distance) / mouse.radius

// Application pondérée par le "poids" de la lettre
this.x -= forceDirectionX * force * this.density
this.y -= forceDirectionY * force * this.density
```

**Le retour élastique :**
```javascript
// Si pas d'interaction : retour progressif à la position d'origine
this.x -= (this.x - this.baseX) / 10  // 10% de l'écart à chaque frame
```

---

## 🎨 Le principe UX

**L'utilisateur contrôle le chaos — sentiment d'agentivité.**

Quand une interface résiste puis cède, elle crée un sentiment de *pouvoir*. L'utilisateur comprend qu'il a une influence directe. C'est l'un des patterns les plus engageants des interfaces interactives.

> *Règle UX : Résister puis céder crée plus d'engagement que céder immédiatement.*

---

## 🌍 Dans la vraie vie

- **Hero sections interactives** — portfolios de designers créatifs
- **Titres de pages d'accueil** — awwwards.com, sites de studios
- **Expériences de marque** — Nike, Adidas landing pages interactives
- **Jeux de menu** — titres qui réagissent au curseur

---

## 🎛️ Valeurs à modifier

```javascript
// Rayon d'influence — essaie 50 (petite bulle) ou 200 (grande zone)
const mouse = { radius: 100 }

// Poids des lettres — plus dense = fuit moins vite
this.density = (Math.random() * 30) + 1  // essaie * 5 pour leger, * 60 pour lourd

// Vitesse de retour — /10 = lent, /3 = rapide
this.x -= (this.x - this.baseX) / 10

// ATTRACTION au lieu de répulsion : change -= par +=
this.x += forceDirectionX * force * this.density
```

---

*MathxCanvas · Jour 10/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
