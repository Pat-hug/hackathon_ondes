---

## 🛠️ Explication de ce que j'ai fait

### 📡 1. Sécurisation de la borne Wi-Fi (OpenWrt)

Pour bien protéger la borne Wi-Fi, j'ai d'abord lancé une vérification pour voir les problèmes de sécurité. Voici toutes les étapes que j'ai réalisées :

* **Protection des réglages de la borne :**
  * J'ai changé le mot de passe de départ par un mot de passe solide pour que personne ne puisse modifier mes réglages.
  * J'ai activé la connexion sécurisée (**HTTPS**) sur la page de gestion pour que les mots de passe ne circulent pas en clair sur le réseau.
  * J'ai bloqué l'accès aux réglages de la borne depuis Internet (**WAN**) pour éviter les attaques venant de l'extérieur.

* **Sécurisation du réseau Wi-Fi :**
  * J'ai allumé le Wi-Fi principal et je lui ai donné le nom **Mercator** pour bien le reconnaître.
  * J'ai mis en place une sécurité moderne (**WPA2/WPA3**) avec un mot de passe long d'au moins **12 caractères** pour empêcher les pirates de le deviner.
  * J'ai désactivé le bouton de connexion rapide (**WPS**) qui représente une faille de sécurité.

* **Séparation et sauvegarde :**
  * J'ai créé un **réseau invité** bien séparé du réseau principal : comme ça, les invités ont Internet mais ne peuvent pas voir mes appareils personnels.
  * J'ai enregistré une **sauvegarde** de tous mes réglages pour pouvoir les remettre facilement en cas de problème.

* **Ce qu'il reste à faire :**
  * Il me reste uniquement à sécuriser la connexion à distance (**SSH**) en utilisant une clé numérique à la place du mot de passe (étape prévue dans la **quête 13**).

---

### 💻 2. Sécurisation du poste Ubuntu (Quête 14 — Boss : Le Glitch)

Lors du premier test de sécurité sur mon ordinateur Ubuntu, **3 attaques sur 9** réussissaient encore à passer, même si le pare-feu (**UFW**) bloquait déjà les connexions interdites. Voici comment j'ai corrigé cela :

* **Blocage des mots de passe en SSH :** J'ai modifié le fichier de réglage `/etc/ssh/sshd_config` en ajoutant `PasswordAuthentication no` (pour obliger l'utilisation d'une clé sécurisée à la place d'un simple mot de passe) et `PermitRootLogin no` (pour interdire la connexion directe sur le compte administrateur principal).
* **Application des réglages :** J'ai redémarré le service avec la commande `sudo systemctl restart ssh` pour valider mes changements.
* **Protection contre les essais de mots de passe :** J'ai installé et activé le logiciel **Fail2ban** (`sudo apt install fail2ban`). Ce programme surveille les connexions et bloque automatiquement les adresses IP qui essaient de deviner un mot de passe plusieurs fois de suite.

Grâce à ces réglages, le test final a permis de bloquer **9 attaques sur 9**.
