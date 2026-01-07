# Fiche Technique 5 : Paramètres et Panneau de configuration

Cette section explique la coexistence des deux interfaces de configuration de Windows et comment accéder aux réglages système avancés.

## 1. La dualité des interfaces

Depuis Windows 8 et 10, Windows propose deux environnements pour gérer le système :

* **L'application Paramètres (Settings) :** * Interface moderne, tactile et simplifiée.
* Conçue pour les réglages quotidiens (Wi-Fi, personnalisation, mises à jour via Windows Update).


* **Le Panneau de configuration (Control Panel) :** * Interface classique héritée des anciennes versions de Windows.
* Contient des outils plus granulaires et techniques qui n'ont pas encore été migrés vers l'application moderne.



## 2. System Configuration (msconfig)

L'utilitaire `msconfig` est un outil de dépannage essentiel pour modifier la manière dont Windows démarre.

* **Général :** Permet de choisir entre un démarrage normal, un démarrage en mode diagnostic ou un démarrage sélectif.
* **Démarrer (Boot) :** Permet d'activer le **Mode sans échec** (Safe Boot) et de gérer les options de multiboot si plusieurs systèmes d'exploitation sont installés.
* **Services :** Liste tous les services qui se lancent au démarrage. Une option utile permet de "Masquer tous les services Microsoft" pour identifier un service tiers qui causerait un ralentissement.

## 3. Configuration système avancée

Pour accéder aux réglages de bas niveau, on utilise souvent les "Propriétés système" (accessibles via `sysdm.cpl`).

* **Nom de l'ordinateur :** Pour modifier le nom de la machine ou joindre un domaine/groupe de travail.
* **Paramètres système avancés :**
* **Performances :** Permet de désactiver les effets visuels pour accélérer le système ou de gérer la **Mémoire virtuelle** (fichier d'échange / pagefile.sys).
* **Profils utilisateur :** Une autre méthode pour supprimer des profils stockés sur le disque.
* **Démarrage et récupération :** Définit le comportement du système en cas d'erreur fatale (Écran bleu / BSOD), notamment la création de fichiers de vidage mémoire (dumps).
* **Variables d'environnement :** Accès direct pour modifier les chemins système (PATH) et autres variables globales.
 
