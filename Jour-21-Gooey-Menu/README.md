# Jour 21 — Gooey Menu

> *Des bulles qui fusionnent — un filtre SVG transforme la physique en liquide.*

---

## 👁️ Ce que tu vois

Une bulle centrale rouge. Approche ta souris : cinq bulles satellites s'écartent en cercle. L'effet saisissant : les bulles semblent *fondre* les unes dans les autres quand elles se touchent — comme du mercure liquide.

---

## 📐 Le concept mathématique

**Le filtre Gooey — flou gaussien + seuil de couleur.**

```xml
<filter id="gooey">
  <!-- 1. Flou : les bords deviennent graduels -->
  <feGaussianBlur stdDeviation="10" result="blur"/>
  
  <!-- 2. Matrice de couleur : amplifie le canal alpha -->
  <!-- Les zones mi-transparentes deviennent soit pleines soit vides -->
  <feColorMatrix values="1 0 0 0 0
                         0 1 0 0 0
                         0 0 1 0 0
                         0 0 0 18 -7"/>
</filter>
```

La valeur `18` amplifie l'alpha. La valeur `-7` crée un seuil brutal. Résultat : les zones floues entre les cercles deviennent soit totalement opaques (fusion) soit totalement transparentes (séparation).

---

## 🎨 Le principe UX

**Fluidité = douceur perçue — la matière liquide comme métaphore.**

Les interfaces qui imitent la physique des fluides sont perçues comme plus douces, plus naturelles, moins mécaniques. Le menu Gooey communique "souplesse" et "fluidité" — des qualités qu'on veut associer à une application.

> *Règle UX : La métaphore physique choisie communique la personnalité de l'interface.*

---

## 🌍 Dans la vraie vie

- **FAB buttons (Floating Action Button)** — Material Design, Android
- **Menus circulaires mobiles** — applications de dessin, outils créatifs
- **Effets de blob** — sites d'agences créatives modernes
- **Interface de jeux** — sélection de personnages, menus d'inventaire

---

## 🎛️ Valeurs à modifier

```xml
<!-- Intensité du flou — 5 (peu liquide) ou 20 (très fondu) -->
<feGaussianBlur stdDeviation="10"/>

<!-- Seuil de fusion — augmente 18 pour fusion plus agressive -->
<feColorMatrix values="... 0 0 0 18 -7"/>
```

```javascript
// Distance de déploiement des bulles
const spread = dist < activeRange ? (activeRange - dist) * 0.8 : 0

// Nombre de bulles — ajoute des .side-bubble dans le HTML avec data-angle
```

---

*MathxCanvas · Jour 21/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
