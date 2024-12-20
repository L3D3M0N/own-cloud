**Synthèse du TP Stockage Cloud avec OwnCloud :**

Ce TP présente **OwnCloud**, une solution de stockage et partage de fichiers en ligne offrant un contrôle total sur vos données, contrairement à des solutions commerciales comme Dropbox ou Google Drive. L'objectif est de configurer et d'exploiter OwnCloud côté serveur et client, tout en automatisant les sauvegardes.

---

### **1. Installation de OwnCloud**
- **Via Docker** : 
  - Téléchargement du conteneur avec la commande :  
    `docker pull owncloud`
  - Lancement du conteneur :  
    `docker run -p 8082:80 -d owncloud`
  - Vérification des conteneurs actifs :  
    `docker ps`

---

### **2. Installation du Client OwnCloud**
- Sur **Windows 10/11** : Téléchargement du client via [owncloud.com](https://owncloud.com/download/).
- Configuration d’un utilisateur nommé **"utilisateur"** avec le mot de passe **"Sio2021***`.

---

### **3. Fonctionnalités offertes par OwnCloud**

#### **Côté serveur** :
- **Sécurité** : Plugins pour bloquer les IP suspectes et protéger contre les attaques brute-force.
- **Supervision** : Surveillance des quotas de stockage et des performances grâce à des outils intégrés.
- **Personnalisation** : Ajout de plugins selon les besoins spécifiques (gestion des données, collaboration, etc.).

#### **Côté client** :
- **Exploration locale** : Accès simplifié aux fichiers via l’explorateur.
- **Synchronisation hors ligne** : Travail local avec mise à jour automatique des modifications au retour en ligne.

---

### **4. Automatisation des sauvegardes**
- Un script Bash est utilisé pour :
  - Sauvegarder un fichier **CSV** localement avec un nom basé sur la date/heure.
  - Compresser le fichier en **tar.gz** pour économiser l’espace.
  - Transférer la sauvegarde compressée vers un serveur FTP.



- **Planification des sauvegardes** avec **Cron** :
  - Installation de Cron :  
    `apt install cron`
  - Configuration via `crontab -e` pour exécuter le script quotidiennement :  
    `45 23 * * * /home/sisr-6/script.sh`  
    (Pour des tests : `* * * * * /home/sisr-6/script.sh`).

---

### **Conclusion**
Ce TP a permis de configurer OwnCloud côté serveur et client tout en automatisant les sauvegardes. OwnCloud se distingue par ses fonctionnalités personnalisables, sa sécurité avancée, et son contrôle total sur les données, en offrant une alternative solide aux solutions commerciales comme Dropbox.
