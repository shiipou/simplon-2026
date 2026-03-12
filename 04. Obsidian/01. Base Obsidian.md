
## Travailler avec un projet existant

Avant tout, tu dois cloner ton projet sur ton ordinateur (en local).
Ouvre un terminal, rend toi dans le dossier dans lequel tu veut cloner ton projet.
Puis clone ton projet:
```
git clone <url du projet>
```

Rends toi dans le dossier nouvellement créé :
```
cd <nom du dossier>
```

Ne travaille jamais sur ta branch 'main'. Tu dois créer une nouvelle branch et te rendre dedans :
```
git branch <nom de la branch>
git checkout <nom de la branch>
```

Pour aller plus vite :
```
git checkout -b <nom de la branch>
```

Cette commande créé une branch et va directement dedans.

Une fois cela fait, ouvres obsidian. Cliques sur **Open** et selectionne le dossier de ton projet

![image de la fenêtre de création d'un nouveau vault](images/create_new_vault.png)




Si tu es déjà dans une vault (si obsidian ouvre automatiquement un document sur lequel tu travaillais), cliques sur le nom de la vault en cours en bas à gauche

<img src="images/current_vault.png" width="200px" height="50px"/>

Puis cliques sur **manage vault**

<img src="images/manage_vault.png" width="300px" height="200px" />

Cela ouvrira la même fenêtre que si tu démarrais obsidian pour la première fois. Maintenant tu peux cliquer sur **open** et selectionnes le dossier de ton projet

Tu es prêt à travailler.
