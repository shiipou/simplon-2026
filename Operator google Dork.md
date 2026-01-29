
## Search Term

This operator searches for the exact phrase within speech marks only.  This is ideal when the phrase you are using to search is ambiguous and  could be easily confused with something else, or when you’re not quite  getting relevant enough results back. For example:

```
"Tinned Sandwiches"
```

## OR
This self explanatory operator searches for a given search term OR an equivalent term.

```
site:facebook.com | site:twitter.com
site:facebook.com OR site:twitter.com
```

#### AND

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

This will order results by the number of occurrence of the keyword.

```
-site:facebook.com +site:facebook.*
```

## Exclude results

```
site:facebook.* -site:facebook.com
```

## Synonyms

Adding a tilde to a search word tells Google that you want it to bring back synonyms for the term as well.

“~set” will bring back results that include words like “configure”, “collection” and “change” which are all synonyms of “set”.

```
~set
```

## Glob pattern (\*)

Putting an asterisk in a search tells Google ‘I don’t know what goes here’. Basically, it’s really good for finding half remembered song lyrics or names of things.

```
site:*.com
```

---
source: https://haft.fr/Knowledge-Notes/google-dorks#operators