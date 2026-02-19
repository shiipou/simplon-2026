# Comment structurer sa recherche ?

# # Structurer sa recherche en 7 étapes :
1. **_Définir le problème_**  

==Contexte technique==
- Le langage (java, JavaSript...) 
- le framework : react, Quarkus...
- la fonctionnalité : async, routing, ORM, CORS...
- Le message d'erreur exact entre guillemets (copié-collé)
- La version si nécessaire

==Comportement attendu== 
Ce que ton code devrait faire

==Comportement observé==
Ce qu'il fait réellement

==Message d'erreur exact ==
Copié-collé, entre guillemets

==Ce que tu as déjà essayé==
Pour éviter de tourner en rond


2. **_ Extraire les mots clés_** 
Tu dois extraire les éléments techniques qui vont guider ta recherche, dont :

- Le langage
- Le framework
- La fonctionnalité ciblée
- Le message d’erreur exact
- La version si elle influence le comportement
- Le concept technique (async, CORS, routing, ORM…)


==Plusieurs structures sont ensuite possibles, selon le problème rencontré== :
Technologie + problème + le contexte 
Technologie + concept + erreur
Langage + fonction + comportement attendu
Framework + mot clé +version

==Exemple == 

react 18 + useEffect + infinite loop


3. **_Construire une requête efficace_**

Combiner les mots-clés de façon structurée (ci-dessus) +opérateurs/filtres de recherche (cf les 2 documentations)

3.**_ Cibler les bonnes sources_**
- ==La documentation officielle ==: toujours commencer par ça, mdn, React Docs, Python Docs
- ==GitHub Issues== : c'est une bibliothèque de bug (bugs connus, limitations, workarounds, discussions entre mainteneurs). La réponse se trouve souvent dans l'onglet « Problèmes » du dépôt, et non sur Google. 
- ==Stack Overflow ==: pour les bugs spécifiques, les cas concrets, erreurs, edge cases. 
  Attention : toujours rechercher la coche verte ✅,  le nombre de votes positifs et toujours vérifier la date 
- ==Blogs techniques ==(Medium, Dev.to, freeCodeCamp, DigitalOcean) : utiles pour les tutoriels « pratiques ».
  Attention aux articles obsolètes. 
- ==Forums obscurs / spam SEO== : à éviter (contenu souvent généré automatiquement).


4. **_Vérifier et croiser_**
- ==La date== 
Exemple : un article React de 2018 est souvent obsolète
- ==La version ==
React 17 et React 18
- ==La cohérence==
Vérifier si plusieurs sources donnent le même résultat, si c'est le cas c'est bien parti !
- ==Les commentaires== 
Sur StackOverflow, ils corrigent souvent la réponse, pour éviter les fausses pistes et les solutions périmées.


4. **_Tester_**
Une solution peut marcher dans un contexte mais pas dans celui recherché, c'est pourquoi effectuer des tests permet de valider avant d'intégrer.
==La démarche à suivre== : 
- Trouver une piste
- Tester dans un environnement isolé (projet test...)
- Observer ce qui se passe
- Ajuster la recherche si nécessaire

5. **_Documenter_**
L'objectif est de parfaire ses connaissances et ses pratiques, d'où l'importance de créer des notes (sous obsidian, sous forme de commentaire dans le code...) à chaque problème rencontré.
Les notes peuvent contenir cette trame :
- La cause du problème
- La solution
- un snippet minimal (aoerçu d'une page qui apparait dans les résultats de recherche, souvent en haut de la liste des sites pertinents)
- un lien vers la source
- la version concernée

### En résumé :

|Etape 



