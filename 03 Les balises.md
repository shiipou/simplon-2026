
Pour commencer un fichier Html on peut taper directement : "html:5" cela créera directement la base d'un fichier html vide : 

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
</head>
<body>
</body>
</html>
```


Les 2 types principaux sont block et inline

Par exemple : 

Des balises de types blocs : 

```
<p>
<h1>…<h6>
<main>
<section>
<article>
<div>

```

Des balises de type inline : 

```
…	<a>
<em>
<strong>
<img>
<abbr>
<span>
```

Les éléments « en bloc » commencent sur une nouvelle ligne occupent le maximum d’espace disponible (la largeur de leurs conteneurs) peuvent contenir des éléments block ou inline. Les éléments « en ligne » suivent le fil du texte occupent l’espace de leur contenu (la largeur de leurs contenus) ne peuvent contenir que des éléments inline; seule exception, le lien 
```
<a>
```


qui lui peut contenir des éléments de type block

D’autres types existent comme :

list item ``` <li>```
table ```<table>```
etc…

Pour aller plus loin avec les types d’éléments, la page sur les catégories de contenu du MDN est très complète.

Quelques exemples de balises : 

```
<body> // Contient par definition l'ensemble du corps de la page web.

<link> //  Permet de lier une ressource à la page web.

<script> // Permet de lier un document javascript à la page.

<h1><h2><h3><h4><h5><h6> // Sont utilisés pour créer des titres. 

<p> // Pour ajouter du texte

<img src="" alt=""> // Pour ajouter une image 

<a href=""></a> // pour créer un lier vers une ancre (soit dans la même page ou vers une autre page)

<ul>                                                  
    <li>La programmation</li>
    <li>La montagne</li>                // Pour créer une liste 
    <li>La musique</li>
</ul>
<nav> // Pour créer une navigation 
<table> //  Permet de créer un tableau 
```

Pour aller plus loin la documentation MDN est là pour vous aider 