## Fiche Technique 6 : Gestionnaire des tâches

Le **Gestionnaire des tâches** (Task Manager) est l'outil de surveillance et de diagnostic rapide par excellence. On l'ouvre généralement avec le raccourci **`Ctrl + Maj + Échap`**.

<hr>

## 1. Gestion des processus

C'est l'onglet principal qui affiche tout ce qui s'exécute sur la machine.

* **Processus d'application :** Les logiciels ouverts par l'utilisateur (Chrome, Word, etc.).
* **Processus d'arrière-plan :** Services et tâches lancés par le système ou des logiciels tiers.
* **Actions possibles :** En faisant un clic droit, on peut "Fin de tâche" (forcer la fermeture) ou "Ouvrir l'emplacement du fichier" pour identifier l'origine d'un programme suspect.

### Commandes SC et TASK

- **sc query** : Affiche l'état des services.
- **tasklist** : Liste tous les processus en cours d'exécution, avec des détails sur chaque processus.

<hr>

## 2. Surveillance de la performance

L'onglet **Performance** offre une vue graphique en temps réel des ressources :

* **Processeur (CPU) :** Pour repérer si un processus sature la puissance de calcul.
* **Mémoire (RAM) :** Indique la quantité de mémoire utilisée et la vitesse des barrettes.
* **Disque :** Affiche le temps d'activité et le taux de transfert (très utile pour diagnostiquer un PC lent à cause d'un disque saturé).
* **Réseau (Ethernet/Wi-Fi) :** Permet de voir les débits de téléchargement et d'envoi.

### Commandes SC et TASK

- **taskmgr** : Ouvre le gestionnaire de tâches directement.
- **wmic cpu get loadpercentage** : Affiche le pourcentage d'utilisation du CPU.

<hr>

## 3. Applications au démarrage

L'onglet **Applications de démarrage** (Startup) est crucial pour optimiser la vitesse de boot :

* Il liste les programmes qui se lancent automatiquement à l'ouverture de session.
* Il indique l'**Impact au démarrage** (Bas, Moyen, Haut).
* **Conseil :** On peut désactiver les programmes non essentiels pour gagner en rapidité sans pour autant les désinstaller.

### Commandes SC et TASK

- **sc delete [nom_service]** : Supprime un service qui est lancé au démarrage.
- **taskkill /im [nom_processus]** : Met fin à un processus en cours.

<hr>

## 4. Utilisateurs et Détails

* **Utilisateurs :** Permet de voir quelles ressources sont consommées par chaque session ouverte sur la machine.
* **Détails :** C'est la vue avancée de l'onglet Processus. On y trouve le **PID** (Process Identifier), indispensable pour les administrateurs, et on peut y définir la **Priorité** d'un processus (par exemple, donner plus de ressources à un rendu vidéo).

### Commandes SC et TASK

- **tasklist /fi "username eq [nom_utilisateur]"** : Filtre les processus du gestionnaire de tâches pour afficher ceux d'un utilisateur spécifique.
- **sc config [nom_service] start= [type_démarrage]** : Modifie le type de démarrage d'un service.

<hr>

## 5. Historique des applications et Services

* **Historique :** Utile pour voir quels programmes ont consommé le plus de données ou de batterie sur une période donnée.
* **Services :** Un accès rapide aux services système pour voir s'ils sont en cours d'exécution ou arrêtés.

### Commandes SC et TASK

- **sc start [nom_service]** : Démarre un service spécifié.
- **sc stop [nom_service]** : Arrête un service en cours d'exécution.
