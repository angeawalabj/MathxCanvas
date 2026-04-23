# Jour 01 — Neon Grid

> *Le point de départ. Zéro JavaScript, zéro calcul — juste CSS et une grille qui s'allume.*

---

## 👁️ Ce que tu vois

Une grille de 400 carrés sombres. Quand ta souris les effleure, ils s'allument en cyan néon avec un halo lumineux. Quand tu t'éloignes, la lumière s'estompe lentement — comme une braise qui refroidit.

---

## 📐 Le concept mathématique

**Aucun calcul — et c'est le point.**

Le Jour 01 existe pour montrer que l'interaction visuelle n'a pas besoin de maths. Le hover CSS suffit. La transition temporelle est gérée par le navigateur.

```
Allumage : transition: 0s   → instantané
Extinction : transition: 2s  → lent, comme de la chaleur
```

C'est la leçon zéro : *avant d'ajouter des maths, comprends ce que CSS peut faire seul.*

---

## 🎨 Le principe UX

**Feedback immédiat.**

L'un des principes fondamentaux du design d'interaction : l'interface doit répondre *immédiatement* à l'action de l'utilisateur. Zéro délai à l'allumage — le cerveau perçoit le lien causal. Le délai à l'extinction crée une "mémoire visuelle" du chemin parcouru.

> *Règle UX : Le délai à l'action casse la confiance. Le délai à la disparition crée de la profondeur.*

---

## 🌍 Dans la vraie vie

- **Claviers gaming RGB** (Corsair, Razer) — chaque touche réagit à la frappe
- **Hover states** sur les sites e-commerce — les cartes produit s'illuminent
- **Dashboards de données** — les cellules d'une table réagissent au survol
- **Apple.com** — les grilles de produits avec effets de lumière au survol

---

## 🎛️ Valeurs à modifier pour changer l'effet

Dans `index.html`, cherche ces lignes et modifie :

```css
/* Vitesse d'extinction — essaie 0.5s pour un flash rapide, 5s pour très lent */
transition: 2s ease;

/* Couleur allumée — essaie #ff0055 pour rouge, #7c3aed pour violet */
background-color: #00fffc;

/* Intensité du halo — augmente le 3ème chiffre pour un halo plus large */
box-shadow: 0 0 10px #00fffc, 0 0 30px #00fffc;

/* Taille des carrés — essaie 10px pour une grille fine, 40px pour des blocs */
height: 20px;
width: 20px;
```

---

## 💡 Question pour aller plus loin

Si tu voulais que les carrés s'allument *progressivement* depuis la souris (vague de lumière), que faudrait-il ajouter ? 

→ *Réponse au Jour 02 : la distance euclidienne.*

---

*MathxCanvas · Jour 01/30 · [github.com/angeawalabj](https://github.com/angeawalabj)*
