# Elasticsearch

### Comment ça marche vraiment ?


---

## Au programme

1. C'est quoi Elasticsearch ?
2. Elasticsearch vs PostgreSQL
3. Document & Index
4. Shards & Réplicas
5. Le Mapping
6. `text` vs `keyword`
7. Le score de pertinence
8. La stack ELK
9. Applications concrètes

---

## C'est quoi Elasticsearch ?

Moteur de **recherche et d'analyse** open source basé sur **Apache Lucene**

- Stocke des données en **JSON**
- Exposé via une **API REST**
- Recherches **ultra-rapides** sur de gros volumes

> Créé en 2010 par Shay Banon pour indexer des recettes de cuisine 

---

## Elasticsearch vs PostgreSQL

||PostgreSQL|Elasticsearch|
|---|---|---|
|Modèle|Tables / Lignes|Documents JSON|
|Recherche texte|Basique (`LIKE`)|Full-text avancé|
|Scalabilité|Verticale|Horizontale|
|Transactions|✅ ACID|❌ Non|

→ **Complémentaires**, pas concurrents

---

## Document & Index

**Document** = unité de base, un objet JSON

```json
{
  "nom": "Tarte Tatin",
  "categorie": "dessert",
  "date": "2025-01-15"
}
```

**Index** = regroupement de documents similaires → Un index `recettes`, un index `logs`, un index `utilisateurs`…

---

## Shards

Un index est découpé en **shards** répartis sur plusieurs serveurs

```
Index "recettes"
├── Shard 0 → Node 1
├── Shard 1 → Node 2
└── Shard 2 → Node 3
```

⚠️ Le nombre de shards **ne peut pas être modifié** après création

> Bonne pratique : **~50 Go par shard**

---

## Réplicas

Un **replica** est une copie d'un shard sur un autre node

- ✅ **Haute disponibilité** : si un node tombe, le replica prend le relais
- ✅ **Meilleures perfs** : les recherches se parallélisent sur les replicas

Un shard et sa copie ne sont **jamais sur le même serveur**

---

## Le Mapping

Le mapping = le **schéma** de ton index

```json
{
  "properties": {
    "nom":         { "type": "keyword" },
    "description": { "type": "text"    },
    "date":        { "type": "date"    },
    "note":        { "type": "float"   }
  }
}
```

⚠️ À définir **avant** d'indexer des données

---

## `text` vs `keyword`

La distinction **la plus importante** du mapping

|Type|Usage|
|---|---|
|`text`|Recherche full-text — description, instructions|
|`keyword`|Valeur exacte — catégorie, auteur, statut|

- `categorie` → `keyword` : filtrer exactement sur `"dessert"`
- `description` → `text` : chercher `"pommes caramélisées"` dans le texte

→ Mettre `text` sur `categorie` = bug silencieux 

---
```json
{
  "properties": {
    "nom":              { "type": "text"    },
    "description":      { "type": "text"    },
    "categorie":        { "type": "keyword" },
    "auteur":           { "type": "keyword" },
    "date_creation":    { "type": "date"    },
    "temps_preparation":{ "type": "integer" },
    "note_moyenne":     { "type": "float"   },
    "difficulte":       { "type": "keyword" },
    "ingredients": {
      "type": "nested",
      "properties": {
        "nom":      { "type": "text"    },
        "quantite": { "type": "float"   },
        "unite":    { "type": "keyword" }
      }
    }
  }
}
```

---
## Le score de pertinence

Elasticsearch **classe les résultats** par pertinence avec un `_score`

Basé sur **TF/IDF** :

- **TF** : le mot apparaît souvent dans le doc ? → score ↑
- **IDF** : le mot est rare dans tous les docs ? → score ↑

```json
{ "_score": 2.94, "categorie": "Grillade" }
{ "_score": 6.02, "categorie": "Vegan" }
```

---

## La stack ELK

|Outil|Rôle|
|---|---|
|**E**lasticsearch|Stockage & recherche|
|**L**ogstash|Collecte & transformation|
|**K**ibana|Dashboards & visualisation|
|**Beats**|Agents légers de collecte|

→ **Kafka peut alimenter Elasticsearch** via Logstash ou un consumer Spring

---

## Applications concrètes

Avec une stack **Spring + Kafka + PostgreSQL + Elasticsearch** :

- Recherche full-text sur les données métier
- Centralisation des logs Spring Boot → Kafka → Elastic
- Dashboards Kibana sur les événements Kafka
- Alerting sur des patterns suspects (erreurs 500…)

---

## En résumé

|Concept|En bref|
|---|---|
|**Index / Document**|Table / Ligne en JSON|
|**Shard**|Partition de l'index, non modifiable|
|**Replica**|Copie pour la dispo et les perfs|
|**Mapping**|Schéma à définir avant tout|
|**text vs keyword**|Full-text vs valeur exacte|
|**Score**|Résultats classés par pertinence|

---
## Références

- [elastic.co/guide](https://www.elastic.co/guide/en/elasticsearch/reference/current/index.html) — Documentation officielle

- [elastic.co/search-labs/fr](https://www.elastic.co/search-labs/fr) — Blog technique Elastic en français

- [RFC TF/IDF](https://fr.wikipedia.org/wiki/TF-IDF) — Explication de l'algorithme de pertinence