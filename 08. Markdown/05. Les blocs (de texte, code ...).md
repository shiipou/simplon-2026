
## Mettre en valeur un bloc de texte

^e22e7e

```markdown
> "Ceci est un bloc de texte mis en valeur", Lorem ipsum dolor sit amet et tout le monde connaît la suite (ou pas).
```
Donne
> "Ceci est un bloc de texte mis en valeur", Lorem ipsum dolor sit amet et tout le monde connaît la suite (ou pas).

## Mettre un bloc de texte non-formaté

Il faut utiliser une tabulation au début de la ligne.
```markdown
	Ceci est un texte non formaté
```
Donne
	Ceci est un texte non formaté.

## Intégrer un bloc de code

^98c884

Pour insérer un bloc de code, on peut utiliser 3 backticks (AltGr + 7) avant et après le bloc concerné.
```
<html>
	<body>
		<h1>Hello World!</h1>
	</body>
</html>
```

On peut customiser la mise en valeur du code en précisant le langage qui sera affiché. Dans l'exemple suivant, on met en valeur le html.
```html
<html>
	<body>
		<h1>Hello World!</h1>
	</body>
</html>
```

## Les blocs de texte d'alertes

^dd6af1

Les alertes permettent un formatage automatique avec une icône et une couleur automatique. Il faut toutefois préciser que certaines ne sont pas prises en charge par Obsidian alors qu'elles le sont sur Github.

```markdown
[!important]
	Ceci est une alerte vraiment très importante !
```
Donne
>[!important]
>Ceci est une alerte vraiment très importante !

Important peut être remplacé par l'un des mots suivants selon l'information que vous souhaitez donner :
- note (icône crayon) / info (icône i) => elles s'affichent sur un fond bleu.
- tip / important => fond vert avec une icône identique sur Obsidian.
- warning / caution => fond rouge avec une icône identique sur Obsidian mais pas sur GitHub.