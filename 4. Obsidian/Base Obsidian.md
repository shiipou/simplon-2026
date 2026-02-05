
### Travailler sur un projet github existant

Avant tout, tu dois cloner le projet sur ton ordinateur (en local).
Ouvres un terminal (gitbash) et va dans le dossier dans lequel tu veux cloner ton projet.
Puis clone le projet :
```
git clone <url du projet>
```

Ensuite va dans le repertoire de ton projet nouvellement créer
```
cd <nom du dossier>
```

Ouvres vscode. 
```
code .
```


Dans vscode, ouvres un nouveau terminal.
Attention ne travailles pas directement sur ta branch main. Tu dois créer une nouvelle branch et basculer sur cette branch avant toute modification de code:  
```
git branch <nom de la branch>
git checkout <nom de la branch>
```

Pour aller plus vite :
```
git checkout -b <nom de la branch>
```

Cette commande créée une branch et bascule dessus


Quand c'est fait, ouvres Obsidian. Clique sur 'Open folder as vault' et selectionne le dossier de ton projet

![image de la fenêtre de création d'un nouveau vault](images/create_new_vault.png)


Si Obsidian s'ouvre automatiquement sur un document, cliques sur le nom de ta vault en bas à gauche:

<img src="images/current_vault.png" width="200px" height="50px"/>

puis clique sur 'manage vault':

<img src="images/manage_vault.png" width="300px" height="200px" />

Cela ouvrira la même fenêtre que plus haut. Tu peux maintenant cliquer sir 'Open folder as vault'
Tu es prêt à travailler!


Pour envoyer tes modifications sur le github, tu devras valider ton travail dans vscode.
Dans ton terminal ouvert dans vscode tu tapes :
```
git add .
```
 ou
 ```
git add *
 ```
  
  puis
  ```
  git commit -m "<message du commit>"
  ```


et enfin:
```
git push -u origin <nom de la branch sur laquel tu es qui ne devrais pas être main>
```

Tu peux revenir sur ta branch main:
```
git checkout main
```

pour mettre à jour ton dossier avec d'éventuelles modifications qui ont été faite sur la branch main du projet github, fais :
```
git pull
```

Inch'allah tout se passe bien, sinon tu dois résoudre les conflits. Et dans ce cas, BON COURAGE!