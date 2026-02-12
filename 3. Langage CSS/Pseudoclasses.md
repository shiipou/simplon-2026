Les **pseudo-classes** en CSS permettent de définir un style particulier pour un élément dans un **état spécifique** ou selon une **condition donnée**.

Elles commencent par un deux-points `:`

### Syntaxe

```css
selecteur:pseudo-classe {
  propriete: valeur;
}
```

---
## 1. Pseudo-classe liée aux interactions utilisateur

`:hover` : Appliquée lorsque l'utilisateur survole un élément avec la souris
### Exemple

```css
/* Tout bouton sur lequel le pointeur de l'utilisateur est en survol */
button:hover {
	color: blue;
}
```

---

`:active` : Appliquée pendant que l'élément est activé

### Exemple

```css
button:active {
	transform: scale(0.95);
}
```

---

`:focus` : Appliquée lorsque l'élément reçoit le focus (champ de formulaire par exemple)

```css
input:focus {
	border: 2px solid green;
}
```

---
`:focus-visible` : Appliquée lorsque le focus est visible (navigation clavier)

```css
button:focus-visible {
	outline: 3px solid orange;
}
```

---
`:focus-within` : Appliquée à un parent si un de ses enfants a le focus

```css
form:focus-within {
	background-color: #f0f0f0;
}
```

---
## 2. Pseudo-classes liées aux liens

 `:link` : Lien non visité.

```css
a:link {
	color: blue;
}
```

---
`:visited` : Lien déjà visité.

```css
a:visited {
	color: purple;
}
```

---
## Pseudo-classes structurelles

`:first-child` : Sélectionne le premier enfant.

```css
li:first-child {
	font-weight: bold;
}
```

---
`:last-child` : Sélectionne le dernier enfant.

```css
li:last-child {
	color: red;
}
```

---
`:nth-child(n)` : Sélectionne selon une position.

```css
li:nth-child(2) {
	color: blue;
}

li: nth-child(odd) {
	background: #eee;
}

li:nth-child(2n) {
	background: #ccc;
}
```

---
`:nth-last-child(n)` : Compte à partir de la fin.

```css
li: nth-last-child(1) {
	color: green;
}
```

---
## `:first-of-type`

Premier élément du même type.

`p:first-of-type {   font-size: 20px; }`

## `:last-of-type`

`p:last-of-type {   color: orange; }`

## `:nth-of-type(n)`

`p:nth-of-type(2) {   color: red; }`

## `:only-child`

Élément unique enfant.

`div:only-child {   border: 1px solid black; }`

## `:only-of-type`

Unique élément de son type.

---

# 🔹 4. Pseudo-classes liées aux formulaires

## `:checked`

Pour les cases cochées.

`input:checked {   accent-color: green; }`

## `:disabled`

Élément désactivé.

`input:disabled {   background: #ddd; }`

## `:enabled`

Élément activé.

## `:required`

Champ requis.

`input:required {   border-left: 4px solid red; }`

## `:optional`

Champ non requis.

## `:valid`

Contenu valide.

`input:valid {   border-color: green; }`

## `:invalid`

Contenu invalide.

`input:invalid {   border-color: red; }`

## `:in-range`

Valeur dans l’intervalle autorisé.

## `:out-of-range`

Valeur hors intervalle.

## `:read-only`

Champ en lecture seule.

## `:read-write`

Champ modifiable.

---

# 🔹 5. Pseudo-classes logiques (sélecteurs avancés)

## `:not()`

Exclut des éléments.

`div:not(.active) {   opacity: 0.5; }`

## `:is()`

Regroupe plusieurs sélecteurs.

`:is(h1, h2, h3) {   color: navy; }`

## `:where()`

Comme `:is()` mais sans ajouter de spécificité.

`:where(section, article) {   margin: 20px; }`

## `:has()` (moderne)

Sélectionne un parent selon ses enfants.

`div:has(img) {   border: 2px solid blue; }`

---

# 🔹 6. Pseudo-classes globales

## `:root`

Sélectionne l’élément racine (`html`).

`:root {   --main-color: #3498db; }`

## `:empty`

Élément sans contenu.

`div:empty {   display: none; }`

---

# 🔹 Différence entre pseudo-classes et pseudo-éléments

|Pseudo-classe|Pseudo-élément|
|---|---|
|Commence par `:`|Commence par `::`|
|Définit un état|Crée une partie virtuelle|
|Exemple : `:hover`|Exemple : `::before`|