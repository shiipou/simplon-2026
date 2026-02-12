
### argument de commande

Pour saisir des instructions Linux et les faire exécuter par le système, il faut préalablement ouvrir une ligne de commande (CLI). Il s’agit en effet d’un terminal qui permet aux utilisateurs d’écrire les commandes pour dicter à la machine les actions à réaliser.

Ce composant de base des systèmes d’exploitation ou OS s’affiche généralement à l’écran sous forme d’une console noire. Le Shell quant à lui est l’interpréteur de ligne de commandes qui fait le lien avec le noyau Linux. Il traite les lignes de commandes Linux pour les comprendre et les exécuter.

Dans la barre de recherche des applications, vous pouvez facilement trouver un interpréteur de commande avec le mot clé « terminal ». Différents raccourcis permettent également de directement ouvrir une ligne de commande. Essayez « Ctrl + Alt + t » sur Ubuntu par exemple.

Ce programme est aussi accessible dans la section Utilitaires sur toutes les distributions Linux. Le premier message qui s’affiche au lancement de la console est appelé invite de commande. Avec une fonction claire, il donne des indications sur :

- Le nom de l’utilisateur ;
- Le nom de la machine ;
- La nature du dossier courant (personnel ou étranger) ;
- Le mode de connexion (simple utilisateur ou super utilisateur).

Une fois le terminal ouvert, vous pourrez utiliser l’une des nombreuses commandes Linux pour réaliser diverses actions. Pour la plupart, elles acceptent des paramètres (ou arguments) qui sont précédés d’un simple espace dans la syntaxe de la ligne de commande.

Ces paramètres sont majoritairement des chemins d’accès vers des documents ou fichiers. Les commandes Linux utilisent également des flags qui sont quant à eux précédés d’un (-) ou deux tirets (–). Ils spécifient certaines options sur ces instructions.

## **34 commandes Linux à connaître**

Voici les commandes Linux de base que vous vous devez de connaître.

### **1 – La commande ls**

La commande « ls » est la première que de nombreux utilisateurs de Linux saisissent dans leur interpréteur de commandes. Cette commande affiche par défaut le contenu du répertoire courant. Il est toutefois possible d’afficher le contenu d’un dossier spécifique en indiquant son chemin d’accès en argument.

Cette instruction a de multiples options que vous pouvez toutes découvrir avec le flag « –help ». Comme options de la commande ls, on distingue entre autres :

- ls – l : donne des informations sur les fichiers dans chacun des répertoires ;
- ls – al : liste les fichiers et répertoires avec des informations détaillées ;
- ls -R : affiche également le contenu des sous-répertoires.

![Command Linux 'ls'](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linus-ls.jpg)

Command Linux ‘ls’



![Command Linux 'ls' - resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linus-ls-resultat.jpg)

Command Linux ‘ls’ – resultat

Enfin, la sortie de cette commande peut se faire en couleur avec l’instruction « ls –color=auto ».

### **2 – La commande cd**

« cd », pour _Change Directory_, est également une commande très utilisée sur le CLI Linux. Cette commande permet en effet de changer le répertoire courant.

Selon le répertoire dans lequel vous vous trouvez, vous aurez besoin du nom du répertoire où vous allez ou encore de son chemin d’accès complet. On distingue quelques raccourcis intéressants avec cette instruction Linux :

- cd- : permet de passer au répertoire précédent ;
- cd.. : permet de passer au répertoire directement plus haut dans l’arborescence ;
- cd : permet de se rendre au dossier principal (home).

![Command Linux cd](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cd.png)

Command Linux ‘cd’

![Command Linux cd Resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cd-resultat.png)

Command Linux ‘cd’ – resultat

Notez également que l’interpréteur de commandes Linux est sensible à la casse. En d’autres termes, il fait une différence entre les caractères en majuscule et en minuscule. Tenez-en compte aussi bien au niveau de l’écriture des commandes que des chemins d’accès.

### **3 – La commande pwd**

La commande « pwd » est un diminutif de _Print Working Directory_. Comme son nom l’indique, sans argument et sans flag, cette commande retourne le chemin absolu complet du répertoire de travail dans lequel on se trouve. Le résultat obtenu peut être copié pour servir à d’autres usages.

![Command Linux pwd](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-pwd.png)

Command Linux ‘pwd’

![Command Linux pwd Resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-pwd-resultat.png)

