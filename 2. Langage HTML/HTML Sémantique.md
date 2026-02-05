
Pour créer une page web en HTML, il suffit de créer un fichier en extension .html.

**Les balises HTML** :
Le langage HTML utilise des balises. On les écrit entre des chevrons <et>

*exemple* :
<p> balise ouvrante
</p> balise fermante
Ce qui se trouve à l'intérieur des balises se nomme "contenu".
Les balises et le contenu réunis sont appelés un élément.

Les balises indiquent la nature du texte qu'elles encadrent. Elles permettent au navigateur de comprendre ce qu'il faut afficher à l'écran pour les visiteurs d'un site.

Il existe des balises "**en paires**" et des balises "**orphelines**"

- Les balises "en paires" = comportent une balise ouvrante et une balise fermante
Elles s'ouvrent, contiennent du texte, et se ferment plus loin.
	Exemple, la balise ouvrante <p> ci-dessus, qui se ferme ainsi </p>

- Les balises orphelines = une seule balise
Ce sont des balises qui servent à insérer un élément à un endroit précis. Il n'est pas nécessaire de délimiter une fin.
*Exemple*, avec la balise <image>, il n'est pas nécessaire de délimiter le début et la fin de l'image.

**Les attributs HTML** 
Les attributs permettent de paramétrer les balises, de donner des informations supplémentaires.
Un attribut est situé dans la balise ouvrante d'une balise paire, ou directement dans une balise orpheline.

*Exemple :*
<img src="maphoto.jpg">
<img src  correspond au nom de l'attribut
ma photo de profil correspond à la valeur de l'attribut
<img src="maphoto.jpg"> correspond à la balise orpheline

## Structure de base d'une page html :

Ci-dessous les balises principales :
<head> correspond à l'en-tête de la page, le contenu n'apparaît pas dans l'affichage de la page.
<Body> correspond au corps et il apparaît dans l'affichage de la page.
<nav>correspond au menu
<main> correspond au contenu important
<footer> correspond au bas de la page
<section>permet de séparer le contenu de <main>
<article> permet de séparer le contenu de <section>
<aside> correspond à la barre de côté d'un site Web

## Un code s'écrit dans un éditeur de code comme Visual Studio Code. 
Il suffit d'ouvrir le fichier créé avec ".HTML" et de compléter à chaque fois le code ci-dessous :
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Le titre de ma page </title>
</head>
<body>

    <header>
        <h1>My Coding Journey</h1>
        
        <nav>
            <ul>
                <li><a href="#home">Home</a></li>
                <li><a href="#posts">Posts</a></li>
                <li><a href="#contact">Contact</a></li>
            </ul>
        </nav>
    </header>

    <main>
        
        <article>
            <h2>Understanding Semantics</h2>
            <p>Today I learned why semantics matter.</p>
            <p>It helps accessibility and SEO (Search Engine Optimization).</p>
        </article>

        <article>
            <h2>My First Code</h2>
            <p>I wrote my first HTML tag today!</p>
        </article>

    </main>

    <aside>
        <h3>About Me</h3>
        <p>I am a student learning web development.</p>
    </aside>

    <footer>
        <p>&copy; 2023 My Semantic Blog</p>
    </footer>

</body>
</html>
```

## Commenter** un code en HTML s'écrit :
<!--C'est un commentaire-->
