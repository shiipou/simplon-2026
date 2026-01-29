
## relier obsidian à un projet github

### Création de votre projet

Avant tout, il va falloir cloner votre projet en local.
Dans un terminal ( gitbash ), rends toi dans le repertoire dans lequel ton projet sera cloner. Puis clone ton projet (repository):

```
git clone <url du projet>
```

Puis rends toi dans le dossier du projet : 
```
cd <nom du dossier>
```

On ne va pas travailler sur la branch main. Tu vas créer une nouvelle branch pour travailler dessus:
```
git branch <nom de la branch>
git checkout <nom de la branch>
```

Pour aller plus vite :
```
git checkout -b <nom de la branch>
```

Cette commande fait les deux commandes précédente en une. 

Une fois cela fait, ouvres obsidian. Si obsidian te propose de créer un nouveau vault ou d'en ouvrir un, cliques sur **open** et indique lui le dossier de ton projet. Cela ouvrira dan obsidian le projet. 

Si tu étais déjà dans un vault et que obsidian au démarrage a ouvert automatiquement le document sur lequel tu travaillais, clique en bas à gauche sur le **nom de ta vault** (avec les petits chevrons haut bas), puis **manage vault**. Cela ouvrira la même fenêtre que si tu démarrais obsidian pour la première fois et tu pourras ouvrir ton projet comme écrit au dessus (cliques sur **open**).

Tu es prêts à travailler !
