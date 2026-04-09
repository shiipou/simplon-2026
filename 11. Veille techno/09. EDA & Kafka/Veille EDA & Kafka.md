
## Event-Driven Architecture (EDA)

![[Pasted image 20260408083914.png]]

---
## Définition

**Event-Driven Architecture (EDA) ou Architecture Orientée Événements** est une approche de conception logicielle où les applications agissent en produisant et en répondant à des événements de façon asynchrone.

---

## Principes fondamentaux

**Dissociation** — les composants n'ont aucune dépendance directe entre eux. Un producteur publie un événement sans savoir qui va le consommer.

**Couplage faible** — les composants peuvent interagir sans créer de dépendance. Ils se connaissent via le contrat de l'événement, pas via un appel direct.

**Les deux principes** rendent le système flexible, indépendant et évolutif.

---
## Qu'est-ce qu'un événement ?

Un événement c'est simplement **quelque chose qui s'est passé**. Un fait accompli, immuable.

Exemples :

- Sinistre déclaré
- Contrat résilié
- Commande passée
- Virement initié
- ...

---
## Cas concret

Un client ouvre l'application de son assureur et soumet un formulaire de sinistre — dégât des eaux dans son appartement.

---

À ce moment précis, un événement se produit :

```json
SINISTRE_DÉCLARÉ
{
  "id"        : "SIN-2024-00842",
  "type"      : "DÉGÂT_DES_EAUX",
  "client_id" : "CLI-49201",
  "date"      : "2024-11-04T09:32:00",
  "montant"   : 3200.00
}
```

L'événement ne dit pas "ouvre un dossier" ou "préviens un expert". Il dit juste : **"un sinistre a été déclaré, voilà les faits"**.

---
## L'immuabilité

Un événement **ne se modifie jamais**. Si une erreur est commise, on crée un nouvel événement :

```json
SINISTRE_CORRIGÉ
{
  "id"     : "SIN-2024-00842",
  "montant": 4100.00,
  "motif"  : "Estimation initiale incomplète"
}
```

C'est comme un journal de bord — on n'efface pas une ligne, on en ajoute une nouvelle.

---
## Producteur et consommateur

---
### Le producteur

C'est le composant qui **détecte qu'un événement s'est produit et le publie**. Il ne sait pas ce qui va se passer ensuite. Son seul rôle : dire "ça s'est passé" et passer à autre chose.

Dans notre exemple, le producteur c'est **l'application mobile** de l'assureur.

---
## Le consommateur

C'est un service qui **s'abonne à un type d'événement et réagit quand il en reçoit un**. Il y en a autant que nécessaire, chacun travaille indépendamment.

---

#### 5 consommateurs écoutent tous le même événement `SINISTRE_DÉCLARÉ` ->

---

|Consommateur|Ce qu'il fait|
|---|---|
|Service Dossier|Ouvre et enregistre le dossier client|
|Service Fraude|Analyse les données pour détecter une fraude|
|Service Expert|Planifie l'intervention d'un expert terrain|
|Service Notification|Envoie un SMS de confirmation au client|
|Service Comptabilité|Provisionne le montant estimé du sinistre|

---
## Le Découplage

Le producteur et les consommateurs **ne se connaissent pas**. L'application mobile ne sait pas que le Service Fraude existe. Le Service Notification ne sait pas que le Service Comptabilité existe.

Tout ce qu'ils partagent : le nom du topic `"sinistres"` et le format de l'événement.

---
## Le Bus d'événements

Le bus d'événements est un **serveur séparé** — un programme qui tourne indépendamment de toutes les applications. Son seul rôle : **recevoir des événements, les stocker, et les distribuer aux abonnés**.


![[Pasted image 20260408083845.png]]

---
## Modèles d'EDA


**Pub/Sub (Publication/Abonnement)** : Modèle où un producteur publie un message et tous les abonnés le reçoivent. C'est le principe de base.


**Flux d'événements (Event Streaming)** : Couche supplémentaire au-dessus du pub/sub. Ce qui le distingue :

- Les événements sont **stockés dans l'ordre chronologique** comme un journal
- On peut **rejouer** les événements passés
- On peut **traiter les événements en continu** comme un flux de données

---
## Kafka — les 3 concepts clés

![[Pasted image 20260408083937.png]]

---
#### 1. Le topic

Un topic c'est comme une **boîte aux lettres nommée**. Le producteur dépose ses événements dedans, les consommateurs y piochent.

```
topic "sinistres"   → événements liés aux sinistres
topic "contrats"    → événements liés aux contrats
topic "paiements"   → événements liés aux paiements
```

---
#### 2. Le stockage

Quand un événement est publié, **Kafka le conserve pendant une durée configurable.**

Scénario concret :

- L'App Notification tombe en panne à 9h32 au moment du sinistre
- L'événement `SINISTRE_DÉCLARÉ` reste stocké dans Kafka
- L'App Notification redémarre à 10h15
- Elle récupère l'événement et envoie le SMS — **rien n'a été perdu**

---
#### 3. L'offset

Kafka garde une position pour chaque consommateur — l'**offset**. C'est un numéro qui dit "jusqu'où ce consommateur a lu".

```
Topic "sinistres"
────────────────────────────────────────────
[événement 0] [événement 1] [événement 2] [événement 3]
                             ↑                          ↑
                     App Fraude                 App Notification
                     (a lu jusqu'ici)           (a lu jusqu'ici)
```

Chacune avance indépendamment, sans bloquer les autres.

---
## Ce que Kafka garantit