Command Linux ‘pwd’ – resultat

### **4 – La commande cat**

Abréviation de _Concatenate_, la commande « cat » est aussi très utilisée. Si elle sert souvent à prévisualiser un fichier sans ouvrir un éditeur de texte, elle permet essentiellement de créer, d’afficher et de concaténer des fichiers en ligne de commande.

De plus, la ligne “cat _nomDuFichier.extension_” affiche le contenu d’un fichier. Cette commande offre également d’autres options pour le traitement de textes. Elle peut par exemple afficher les numéros de ligne ou supprimer les lignes d’un fichier dans la mesure où elles sont vides.

![Command Linux cat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cat.png)

Command Linux ‘cat’

![Command Linux cat Resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cat-resultat.png)

Command Linux ‘cat’ – resultat

### **5 – La commande cp**

Pour copier un fichier du répertoire courant ou non, utilisez la commande « cp ». Le premier paramètre prend le nom et l’extension du fichier à copier ou encore son chemin absolu.

Le second paramètre quant à lui est le nom et l’extension du fichier de destination. Il peut également s’agir du chemin absolu du répertoire de destination. Cette commande permet de copier des répertoires grâce à l’option - r. Ces derniers se terminent par une barre oblique sous Linux (/).

![Command Linux cp](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cp.png)

Command Linux ‘cp’

![Command Linux cp Resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cp-resultat.png)

Command Linux ‘cp’ – resultat

---

![Command Linux cp](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cp-directory.png)

Command Linux ‘cp’

![Command Linux cp Resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-cp-resultat-directory.png)

Command Linux ‘cp’ – resultat

### **6 – La commande mkdir**

L’instruction « mkdir » pour _Make Directory_ permet de créer un nouveau dossier dans le répertoire courant. Spécifiez le nom du nouveau répertoire et assurez-vous qu’il n’existe pas encore. Par exemple, faites « mkdir Articles/ » pour créer un répertoire nommé « Articles ».

Pour créer des répertoires avec des sous-répertoires, ajoutez le flag « -p ». Avec la commande « mkdir -p Articles/Baskets/ », vous créerez un répertoire « Articles » qui en contient un autre nommé « Baskets ».

![Command Linux mkdir](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mkdir.png)

Command Linux ‘mkdir’

![Command Linux mkdir verifier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mkdir-verifier.png)

Command Linux ‘mkdir’ – verifier

![Command Linux mkdir resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mkdir-verifier-resultat.png)

Command Linux ‘mkdir’ – resultat

### **7 – La commande mv**

Si la commande « mv » sert principalement à déplacer des fichiers ou répertoires, elle permet également de les renommer. Comme avec « cp », il faut, à la suite de l’instruction « mv », spécifier la source et la destination.

Pour copier un dossier en entier, il vous suffira d’ajouter l’option r et d’indiquer le nom du fichier ou répertoire en argument.

![Command Linux mv Renommer un fichier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mv-renommer-un-fichier.png)

Command Linux ‘mv’ – Renommer un fichier

![Command Linux mv Déplacer un fichier dans un autre répertoire](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mv-deplacer-un-fichier-dans-un-autre-repertoire.png)

Command Linux ‘mv’ – Déplacer un fichier dans un autre répertoire

![Command Linux mv Déplacer un répertoire](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-mv-deplacer-un-repertoire.png)

Command Linux ‘mv’ – Déplacer un répertoire

### **8 – La commande rm**

« rm » permet la suppression de fichiers et même d’un répertoire. Faites toutefois attention à l’usage de cette commande, car elle peut avoir des actions irréversibles.

Ajoutez le nom et l’extension d’un fichier ordinaire en paramètre pour le supprimer. La commande « rm -r » permet de supprimer des répertoires vides. Elle se comporte donc comme la commande « rmdir ».

Quant à la suppression d’un répertoire avec son contenu, ajoutez le flag force. « rm -rf Liste/ » permettrait ainsi de supprimer un répertoire nommé « Liste » avec tout son contenu.

