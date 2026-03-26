
## Architecture & Sécurité : Comprendre les Ports et la Surface d'Exposition

---
## Les Ports : Les "Portes" de ton Serveur

---

Un serveur possède **65 535 ports** disponibles (1 à 65535). On peut les voir comme des canaux de communication logiques sur une adresse IP.

Répartition des ports
- **Ports système (Réservés) :** 0 à 1023. Utilisés par les services fondamentaux (root requis pour les ouvrir).
- **Ports enregistrés :** 1024 à 49151. Utilisés par des applications tierces (ex: MongoDB sur 27017).
- **Ports dynamiques/privés :** 49152 à 65535.

---
## Les standards incontournables

---

| service | port |  rôle                                           |
| :------ | :--- | :---------------------------------------------- |
| ssh     | 22   | Accès administrateur sécurisé (tunnel chiffré). |
| http    | 80   | Trafic web non chiffré (déprécié).              |
| https   | 443  |  Trafic web chiffré (SSL/TLS).                  |

---

## Mise en place d'un site web

---

1. connection au serveur via ssh
2. installation du site (le site écoute le port renseigné dans votre application)
3. mise en place de de serveur web (apache, nginx). c'est ce serveur web qui écoute les ports 80 et 443. il redirige le trafic vers le port de votre site web.

---

## La réalité du terrain : La menace permanente

---

Quand tu ouvres un port sur Internet, tu ne l'ouvres pas seulement pour tes utilisateurs légitimes. Tu l'ouvres pour **tous les bots de la planète**.

Ceux de google (utile pour le référencement), mais aussi ceux des hackers.

Les robots de hackers vont scanner votre serveur à la recherche des ports ouvets et derrière lesquels une application écoute.

---

exemples :
- apache ou nginx écoutent les ports 80 et 443.
- une application nodejs écoute par défaut le port 3000.

---

## Anatomie d'une attaque : Le cycle automatisé

---

### Étape 1 : Le Fingerprinting (Reconnaissance)

- Le bot analyse les en-têtes HTTP (Server, X-Powered-By) et les patterns d'URLs pour identifier la "pile technologique" (Stack).

- Il récupère également les versions utilisées.

- Il compare les réponses du serveur avec des bases de données de vulnérabilités connues (CVE - Common Vulnerabilities and Exposures).

---

### Étape 2 : L'Exploitation (La phase active)

Une fois la stack identifiée, le bot envoie des charges utiles (Payloads) spécifiques :
- **Injection** : Test de SQL Injection si le framework interagit avec une base de données.

- **Remote Code Execution (RCE)** : Tentative d'exploitation de failles dans des bibliothèques

- **Path Traversal** : Il tente d'accéder à des fichiers de configuration (.env, config.json) qui sont souvent exposés par erreur.

---

### Étape 3 : La persistance

Si une faille est trouvée, le bot injecte souvent un Web Shell (un petit script PHP, JS, BASH) pour garder un accès permanent au serveur, même si tu redémarres l'application.

---

## Étude de cas

---

1. J'ai un site en production sur un VPS (machine virtuelle).

2. Vers le 20 décembre 2025, google m'informe qu'il ne peut plus voir mon site (erreur 500).

3. Je me connecte au vps via ssh.

4. Je regarde les logs. 

---

5. Je découvre que mon site reçois énormement de requêtes.

6. Un fichier a été téléchargé dans le dossier tmp et s'appel vim (/tmp/vim).

7. Le fichier tente d'établir des connexions avec l'extérieur en passant par mon site.

8. mon site a fini par planter.

---

## Action -> Réaction

---

1. Suppression du fichier vim. 

2. redémarrage du sytème. l'objectif étant de voir si après le redémarrage, le fichier se ré-installe ou pas.

3. ```bash sudo crontab -l ``` voir si aucune tâche n'a été créée

4. ```bash ls ~./shh ``` voir si aucune clé ssh n'a été installée

5. Mise en place de Fail2ban (on banni les ip malveillantes)

---

## Rapport de Fail2ban

---

Status for the jail: nextjs-global

|- Filter

|  |- Currently failed: 110

|  |- Total failed: 9904

