# Réseautage sous Windows  

Ce cours regroupe les notions fondamentales pour configurer, connecter et faire communiquer des systèmes Windows dans un environnement physique ou virtuel.

## I. Configuration de base du système

Avant toute manipulation réseau, il est essentiel de préparer l'identité de la machine.

### 1. Identification de l'ordinateur

* **Action** : Accédez aux **Propriétés du système** > **Modifier les paramètres**.
* **Rôle** : Donner un nom unique (ex: `PC-FORMATION-01`) pour identifier la machine sur le réseau (Groupe de travail ou Domaine).

### 2. Le Protocole TCP/IP (IPv4)

La communication repose sur l'adresse IP, composée d'une **partie Réseau** (fixée par le masque) et d'une **partie Hôte** (propre à la machine).

* **Mode Dynamique (DHCP)** : Le routeur attribue automatiquement l'IP.
* **Mode Statique** : Vous fixez l'IP manuellement pour un serveur ou un test spécifique.

---

## II. Paramétrage des Adresses IP

### 1. Configurer une IP fixe

1. **Chemin** : Panneau de configuration > Centre Réseau et partage > Modifier les paramètres de la carte.
2. **Propriétés** : Clic droit sur la carte > Propriétés > **Protocole Internet version 4 (TCP/IPv4)**.
3. **Saisie** :
* **IP** : ex: `192.168.1.10`
* **Masque** : ex: `255.255.255.0`
* **Passerelle** : L'IP de votre routeur (ex: `192.168.1.1`).
* **DNS** : ex: `8.8.8.8` (Google) pour la navigation internet.



### 2. Configuration Alternative

Utile pour définir une IP de secours quand aucun serveur DHCP n'est détecté.

* Dans les propriétés IPv4, allez dans l'onglet **Configuration alternative**.
* Cochez **Utilisateurs configurés** et entrez vos paramètres statiques.

---

## III. Virtualisation avec VirtualBox

Pour faire communiquer une machine virtuelle (VM) avec votre ordinateur physique (Hôte).

### 1. Modes de connexion

* **Accès par pont (Bridged)** : La VM est au même niveau que l'hôte sur votre box internet.
* **Réseau privé hôte (Host-Only)** : Crée un réseau local fermé uniquement entre l'hôte et la VM.

### 2. Mise en place (Host-Only)

1. Dans VirtualBox : **Fichier** > **Gestionnaire de réseau hôte** (vérifiez l'IP de l'adaptateur, souvent `192.168.56.1`).
2. Dans les paramètres de la VM : Onglet **Réseau**, choisissez "Réseau privé hôte".

---

## IV. Partage de fichiers (Protocole SMB)

Permet d'échanger des dossiers entre deux machines sur le même réseau.

### 1. Préparation du système

* **Profil Réseau** : Doit être réglé sur **Privé** (Paramètres > Réseau et Internet).
* **Partage avancé** : Dans le Centre Réseau et partage, activez la "Découverte de réseau" et le "Partage de fichiers".

### 2. Partager un dossier

1. Clic droit sur le dossier > **Propriétés** > Onglet **Partage**.
2. Cliquez sur **Partage avancé** > **Partager ce dossier**.
3. Configurez les **Autorisations** (ex: "Tout le monde" en lecture/écriture).

### 3. Accéder au partage

Depuis l'autre machine, utilisez le raccourci `Windows + R` et tapez :
`\\ADRESSE_IP_DU_PC_DISTANT` (ex: `\\192.168.56.101`).

---

## V. Outils de Diagnostic (Invite de commande)

Utilisez ces commandes pour valider votre installation :

| Commande | Utilité |
| --- | --- |
| `ipconfig /all` | Affiche la configuration réseau complète. |
| `ping [IP]` | Teste la réponse d'une autre machine. |
| `tracert [IP]` | Trace la route vers une destination (saute de routeurs). |
| `netstat` | Affiche les connexions actives (ex: communication vers Active Directory). |
| `net share` | Affiche la liste des dossiers que vous partagez actuellement. |

> **Note importante** : Si le réseau semble bien configuré mais que le `ping` échoue, vérifiez toujours le **Pare-feu Windows**. Pour vos tests, vous devrez souvent autoriser le "Partage de fichiers et d'imprimantes" dans les règles du pare-feu.
