## Qu'est-ce que le SMB ?

Le **SMB** (*Server Message Block Protocol*) est un protocole de communication client-serveur utilisé pour partager l'accès aux fichiers, aux imprimantes, aux ports série et à d'autres ressources sur un réseau.

### Fonctionnement

Les serveurs mettent à disposition des clients du réseau des systèmes de fichiers et d'autres ressources (imprimantes, tubes nommés, API). Bien que les ordinateurs clients possèdent leurs propres disques durs, ils souhaitent également accéder aux systèmes de fichiers et aux imprimantes partagés sur les serveurs.

### Caractéristiques techniques

Le protocole SMB est un protocole de type **requête-réponse**, ce qui signifie qu'il transmet plusieurs messages entre le client et le serveur pour établir une connexion. Les clients se connectent aux serveurs via :

* **TCP/IP** (plus précisément NetBIOS sur TCP/IP, comme spécifié dans les documents RFC1001 et RFC1002).
* **NetBEUI**.
* **IPX/SPX**.

---
Voici la suite de la traduction en français, adaptée au contexte technique de la cybersécurité :

Une fois la connexion établie, les clients peuvent envoyer des commandes (**SMBs**) au serveur leur permettant d'accéder aux partages, d'ouvrir des fichiers, de lire et d'écrire des données, et généralement d'effectuer toutes les actions habituelles sur un système de fichiers. Cependant, dans le cas du SMB, ces actions sont effectuées à travers le réseau.

### Quels systèmes utilisent SMB ?

Les systèmes d'exploitation Microsoft Windows (depuis Windows 95) incluent nativement le support client et serveur du protocole SMB. **Samba**, un serveur open source prenant en charge le protocole SMB, a été développé pour les systèmes Unix.

---

## Énumération du SMB
### L'Énumération

L'énumération est le processus consistant à recueillir des informations sur une cible afin de trouver des vecteurs d'attaque potentiels et de faciliter l'exploitation.

Ce processus est essentiel à la réussite d'une attaque : perdre du temps avec des exploits qui ne fonctionnent pas ou qui font planter le système est une perte d'énergie. L'énumération permet de collecter des noms d'utilisateurs, des mots de passe, des informations réseau, des noms d'hôtes, des données d'application, des services ou toute autre information précieuse pour un attaquant.

### SMB

En règle générale, un serveur possède des lecteurs de partage SMB auxquels on peut se connecter pour visualiser ou transférer des fichiers. Le SMB est souvent un excellent point de départ pour un attaquant cherchant des informations sensibles — vous seriez surpris de ce que l'on trouve parfois sur ces partages.

### Analyse de ports (Port Scanning)

La première étape de l'énumération consiste à effectuer un scan de ports pour obtenir un maximum d'informations sur les services, les applications, la structure et le système d'exploitation de la machine cible.

### Enum4Linux

**Enum4linux** est un outil utilisé pour énumérer les partages SMB sur les systèmes Windows et Linux. Il s'agit essentiellement d'un "wrapper" (une interface) autour des outils du paquet Samba, permettant d'extraire rapidement les informations SMB de la cible.

La syntaxe d'Enum4Linux est simple : `enum4linux [options] <ip>`

---

## Exploitation du SMB

### Types d'exploits SMB

Bien qu'il existe des vulnérabilités telles que la **CVE-2017-7494** permettant l'exécution de code à distance (RCE) via SMB, vous rencontrerez plus souvent des situations où la meilleure porte d'entrée réside dans des **erreurs de configuration** du système. Dans ce cas précis, nous allons exploiter un accès anonyme à un partage SMB — une mauvaise configuration courante qui peut nous permettre d'obtenir des informations menant à l'obtention d'un "shell" (accès en ligne de commande).

### Analyse de la méthode

Grâce à notre étape d'énumération, nous connaissons désormais :

* L'emplacement du partage SMB.
* Le nom d'un partage SMB intéressant.

### SMBClient

Puisque nous essayons d'accéder à un partage SMB, nous avons besoin d'un client pour accéder aux ressources du serveur. Nous utiliserons **SMBClient**, car il fait partie de la suite Samba par défaut.

Nous pouvons accéder à distance au partage SMB en utilisant la syntaxe suivante :

* **Syntaxe :** `smbclient //[IP]/[NOM_DU_PARTAGE] -U [UTILISATEUR] -p [PORT]`
* **Exemple :** `smbclient //10.10.10.10/secrets -U Anonymous -p 445`

### Commandes SMBClient

Une fois connecté au partage, vous pouvez afficher les commandes disponibles en tapant `help`. Les plus utiles sont :

* `ls` ou `dir` : Lister les fichiers et les répertoires.
* `cd [RÉPERTOIRE]` : Se déplacer dans un autre répertoire.
* `get [FICHIER]` : Télécharger le fichier sur votre machine d'attaque (AttackBox).

 
