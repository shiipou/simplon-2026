
### Bonne démarche au départ

Se rendre sur la page [Projects](https://github.com/users/shiipou/projects/9) de notre repo collectif.

Cliquer sur la _card_ que l'on veut réaliser, elle va s'ouvrir.

Dans le menu de droite,
- dans la rubrique _**Assignees**_, cliquer sur _assign yourself_ pour signaler que vous travaillez dessus
- descendre dans le sous-menu **_Development_** et cliquer sur le lien **_Create a branch_**.

Git va créer automatiquement la branch avec son nom associé dans le kanban (l'onglet Projects du repo).

Ouvrir dans le Terminal le dossier de la vault Obsidian de notre repo collectif.

`git fetch -a` permet de prendre connaissance des nouveautés du repo.

`git switch` ou `git checkout` sur la branch (Git donne les commandes à réaliser après le clic)

La branch de la card est récupérée, on peut travailler à partir de là.

### Gestion de ma tâche tant qu'elle n'est pas terminée

`git add -A` => ajoute les fichiers et dossiers crées durant notre travail

`git commit -m "mon message clair de commit"`

`git push`

### Faire une PR (Pull Request)

Après le dernier push, Github propose automatiquement de réaliser une PR.

Saisir un titre de PR explicite. (par défaut, c'est le titre du 1er commit qui est rarement clair)

Ajouter une description claire du travail réalisé pendant la tâche.
Cliquer sur _Create a pull request_.

## Faire une review
Pour faire une review, aller dans l'onglet "_projects_" .

Dans le kanban, on voit que la PR est en cours avec une icône de branch et son numéro précédé d'un #. On clique dessus.

On lit la description pour savoir ce que la personne a fait.

Clique sur "_Files changed_". 
![[Git-Affichage-Markdown.png]]
Le bouton <> montre le markdown au format brut.
Le bouton avec la page cornée affiche le markdown au format lecture.

Les traits verts indiquent l'ajout, les traits rouge la suppression.

Bien penser à lire le chemin des fichiers et des dossiers de la tâche pour éviter les conflits lors du merge.

Clique sur le + sur la ligne (bouton bleu) où il y a un problème, et on peut faire directement une remarque attachée à cette ligne.
Si vous placez le curseur sur la ligne problématique, vous verrez au bout de la ligne une flèche qui pointe vers le bas. En cliquant dessus, vous aurez l'option "_Suggest change on line XXX_". Vous avez alors la possibilité de proposer une correction.
C'est ce que l'on appelle une conversation.

![[Git-Make-suggestion.png]]
Au choix, en passant par le bouton "_+_", l'icône à côté du _H_ permet d'ajouter une suggestion, sinon vous pouvez utiliser le menu déroulant de droite.

Quand on a terminé, on clique sur _Submit review_. On coche si on met un commentaire, si on valide (approve) ou rejeter (reject) selon le retour que l'on fait.

Si un même type d'erreur est récurrent dans le code, plutôt que de s'embêter à faire un retour à chaque ligne où le problème se trouve. On clique sur "_Submit review_" (bouton vert en haut à droite) => ajoute un commentaire global et on coche la case de rejet ou de commentaire.

On ne peut pas merge une PR si des conversations n'ont pas été résolues. Donc bien vérifier quand on ferme.

## Gérer les reviews de notre PR

Lorsqu'une conversation est en cours, on peut appliquer en un clic la correction proposée.
> [!warning]
> Tant que toutes les conversations ne sont pas résolues, le merge sera impossible.

Si on est dans le cas où les modifications à faire sont trop nombreuses, depuis notre Obsidian, on vérifie que l'on est bien sur notre branch

`git checkout maBranch`

On réalise les modifications demandées.

`Retour du git add, commit, push comme d'habitude`

Toutes les modifications que l'on envoie sont alors prise en compte par la PR. Quand c'est bon, il faut resolliciter une review de la part des personnes qui ont laissés les commentaires / conversations.

Quand la tâche est approuvé par 3 personnes, il faut cliquer sur le bouton gris "update branch".

Si jamais des conflits devaient intervenir, voir avec Flavien pour les résoudre si besoin.

### Quand la review est bonne
On clique sur :
Click sur **squash and merge**, => prend nom de la PR pas besoin de le changer.
**Confirm squash and merge** => la PR est fermée, l'issue également et la branch est supprimée.### Bonne démarche au départ

Se rendre sur la page [Projects](https://github.com/users/shiipou/projects/9) de notre repo collectif.

Cliquer sur la _card_ que l'on veut réaliser, elle va s'ouvrir.
Dans le menu de droite, descendre dans le sous-menu **_Development_** et cliquer sur le lien **_Create a branch_**.
Git va créer automatiquement la branch avec son nom associé au kanban (l'onglet Projects du repo)

Ouvrir dans le Terminal le dossier de la vault Obsidian de notre repo collectif.

`git fetch -a` permet de prendre connaissance des nouveautés du repo.

`git switch` ou `git checkout` sur la branch (Git donne les commandes à réaliser après le clic)

La branch de la card est récupérée, on peut travailler à partir de là.

### Gestion de ma tâche tant qu'elle n'est pas terminée

`git add -A` => ajoute les fichiers et dossiers crées durant notre travail

`git commit -m "mon message clair de commit"`

`git push`

### Faire une PR (Pull Request)

Après le dernier push, Github propose automatiquement de réaliser une PR.

Saisir un titre de PR explicite. (par défaut, c'est le titre du 1er commit qui est rarement clair)

Ajouter une description claire du travail réalisé pendant la tâche.
Cliquer sur _Create a pull request_.

## Faire une review
Pour faire une review, aller dans l'onglet "_projects_" .

Dans le kanban, on voit que la PR est en cours avec une icône de branch et son numéro précédé d'un #. On clique dessus.

On lit la description pour savoir ce que la personne a fait.

Clique sur "_Files changed_". 
![[Git-Affichage-Markdown.png]]
Le bouton <> montre le markdown au format brut.
Le bouton avec la page cornée affiche le markdown au format lecture.

Les traits verts indiquent l'ajout, les traits rouge la suppression.

Bien penser à lire le chemin des fichiers et des dossiers de la tâche pour éviter les conflits lors du merge.

Clique sur le + sur la ligne où il y a un problème, et on peut faire directement une remarque attachée à cette ligne.
Si vous placez le curseur sur la ligne problématique, vous verrez au bout de la ligne une flèche qui pointe vers le bas. En cliquant dessus, vous aurez l'option "_Suggest change on line XXX_". Vous avez alors la possibilité de proposer une correction.
C'est ce que l'on appelle une conversation.

![[Git-Make-suggestion.png]]
Au choix, en passant par le bouton "_+_", l'icône à côté du _H_ permet d'ajouter une suggestion, sinon vous pouvez utiliser le menu déroulant de droite.

Quand on a terminé, on clique sur _Submit review_. On coche si on met un commentaire, si on valide (_approve_) ou rejeter (_reject_) selon le retour que l'on fait.

Si un même type d'erreur est récurrent dans le code, plutôt que de s'embêter à faire un retour à chaque ligne où le problème se trouve. On clique sur "_Submit review_" (bouton vert en haut à droite) => ajoute un commentaire global et on coche la case de rejet ou de commentaire.

On ne peut pas merge une PR si des conversations n'ont pas été résolues. Donc bien vérifier quand on ferme.

## Gérer les reviews de notre PR

Lorsqu'une conversation est en cours, on peut appliquer en un clic la correction proposée.
> [!warning]
> Tant que toutes les conversations ne sont pas résolues, le merge sera impossible.

Si on est dans le cas où les modifications à faire sont trop nombreuses, depuis notre Obsidian, on vérifie que l'on est bien sur notre branch

`git checkout maBranch`

On réalise les modifications demandées.

`Retour du git add, commit, push comme d'habitude`

Toutes les modifications que l'on envoie sont alors prise en compte par la PR. Quand c'est bon, il faut resolliciter une review de la part des personnes qui ont laissés les commentaires / conversations.

Quand la tâche est approuvé par 3 personnes, il faut cliquer sur le bouton gris "update branch".

Si jamais des conflits devaient intervenir, voir avec Flavien pour les résoudre si besoin.

### Quand la review est bonne
On clique sur :
Click sur **squash and merge**, => prend nom de la PR pas besoin de le changer.
**Confirm squash and merge** => la PR est fermée, l'issue également et la branch est supprimée.