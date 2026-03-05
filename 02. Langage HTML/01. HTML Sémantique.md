
Pour créer une page web en HTML, il suffit de créer un fichier en extension .html.

**Les balises HTML** :
Le langage HTML utilise des balises. On les écrit entre des chevrons <et> (cf document "balise" pour davantage d'informations)

**Les attributs HTML** 
Les attributs permettent de paramétrer les balises, de donner des informations supplémentaires (cf document "attribut", pour davantage d'informations)


## Un code s'écrit dans un éditeur de code comme Visual Studio Code. 
Il suffit d'ouvrir le fichier créé avec ".HTML" et de compléter à chaque fois le code ci-dessous qui comportent les balises essentielles :
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
