
## Un séparateur

^4bfadf

Pour créer une ligne de séparation, il suffit d'utiliser trois fois de suite sur une ligne le `-` ou le `*`

```
***
ou
---
```

Donne
***

## Une Image

^a29179

Pour insérer une image, il faut commencer par un `!` puis le texte alternatif acollé entre `[]` puis le lien entre `()`. Pour les plus zélé.e.s, un titre peut être ajouté entre `""`.
```markdown
![Tux, la mascotte Linux](https://commons.wikimedia.org/wiki/File:Toicon-icon-fandom-fly.svg "Vive Tux !")
```
Donne
![test](https://upload.wikimedia.org/wikipedia/commons/thumb/3/34/Tux-Tango.svg/120px-Tux-Tango.svg.png?20220831124412)

## Un Lien

^d23057

```markdown
J'adore [cette musique](https://www.youtube.com/watch?v=dQw4w9WgXcQ&list=RDdQw4w9WgXcQ&start_radio=1)
```
Donne
J'adore [cette musique](https://www.youtube.com/watch?v=dQw4w9WgXcQ&list=RDdQw4w9WgXcQ&start_radio=1).

## Un tableau

^f5222e

Un tableau se dessine avec des `|` pour les colonnes. Il faut mettre des tirets `-` sous la première ligne pour marquer les titres des colonnes. L'utilisation des `:` permet d'indiquer l'alignement dans la colonne.

```markdown
| Syntaxe      | Description | Test     |
| :---        |    :----:   |          ---: |
| Header      | Titre       | Here's this   |
| Paragraphe   | Texte        | And more, and more      |
```
Donne

| Syntaxe    | Description |               Test |
| :--------- | :---------: | -----------------: |
| Header     |    Titre    |        Here's this |
| Paragraphe |    Texte    | And more, and more |
