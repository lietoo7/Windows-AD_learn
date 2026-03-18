# Fiche Technique 8 : Informations système

Cette section présente les outils permettant d'obtenir une vue d'ensemble détaillée de la configuration matérielle et logicielle de l'ordinateur.

## 1. L'outil msinfo32

L'outil **Informations système** (`msinfo32.exe`) est une base de données complète qui centralise tous les détails techniques de la machine. Contrairement aux "Paramètres", il n'est pas conçu pour configurer, mais uniquement pour consulter.

* **Résumé système :** Affiche les informations critiques comme la version exacte de Windows (Build), le modèle de la carte mère (BaseBoard), le processeur et le mode BIOS (Hérité ou UEFI).
* **Ressources matérielles :** Détaille les conflits de partage, les adresses E/S et les DMA (Direct Memory Access). C'est une section très technique utilisée pour le dépannage de bas niveau.
* **Composants :** Permet d'inspecter les détails de chaque périphérique (Stockage, Réseau, Affichage). C'est ici que l'on trouve l'ID de périphérique pour chercher un pilote spécifique.
* **Environnement logiciel :** Liste les pilotes chargés, les tâches en cours, les services et les programmes qui se lancent automatiquement au démarrage.

## 2. Les Variables d'environnement

Les variables d'environnement sont des chaînes de caractères dynamiques contenant des informations utilisées par le système et les programmes.

* **Types de variables :**
* **Variables utilisateur :** Spécifiques à la session actuelle (ex: `%TEMP%` qui pointe vers le dossier temporaire de l'utilisateur).
* **Variables système :** Globales pour toute la machine (ex: `%OS%` ou `%SystemDrive%`).


* **La variable PATH :** C'est la variable la plus importante. Elle contient une liste de répertoires. Lorsque vous tapez une commande dans le terminal, Windows cherche l'exécutable dans chaque dossier listé dans le **PATH**.
* **Accès :** On y accède via `sysdm.cpl` > onglet "Paramètres système avancés" > bouton "Variables d'environnement".

## 3. Identification du système en ligne de commande

Pour obtenir un résumé rapide sans interface graphique, on utilise souvent la commande suivante dans l'invite de commandes :
`systeminfo`

Cette commande affiche la date d'installation originale du système, le temps de fonctionnement (Uptime) et les correctifs (Hotfixes) installés.
 
