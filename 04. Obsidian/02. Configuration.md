## Création d'un vault principal

### Objectif
-  **1 seul vault Obsidian global**
-  organisé par dossiers (projets, formation, perso…)
-  synchronisé via **Git**
-  utilisable sur **plusieurs postes**
-  avec **UNE configuration unique** (thème, plugins, raccourcis…)

### Nettoyage
Pour repartir sainement :
- Fermer obsidian
- Supprimer ou mettre de côté les anciens vault
- Choisir **UN dossier racine** , par exemple :
```
Documents/Obsidian
```
### Créer la structure du vault global
Dans l'explorateur de fichiers, créer :
```
Documents/Obsidian/Second-Cerveau
```
A l'intérieur :
```
Second-Cerveau/
├── Projets/
├── Formation/
├── Ressources/
├── Journal/
```

Dans chaque dossier créer un fichier .placeholder qui permettra de conserver l'architecture au moment de cloner le repo Git.
Le dossier **Second-cerveau** sera le vault unique qui servira de repo Git et de base de connaissance.

### Créer le vault Obsidian
- Ouvrir Obsidian
- Open folder as vault
- Sélectionner :
```
Documents/Obsidian/Second-Cerveau
```

### Configuration de base Obsidian
Configurer maintenant :
- thème
- langue
- plugins natifs
- plugins communautaires (Git, Template, Dataview plus tard)
- raccourcis
- snippets CSS si besoin
Tout sera stocké dans :
```
Second-Cerveau/.obsidian/
```

## Déposer le vault principal dans un repo Git
### Initialiser Git (**AU BON ENDROIT**)
Ouvrir un terminal **dans le dossier Second-Cerveau** :
```
cd "Documents/Obsidian/Second-Cerveau"
git init
```
Vérifier l'absence d'erreur:
```
git status
```

### Créer le .gitignore (indispensable)
A la racine du vault, créer le fichier :
```
.gitignore
```
Contenu recommandé :
```
.obsidian/cache
.obsidian/workspace.json
.obsidian/workspace-mobile.json
```

### Premier commit
Toujours dans ==Second-cerveau== :
```
git add .
git commit -m "Initialisation du vault Obsidian global"
```

### Dépot distant (GitHub)
- Créer un repo privé sur GitHub
Par exemple :
```
second-cerveau-obsidian
```
⚠️ Ne rien initialiser côté GitHub
- Puis dans le terminal :
```
git remote add origin git@github.com:TON-COMPTE/second-cerveau-obsidian.git
git branch -M main
git push -u origin main
```

### Installer et configurer Obsidian Git
Dans Obsidian :
- Paramètres -> Community plugins
- Installer **Obsidian Git**
- Configuration conseillée :
	- Auto commit : ON
	- Intervalle: 10 min
	- Auto pull on startup
	- Autopush on commit
	- Message: ==Auto-save Obsidian==
### Utilisation sur un autre poste
Sur un autre ordinateur :
- Créer un dossier (Obsidian par exemple) sur le poste
- Ouvrir un Git Bash dans ce dossier 
- Cloner le repo GitHub
```
git clone git@github.com:TON-COMPTE/second-cerveau-obsidian.git
```
Puis:
- Ouvrir Obsidian
- Open folder as vault
- Sélectionner le dossier cloné

### Règles d’or (à respecter)
- Un seul vault ouvert à la fois  
- Pas de modifications simultanées sur 2 machines  
- Laisser Obsidian Git finir ses commits  
- Repo privé si notes perso