- ✅ Un événement publié ne sera **jamais perdu**
- ✅ Chaque consommateur reçoit **tous les événements**
- ✅ Les événements sont **dans l'ordre**
- ✅ On peut **rejouer les événements**

---
## Architecture classique VS EDA

---
### Classique — les appels sont directs en chaîne

L'App Sinistres doit contacter chaque service **elle-même, directement, dans un ordre précis**.

Chaque appel est **bloquant**. Si chaque service prend 1 seconde, le client attend **5 secondes**.

**Problème du couplage :** L'App Sinistres connaît et dépend de 5 services. Ajouter un Service Juridique = **modifier le code de l'App Sinistres**.

---
### Avec l'EDA — Juste publier

- App Dossier continue ✅
- App Fraude continue ✅
- App Expert continue ✅
- App Notification en panne — l'événement reste dans Kafka
- App Comptabilité continue ✅

---

Au redémarrage, l'App Notification récupère l'événement et envoie le SMS. **Avec du retard, mais sans perte.**

**Ajouter un service :** on crée un nouveau projet, on l'abonne au topic `"sinistres"`. **L'App Sinistres ne change pas d'une ligne.**

---
## Débogage en architecture classique

Le flux est **linéaire et synchrone** — quand quelque chose plante, on a une stacktrace complète :

```
AppSinistres.declarerSinistre()
  → ServiceFraude.verifier()        ✅
  → ServiceExpert.planifier()       ✅
  → ServiceNotification.envoyer()   NullPointerException ligne 42
```

On sait immédiatement quel service a planté, à quelle ligne, dans quel contexte.

**La limite** : si un service a planté, tout ce qui venait après n'a pas été exécuté. Pas de reprise partielle possible.

---
## Débogage en EDA

**L'erreur silencieuse — le service tourne mais traite mal**

Le service reçoit l'événement, dit "OK reçu" à Kafka, mais son traitement échoue en interne. C'est le cas le plus dangereux car il est invisible.

---

Le flux est **asynchrone et distribué**. Une erreur dans le Service Fraude n'apparaît pas dans les logs de l'App Sinistres.

```
App Sinistres publie SINISTRE_DÉCLARÉ  ✅
App Dossier traite                     ✅
App Fraude traite                      erreur silencieuse
App Expert traite                      ✅
App Notification traite                ✅
App Comptabilité traite                ✅
```

Tout semble bien se passer côté App Sinistres — mais le Service Fraude a raté silencieusement.

---
#### Causes les plus courantes :

- **Bug applicatif** — le code plante sur certains cas particuliers
- **Base de données indisponible** — le service tourne mais ne peut pas sauvegarder
- **Données inattendues** — l'événement contient un format que le service ne sait pas gérer

---

Pour y remédier, Kafka fournit **3 mécanismes** :

#### Mécanisme 1 — Le Retry

Quand un consommateur échoue, il **réessaie automatiquement** plusieurs fois avant d'abandonner.

Utile pour les erreurs **temporaires** — BDD momentanément indisponible, timeout réseau passager.


#### Mécanisme 2 — La Dead Letter Queue (DLQ)

Si après tous les retries l'événement ne peut toujours pas être traité, Kafka l'envoie dans un **topic spécial de quarantaine** :

```
Topic "sinistres"
  → App Fraude tente de traiter  ❌ échec
  → retry 1                      ❌ échec
  → retry 2                      ❌ échec
  → retry 3                      ❌ échec
  → événement envoyé en DLQ      "sinistres-dlq"
```

L'équipe peut ensuite :

1. Inspecter les événements en DLQ
2. Corriger le bug
3. **Rejouer** les événements depuis la DLQ

#### Mécanisme 3 — Le Replay

Puisque Kafka conserve les événements, on peut **rembobiner et retraiter** des événements passés.

```
Lundi 09h00 → 50 sinistres déclarés
              → App Fraude les traite tous avec un bug ❌

Lundi 14h00 → l'équipe détecte et corrige le bug

Lundi 14h30 → on rembobine l'offset au lundi 09h00
              → les 50 événements sont retraités correctement ✅
```

---

## Avantages

✅ Plusieurs applications fonctionnent en parallèle sans dépendre l'une de l'autre

✅ Meilleure scalabilité — ajouter un nouveau service ne nécessite pas de modifier le producteur

✅ Capable de gérer de gros volumes d'événements rapidement

✅ Traçabilité complète — chaque événement est stocké, permettant de retracer tout l'historique d'un sinistre

---

## Inconvénients

❌ Débogage plus complexe — pas de stacktrace directe, l'erreur peut venir de n'importe quel service

❌ Complexité opérationnelle — Kafka est un serveur supplémentaire à déployer et maintenir

---

## Quand l'utiliser ?

- **Plusieurs services doivent réagir au même événement**
- **Les traitements peuvent être asynchrones**
- **Perdre un événement est inacceptable** — un paiement, un sinistre, une commande
- **Le système est amené à évoluer** — ajouter de nouveaux services sans toucher au code existant

L'EDA résout le problème du **couplage entre services**. Si l'on n'a pas ce problème, pas besoin d'EDA.

---

## Sources


 - https://www.geeksforgeeks.org/system-design/event-driven-architecture-system-design/
- https://www.redhat.com/fr/topics/integration/what-is-event-driven-architecture#avantages-dune-architecture-orient%C3%A9e-%C3%A9v%C3%A9nements
- https://www.ibm.com/fr-fr/think/topics/event-driven-architecture