![Command Linux rm Suppression d'un fichier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-rm-suppression-d-un-fichier.png)

Command Linux ‘rm’ – Suppression d’un fichier

![Command Linux rm Supprimer un répertoire et son contenu](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-rm-supprimer-un-repertoire-et-son-contenu.png)

Command Linux ‘rm’ – Supprimer un répertoire et son contenu

![Command Linux rm Suppression d'un fichier sans invite](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-rm-suppression-d-un-fichier-ans-invite.png)

Command Linux ‘rm’ – Suppression d’un fichier sans invite

### **9 – La commande man**

Le terminal Linux a tout prévu pour vous permettre de bien utiliser chacune de ses commandes. La commande « man » affiche la page du manuel de toutes les autres commandes. Avec « man alias » par exemple, vous aurez tous les détails sur les fonctions de l’instruction « alias ».

![Command Linux man](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-man.png)

Command Linux ‘rm’

![Command Linux man resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-man-resultat.png)

Command Linux ‘man’ – resultat

### **10 – La commande alias, unalias**

La création et la suppression d’alias est possible respectivement avec les commandes Linux « alias » et « unalias ». Avec cet OS open source, un alias est un mot qui remplace une série de commandes.

#### **Commande Linux alias**

La commande Linux « alias » définit des alias temporaires dans une section du Shell. Depuis votre interface en ligne de commande, tapez « alias ls=”ls –color=auto” » par exemple. Les sorties de « ls » seront systématiquement en couleur sans que vous ayez besoin d’utiliser le flag à chaque fois.

Cette commande prend ainsi en paramètre une chaîne clé-valeur. Sans arguments, cette commande renvoie plutôt la liste de tous les alias actifs dans la section.

![Command Linux alias](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-alias.png)

Command Linux ‘alias’

![Command Linux alias resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-alias-resultat.png)

Command Linux ‘alias’ – resultat

#### **Commande Linux unalias**

Pour désactiver un alias par contre, saisissez la commande Linux « unalias » suivi de l’alias à supprimer. Vous pourriez ainsi faire un « unalias ls » pour supprimer l’alias « ls » créé.

![Command Linux unalias](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-unalias.png)

Command Linux ‘alias’

![Command Linux unalias resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-unalias-resultat.png)

Command Linux ‘unalias’ – resultat

### **11 – La commande touch**

Dans le lot des principales commandes Linux, « touch » permet la création d’un fichier vierge sur un terminal de Linux. Cette commande est aussi connue pour mettre à jour les temps d’accès et de modifications des fichiers. Cette seconde fonction de la commande n’est toutefois que peu connue.

![Command Linux touch](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-touch.png)

Command Linux ‘touch’

![Command Linux touch plusieurs fichiers](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-touch-plusieurs-fichiers.png)

Command Linux ‘touch’ – plusieurs fichiers

### **12 – La commande chmod**

Les permissions de lecture (r), d’écriture (w) et d’exécution (x) de répertoires et de fichiers ont une grande importance sur Linux. Cette commande Linux permet de gérer et de changer ces permissions.

Pour rendre un fichier exécutable par exemple, il faut faire « chmod +x » suivi du nom du fichier concerné.

![Command Linux chmod](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chmod.png)

Command Linux ‘chmod’

![Command Linux chmod vérifier les permissions du fichier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chmod-verifier-les-permissions-du-fichier.png)

Command Linux ‘chmod’ – vérifier les permissions du fichier

![Command Linux chmod vérifier resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chmod-verifier-resultat.png)

Command Linux ‘chmod’ – vérifier resultat

### **13 – La commande chown**

Vous pouvez changer ou transférer la propriété d’un fichier à un utilisateur donné avec « chown ». Tous les fichiers sous GNU/Linux sont en effet rattachés à un _user_ spécifique.

Cette commande prend en premier argument le nom du nouvel utilisateur et en second le nom du fichier dont on veut transférer la propriété.

![Command Linux chown](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chown.png)

Command Linux ‘chown’

![Command Linux chown vérifier la propriété du fichier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chown-verifier-la-propriete-du-fichier.png)

Command Linux ‘chown’ – vérifier la propriété du fichier

![Command Linux chown vérifier resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-chown-verifier-resultat.png)

Command Linux ‘chown’ – vérifier resultat

### **14 – La commande ./**

Si la notation « ./ » n’est pas réellement une commande, elle a une grande importance. Elle permet en effet à n’importe quel interpréteur de ligne de commande Linux l’exécution d’un fichier. Vous pourriez toutefois avoir besoin de changer la permission d’exécution avant de le faire.

![Command Linux ./](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-dot-slash.png)

Command Linux ‘./’

![Command Linux ./ resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-dot-slash-resultat.png)

Command Linux ‘./’ resultat

### **15 – La commande exit**

Comme son nom l’indique, la commande « exit » met fin à une section du Shell sur Linux. Généralement, cette commande s’accompagne aussi de la fermeture de la console Linux.

![Command Linux exit](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-exit.png)

Command Linux ‘exit’

![Command Linux exit resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-exit-confirmir.png)

Command Linux ‘exit’ – resultat

### **16 – La commande shutdown**

« shutdown » permet d’éteindre une machine fonctionnant sous une distribution de Linux. Elle peut aussi la redémarrer immédiatement ou à une heure programmée. Le temps d’attente par défaut est d’une minute.

Vous pouvez toutefois utiliser le paramètre « now » avec cette commande Linux pour une mise hors tension instantanée. Indiquez plutôt « 22 : 35 » pour attendre cette heure-là avant l’extinction. Le flag « -c » quant à lui permet d’annuler une mise sous tension programmée.

![Command Linux shutdown](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-shutdown.png)

Command Linux ‘shutdown’

![Command Linux shutdown reussie](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-shutdown-reussie.png)

Command Linux ‘shutdown’ – reussie

### **17 – La commande locate**

Pour simplifier la localisation d’un fichier ou un répertoire sur une machine Linux, il faut utiliser la commande Linux « locate ». L’ajout du flag « -i » rend la recherche insensible à la casse. Il y a de nombreuses autres options de recherche.

![Command Linux locate](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-locate.png)

Command Linux ‘locate’

![Command Linux locate resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-locate-resultat.png)

Command Linux ‘locate’ – resultat

### **18 – La commande find**

La commande « find » se comporte comme la commande « locate » à quelques différences près. La principale différence est que cette commande recherche des fichiers dans un répertoire donné. La commande permet de multiples options pour affiner la recherche.

![Command Linux find](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-find.png)

Command Linux ‘find’

![Command Linux find resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-find-resultat.png)

Command Linux ‘find’ – resultat

### **19 – La commande sudo**

Si vous avez un niveau intermédiaire en Linux, vous avez sans doute déjà entendu parler de la commande « sudo » pour _SuperUser Do_. Cette commande permet d’exécuter des tâches qui requièrent des droits administrateur ou root.

Elle vous permettra d’effectuer plusieurs opérations pouvant endommager de manière irréversible votre système Linux. Utilisez là donc de manière intelligente et réfléchie.

![Command Linux sudo](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-sudo.png)

Command Linux ‘sudo’

![Command Linux sudo resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-sudo-resultat.png)

Command Linux ‘sudo’ – resultat

### **20 – La commande df**

Retrouvez en Kilo octets (Ko) les détails du pourcentage d’utilisation de l’espace disque de votre système. Vous pourrez plutôt les avoir en Méga octets (Mo) avec « df -m ».

![Command Linux df](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-df.png)

Command Linux ‘df’

![Command Linux df resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-df-resultat.png)

Command Linux ‘df’ – resultat

### **21 – La commande du**

« du » pour _Disk Usage_ par contre permet de connaître l’espace mémoire qu’un fichier ou répertoire occupe sur un disque. Vous pouvez ajouter le flag « -h » à la commande “du” pour avoir cette valeur en octets, Ko ou Mo.

![Command Linux du](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-du.png)

Command Linux ‘du’

![Command Linux du resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-du-resultat.png)

Command Linux ‘du’ – resultat

### **22 – La commande head**

La commande Linux « head » permet de visualiser les premières lignes d’un fichier texte. Si cette commande affiche les 10 premières lignes par défaut, on peut aisément modifier ce nombre à sa convenance. Avec « head -n 6 » suivi du nom et de l’extension, les 6 premières lignes du fichier s’afficheront.

![Command Linux head](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-head.png)

Command Linux ‘head’

![Command Linux head resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-head-resultat.png)

Command Linux ‘head’ – resultat

### **23 – La commande diff**

Vous pourrez comparer ligne par ligne deux fichiers dans un terminal Linux. La commande « diff » permet de le faire, mais elle n’affiche que les lignes qui ne concordent pas en sortie.

Cette commande est par sa fonction très utilisée par les développeurs. Pour s’en servir, il faut écrire la syntaxe de la commande et passer successivement les fichiers à comparer en paramètre.

![Command Linux diff](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-diff.png)

Command Linux ‘diff’

![Command Linux diff resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-diff-resultat.png)

Command Linux ‘diff’ – resultat

### **24 – La commande jobs**

La commande « jobs » en ligne de commande peut être utilisée pour avoir la liste de tous les programmes qui s’exécutent sur un système Linux.

![Command Linux jobs](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-jobs.png)

Command Linux ‘jobs’

![Command Linux jobs resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-jobs-resultat.png)

Command Linux ‘jobs’ – resultat

### **25 – La commande top**

« top » liste et affiche le nom de tous les processus en cours d’exécution sur une machine Linux avec le détail de la quantité de CPU utilisée. Cette commande est très pratique pour suivre l’utilisation des ressources du système. Elle permet aussi d’identifier les programmes qui doivent être arrêtés en cas de surconsommation.

![Command Linux top](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-top.png)

Command Linux ‘top’

![Command Linux top resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-top-resultat.png)

Command Linux ‘top’ – resultat

### **26 – La commande kill**

Pour arrêter un programme Linux en qui ne répond pas ou qui consomme énormément de mémoire RAM, vous pouvez utiliser la commande « kill » Cette commande est si puissante qu’elle peut être utilisée pour forcer la fermeture d’une session. Il faudra bien sûr suivre certaines indications pour bien s’en servir.

![Command Linux kill](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-kill.png)

Command Linux ‘kill’

![Command Linux kill forcer l'arrêt](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-kill-forcer-l-arret.png)

Command Linux ‘kill’ – forcer l’arrêt

### **27 – La commande ping**

Les administrateurs de réseaux informatiques connaissent très bien la commande « ping ». Cette commande permet de vérifier le statut de la connectivité à un serveur et de mesurer le temps de réponse.

![Command Linux ping](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-ping.png)

Command Linux ‘ping’

![Command Linux ping resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-ping-resultat.png)

Command Linux ‘ping’ – resultat

### **28 – La commande wget**

En ligne de commande, vous pouvez utiliser « wget » pour lancer un téléchargement sur internet. Il suffit d’ajouter le lien de téléchargement en paramètre.Cette commande permet de tout télécharger, que ce soit un site web, une vidéo ou une image.

![Command Linux wget](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-wget.png)

Command Linux ‘wget’

![Command Linux wget resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-wget-resultat.png)

Command Linux ‘wget’ – resultat

### **29 – La commande hostname**

La commande « hostname -I » vous permettra d’identifier l’adresse IP de votre réseau. Utilisée sans ce flag, elle affiche le nom de votre hôte ou réseau. Toutefois, pour utiliser cette commande, il faut disposer des droits d’utilisateur root.

![Command Linux hostname](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-hostname.png)

Command Linux ‘hostname’

![Command Linux hostname resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-hostname-resultat.png)

Command Linux ‘hostname’ – resultat

### **30 – La commande uname**

« uname » donne des informations intéressantes et utiles sur le système d’exploitation utilisé. Il s’agit entre autres de l’OS, du noyau et du nom de la machine.

![Command Linux uname](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-uname.png)

Command Linux ‘uname’

![Command Linux uname resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-uname-resultat.png)

Command Linux ‘uname’ – resultat

### **31 – La commande history**

Vous pouvez retrouver l’historique des commandes Linux entrées auparavant grâce à la commande « history ». Cette commande est très pratique compte tenu du fait qu’on est souvent amené à exécuter des centaines de commandes au quotidien.

La commande “history” vous permettra de retrouver jusqu’à 500 lignes de commande. En manipulant habilement les flags, vous pourrez aisément retrouver une commande particulière.

![Command Linux history](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-history.png)

Command Linux ‘history’

![Command Linux history resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-history-resultat.png)

Command Linux ‘history’ – resultat

### **32 – La commande echo**

La commande « echo » déplace ou ajoute des données comme du texte dans un fichier spécifique. Cette commande est l’une des plus basiques et des plus utilisées car elle permet d’avoir accès au contenu d’un fichier sans avoir à l’ouvrir.

![Command Linux echo](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-echo.png)

Command Linux ‘echo’

![Command Linux echo resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-echo-resultat.png)

Command Linux ‘echo’ – resultat

---

![Command Linux echo afficher les variables](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-echo-afficher-les-variables.png)

Command Linux ‘echo’ – afficher les variables

![Command Linux echo afficher les variables resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-echo-afficher-les-variables-resultat.png)

Command Linux ‘echo’ – afficher les variables resultat

### **33 – La commande zip, unzip et tar**

Pour compresser des fichiers dans une archive zip et pour extraire des données d’un fichier zippé, il faut respectivement utiliser « zip » et « unzip ». Si vous recherchez une alternative à ces dernières, la commande « tar » est une excellente option, bien qu’elle soit plus complexe à utiliser.

![Command Linux zip](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-zip.png)

Command Linux ‘zip’

![Command Linux zip resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-zip-resultat.png)

Command Linux ‘zip’ – resultat

---

![Command Linux unzip](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-unzip.png)

Command Linux ‘unzip’

![Command Linux unzip resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-unzip-resultat.png)

Command Linux ‘unzip’ – resultat

### **34 – Le lot de commandes groupadd, groupmod, useradd, userdel, usermod**

Ce lot de commandes est indispensable à tout administrateur système. Il permet à ce dernier de gérer chaque utilisateur présent sur son réseau. Les commandes peuvent aussi être utilisées pour limiter l’accès aux utilisateurs au contenu d’un fichier ou un répertoire spécifique.

Par exemple, utilisez la commande « useradd » pour créer un nouvel utilisateur et « passwd » pour assigner un mot de passe à ce compte. « userdel » par contre permet de supprimer un utilisateur. La commande “groupmod” elle, vous permet de modifier un groupe existant sur votre machine.

![Command Linux groupadd](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-groupadd.png)

Command Linux ‘groupadd’

![Command Linux groupadd vérifier](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-groupadd-verifier.png)

Command Linux ‘groupadd’ – vérifier

![Command Linux groupadd vérifier resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-groupadd-verifier-resultat.png)

Command Linux ‘groupadd’ – vérifier resultat

---

![Command Linux groupmod](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-groupmod.png)

Command Linux ‘groupmod’

![Command Linux groupmod resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-groupmod-resultat.png)

Command Linux ‘groupmod’ – resultat

---

![Command Linux useradd](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-useradd.png)

Command Linux ‘useradd’

![Command Linux useradd resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-useradd-resultat.png)

Command Linux ‘useradd’ – resultat

---

![Command Linux userdel](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-userdel.png)

Command Linux ‘userdel’

![Command Linux userdel resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-userdel-resultat.png)

Command Linux ‘userdel’ – resultat

---

![Command Linux usermod](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-usermod.png)

Command Linux ‘usermod’

![Command Linux usermod resultat](https://blog.lesjeudis.com/wp-content/uploads/2023/03/command-linux-usermod-resultat.png)

Command Linux ‘usermod’ – resultat

## **Les bonnes astuces à utiliser sur un terminal Linux**

Lorsque vous exécutez des commandes Linux, il est assez courant de se retrouver avec une console visuellement chargée. Vous pouvez utiliser la commande « clear » pour vider les messages à l’écran du terminal.

Linux propose aussi des suggestions ou auto complétions pertinentes avec la touche tabulation « Tab » du clavier. Par ailleurs, comme raccourcis clavier, vous pouvez utiliser :

- Ctrl + A pour aller au début de la ligne ;
- Ctrl + E pour aller à la fin de la ligne ;
- Ctrl + Z pour mettre une commande en cours d’exécution en pause ;
- Ctrl + C pour arrêter une commande en cours d’exécution ;
- Ctrl + E pour aller à la fin de la ligne ;
- Ctrl + S pour bloquer le terminal ;
- Ctrl + Q pour débloquer le terminal.

Par ailleurs, plutôt que d’exécuter des commandes Linux les unes après les autres, vous pouvez les exécuter en une seule ligne en les séparant par des « ; ». Utilisez plutôt « && » si vous souhaitez que la commande suivante s’exécute à condition que la précédente ait abouti.

## **Conclusion**

Si l’apprentissage des principales commandes Linux peut prendre un certain temps, le processus est relativement simple et assez agréable.

En effet, vous parviendrez vite à maîtriser les commandes et les principaux outils Linux. Toutefois, vous ne cesserez jamais d’apprendre et de découvrir de nouvelles choses avec ce puissant système d’exploitation.

En attendant, connaître et maîtriser les principales commandes Linux devrait grandement améliorer votre productivité et être d’une grande utilité.



