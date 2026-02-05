# Qu’est‑ce que le système Git
https://git-scm.com/ est un système de gestion de versions libre et Open Source. Il permet d’apporter de l’agilité, de l’organisation au travail, ainsi qu’un suivi simple des versions de fichiers, des problèmes (issues) et des mises à jour d’un projet.
# Comment l’utiliser
Il existe plusieurs alternatives pour utiliser le système Git, telles que :

https://git-scm.com/
https://github.com/
GitLab
…

Certaines utilisent des interfaces web ou applicatives (GUI), ou des commandes bash (CLI), et peuvent souvent être intégrées (comme des plugins ou autres) dans un IDE/éditeur pour un accès plus simple et un gain de temps.
Ces alternatives sont quasiment toujours disponibles à la fois sur les systèmes basés sur Solaris (Linux, macOS, …) et sur les systèmes Windows.
# Architecture Git
## Structure des branches Git :
Un projet est divisé en une ou plusieurs branches :

Il est d’abord composé d’une branche principale/origin, qui représente le début du projet.
Ensuite, le projet peut être divisé grâce à ce que l’on appelle des branches, permettant d’éditer des fichiers en parallèle du projet principal sans soumettre des modifications pouvant causer divers problèmes.

## Structure du transit des fichiers Git :
L’architecture Git peut sembler compliquée au premier abord, mais elle est en réalité assez simple à comprendre. Elle est composée de :

Un dépôt (repo) hébergé sur des serveurs distants
Un stash (peut être traduit par « réserve ») : il contient des informations intermédiaires afin d’éviter des problèmes de versionnage involontaires
Un espace de travail local où l’on peut récupérer ou envoyer des fichiers

# Gestion des conflits Git
Git permet aux utilisateurs de gérer facilement les conflits, en conservant les fichiers dans le stash pendant que l’utilisateur choisit quelles modifications conserver ou supprimer.
Les branches servent également à éviter les “spaghettis” et à garder une branche origin propre, notamment en utilisant des “branch squash” ou des “branch rebase” (n’utilisez pas rebase si vous n’êtes pas sûr de ce que vous faites !).