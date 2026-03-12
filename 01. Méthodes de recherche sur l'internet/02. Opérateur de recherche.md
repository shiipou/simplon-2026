
## Search Term

Cet opérateur recherche l'expression exacte entre guillemets uniquement. Il est idéal lorsque l'expression recherchée est ambiguë et peut facilement être confondue avec autre chose, ou lorsque les résultats obtenus ne sont pas suffisamment pertinents. Par exemple :

```
"Tinned Sandwiches"
```

## OR

Cet opérateur, dont le fonctionnement est explicite, recherche un terme de recherche donné OU un terme équivalent.

```
site:facebook.com | site:twitter.com
site:facebook.com OR site:twitter.com
```

#### AND

Cet opérateur, dont le fonctionnement est explicite, recherche un terme de recherche donné ET un terme équivalent.

```
site:facebook.com & site:twitter.com
site:facebook.com AND site:twitter.com
```

## Operators combinaison
Groups terms or operators

```
(site:facebook.com | site:twitter.com) & intext:"login"
```
```
(site:facebook.com | site:twitter.com) (intext:"login")
```


## Include results

Cela permettra de trier les résultats par nombre d'occurrences du mot-clé.

```
-site:facebook.com +site:facebook.*
```

## Exclude results

```
site:facebook.* -site:facebook.com
```

## Synonyms

Ajouter un tilde à un mot de recherche indique à Google que vous souhaitez qu'il renvoie également les synonymes de ce terme.

“~set” renverra des résultats incluant des mots comme “configure”, “collection” et “change”qui sont tous des synonymes de “set”.

```
~set
```

## Glob pattern (\*)

Mettre un astérisque dans une recherche indique à Google « Je ne sais pas ce qui se trouve ici ». En clair, c'est très pratique pour retrouver des paroles de chanson ou des noms de choses dont on se souvient à moitié.

```
site:*.com
```

---