|  `- File list: /var/log/apache2/access.log

---

`- Actions

   |- Currently banned: 15

   |- Total banned: 1347

   `- Banned IP list: 18.117.75.161 176.65.148.66 185.177.72.13 149.86.227.60 206.168.34.122 35.190.139.8 3.151.241.153 43.138.5.244 87.121.84.76 204.76.203.18 216.180.246.49 93.174.93.12 78.153.140.149 3.131.220.121 95.214.55.63
   
---

Currently failed:  110

C'est le nombre d'adresses IP qui ont commis des erreurs "suspectes" mais qui ne sont pas encore bannies.

---

Total failed:  9904

C'est le nombre total de tentatives malveillantes détectées depuis que le service a été lancé sur le serveur.

---

File list: /var/log/apache2/access.log

C'est le fichier que Fail2Ban surveille

---

Currently banned:  15

Il y a précisément 15 adresses IP qui sont actuellement bloquées par le pare-feu du serveur. Elles ne peuvent plus accéder à ton site web du tout.

---

Total banned: 1347

C'est le nombre total de bannissements effectués depuis le début.

---

Banned IP list: 18.117.75.161 176.65.148.66 185.177.72.13 149.86.227.60 206.168.34.122 35.190.139.8 3.151.241.153 43.138.5.244 87.121.84.76 204.76.203.18 216.180.246.49 93.174.93.12 78.153.140.149 3.131.220.121 95.214.55.63

C'est la liste brute des attaquants (Currently banned).

---

## Logs pm2

---

**[Error: Failed to find Server Action "1"**. This request might be from an older or newer deployement.
Read more: https//nextjs.org/docs/messages/failed-to-find-server-action]

---

**[Error: Failed to find Server Action "22wge6gp"**. This request might be from an older or newer deployement.
Read more: https//nextjs.org/docs/messages/failed-to-find-server-action]

---

**[Error: Failed to find Server Action "AKhix5XM"**. This request might be from an older or newer deployement.
Read more: https//nextjs.org/docs/messages/failed-to-find-server-action]

---

## Logs apache

---

[12/Mar/2026:17:24:04 +0000] "**GET /.env** HTTP/1.1" 404 11552 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/116.0.5845.140 Safari/537.36"

**172.94.9.253** - - [12/Mar/2026:17:40:34 +0000] "**GET /.git/config** HTTP/1.1" 404 11468 "-" "Mozilla/5.0 (X11; Linux i686; rv:1.9.7.20) Gecko/ Firefox/3.6.7"

---

**44.200.217.136** - - [12/Mar/2026:17:58:17 +0000] "**GET /dashboard** HTTP/1.1" 404 7486 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/142.0.0.0 Safari/537.36"

**44.200.217.136** - - [12/Mar/2026:17:58:17 +0000] "**GET /admin** HTTP/1.1" 404 11210 "-" "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/131.0.0.0 Safari/537.36"

**Ils cherchent des erreurs de configuration courantes**

---

**62.171.133.187** - - [12/Mar/2026:23:52:42 +0000] "**POST /cgi-bin/.%2e/.%2e/.%2e/.%2e/.%2e/.%2e/
.%2e/.%2e/.%2e/.%2e/bin/sh** HTTP/1.1" 400 4186 "-" "libredtail-http"

**62.171.133.187** - - [12/Mar/2026:23:52:42 +0000] "**POST /cgi-bin/%%32%65%%32%65/%%32%65%%32%65/%%32%65%%32%65/%%32%65%%32%65/%%32%65%%32%65/
%%32%65%%32%65/%%32%65%%32%65/bin/sh** HTTP/1.1" 400 4186 "-" "libredtail-http"

---

**tentative d'exploitation de vulnérabilité connue (CVE)**

**L'attaquant tente une attaque de type "Path Traversal" ou "Remote Code Execution (RCE)" sur un répertoire cgi-bin**

**Il essaie d'utiliser des séquences comme .%2e/ (qui est du "point-point-slash" encodé) pour sortir du répertoire web et atteindre le fichier /bin/sh de ton système (le shell Linux).**

**S'il réussissait, il pourrait exécuter des commandes système à distance**

---

**74.243.251.125** - - [12/Mar/2026:23:46:11 +0000] "**GET /wp-content/plugins/hellopress/wp_filemanager.php** HTTP/1.1" 403 449 "-" "-"

**74.243.251.125** - - [12/Mar/2026:23:46:12 +0000] "**GET /ws81.php** HTTP/1.1" 403 449 "-" "-"

**74.243.251.125** - - [12/Mar/2026:23:46:12 +0000] "**GET /hnikt.php** HTTP/1.1" 403 449 "-" "-"

**74.243.251.125** - - [12/Mar/2026:23:46:12 +0000] "**GET /awh.php** HTTP/1.1" 403 449 "-" "-"

---

**74.243.251.125** - - [12/Mar/2026:23:46:12 +0000] "**GET /js.php** HTTP/1.1" 403 449 "-" "-"

**74.243.251.125** - - [12/Mar/2026:23:46:12 +0000] "**GET /34.php** HTTP/1.1" 403 449 "-" "-"

**Il essaie d'exploiter des vulnérabilités connues dans des extensions WordPress (wp-content/plugins/...) ou de chercher des fichiers de porte dérobée (backdoor) souvent utilisés lors d'anciennes attaques (les fichiers .php nommés au hasard comme gu.php, rafa.php, etc.)**

---

## Quelques recommandations

---

- Ne jamais lancé une application en tant que root (sudo).
- Il faut créer un utilisateur avec des droits restreints qui lancera l'appli.
- fermer les ports non utilisés via le pare-feu.
- changer le port ssh par défaut.
- Utiliser une clé ssh pour se connecter au serveur.
