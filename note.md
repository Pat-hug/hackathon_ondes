Sécurisation du poste Ubuntu (UFW, SSH, Fail2ban)
Lors de l'exercice de sécurité (Quête 14 — Boss : Le Glitch), 
le test initial a montré que 3 attaques sur 9 pouvaient encore passer sur le système.
 Même si le pare-feu UFW bloquait déjà les connexions réseau non autorisées,
 la connexion à distance (SSH) acceptait encore les mots de passe simples et l'accès direct au compte administrateur (root).
 Pour corriger cela, j'ai modifié le fichier de configuration /etc/ssh/sshd_config en ajoutant PasswordAuthentication no
 (pour obliger l'utilisation d'une clé sécurisée au lieu d'un mot de passe)
 et PermitRootLogin no (pour bloquer l'accès direct au compte administrateur),
 puis j'ai redémarré le service SSH (sudo systemctl restart ssh)
 pour appliquer les changements. Enfin, j'ai installé et activé le logiciel Fail2ban (sudo apt install fail2ban),
 qui surveille les tentatives de connexion et bloque automatiquement les adresses IP qui essaient de deviner un mot de passe plusieurs fois de suite,
 ce qui a permis de bloquer les 9 attaques.

Configuration de la borne Wi-Fi
Pour sécuriser la borne Wi-Fi, je l'ai d'abord démarrée puis j'ai lancé son bilan de vérification quotidien (choix 8)
 afin d'identifier les failles sans fil (mot de passe d'usine, réseau ouvert et accès invité).
 J'ai ensuite remplacé le mot de passe administrateur par défaut de la borne pour éviter que n'importe qui puisse modifier ses réglages,
 et j'ai protégé le réseau sans fil avec un chiffrement sécurisé (WPA2/WPA3) et un mot de passe complexe.
 Enfin, j'ai désactivé les options inutiles comme le réseau invité non sécurisé et le bouton de connexion rapide (WPS),
 ce qui a permis de fermer toutes les failles Wi-Fi lors du test final.
