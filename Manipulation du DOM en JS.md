

## 1. Le DOM (Document Object Model)

Le DOM est l’arbre généalogique de votre page HTML.

- **`window`** : la fenêtre globale du navigateur
    
- **`document`** : la page web actuelle
    

---

Pour modifier un élément, vous devez d’abord le sélectionner (`querySelector`), puis modifier ses propriétés (`textContent`).

HTML de référence :

`<p id="result">Waiting...</p>`

 

### Exemple de sélection et modification: 
 ```js

> const resultEl = document.querySelector('p#result')

> resultEl.textContent = 'Analyzing...'

 ```


 _Note: We use `.textContent` and not `.innerText` for standard tags like `<p>`._

  
---

## 2. Événements (Events)

Pour rendre la page interactive (clic, survol, clavier), on utilise des **écouteurs d’événements** (_event listeners_).

`element.addEventListener("click", function () {   // Action })`

### Exemple pour sélection un bouton, et ajouter un évènement "click" et au click on change le texte :

Reference HTML:
 

```html

<button id="btn-validate">Validate</button>

```

 ```js

 const validateBtn = document.querySelector('button#btn-validate')

validateBtn.addEventListener('click', function () {

 resultEl.textContent = 'Button clicked!'


 })

 ```

---


- MDN Web Docs – Manipuler le DOM
    
- [MDN Web Docs – Fetch API](https://developer.mozilla.org/fr/docs/Web/API/Fetch_API/Using_Fetch)
    
- [JSONPlaceholder](https://jsonplaceholder.typicode.com/) — pour tester des fausses APIs