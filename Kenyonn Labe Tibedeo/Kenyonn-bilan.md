# Bilan du bastion : kenyonn-Laptop-12-13th-Gen-Intel-Core, 10/11/2026 14:22

Quand j'ai affiché le menu du bilan pour le première fois (mardi), le score était de 65 %. Je devais résoudre le système de mise à jour et l'activation du pare-feu. J'ai tout de même essayé de rechercher les commandes pour les autres quêtes ainsi que leur principe. 
Score : **100 / 100** (VERT)

| État | Point | Points | Notes |
|---|---|---|---|
| OK | Système à jour | sudo apt update / udo apt upgrade | Le principe est de lister les paquets qui ont des mises à jour disponibles puis de les installer. |
| OK | Mises à jour de sécurité automatiques | sudo apt install -y unattended-upgrades > sudo dpkg-reconfigure -plow unattended-upgrades > cat /etc/apt/apt.conf.d/20auto-upgrades | Leprincipe est de vérifier que unattended-upgrades est activé. Ainsi, le système s’auto-corrige sans attendre une action manuelle. |
| OK | Pare-feu actif, entrées refusées par défaut | sudo ufw status verbose | La commande doit afficher "Status: active et deny (incoming)". C'est le principe du moindre privilège réseau : tout est bloqué sauf ce qu’on autorise explicitement. |
| OK | Compte root verrouillé | sudo passwd -S root | La commande doit afficher L (Locked) et non P (mot de passe actif). Ainsi, elle empêche toute connexion directe en root (par mot de passe) et oblige à passer par sudo avec traçabilité. |
| OK | Aucun compte sans mot de passe | sudo awk -F: '($2==""){print $1}' /etc/shadow | N doite rien renvoyer car uUn compte sans mot de passe est synonyme de porte ouverte à qui s’assoit devant la machine. |
| OK | Un seul administrateur : toi | getent group sudo | L'objectif est de lister les membres du groupe. Le principe est le suivant: moins de comptes avec privilèges pour moins de surface d’attaque. |
| OK | Verrouillage automatique de l'écran (10 min au plus) | gsettings get org.gnome.desktop.session idle-delay | Le verrouillage donne le délai en secondes avant verrouillage (600 = 10 min). Il protège aussi contre l’accès physique si je m’absente. [
| OK | Dossier personnel fermé aux autres comptes (750) | ls -ld /home/kenyonn | Cette commande doit afficher "drwxr-x---". Le 7 = moi (tout), 5 = groupe (lecture/exécution seulement), 0 = autres (rien). Elle empêche aussi les autres utilisateurs locaux de fouiller mon /home. |
| OK | Aucun serveur SSH installé (rien à attaquer de ce côté) | systemctl status ssh | En effet, si rien n’est installé/actif, aucune porte d’entrée distante possible sur cette machine. Donc rien à exploiter de ce côté. |
| OK | Aucun port TCP ouvert au réseau, sauf SSH | sudo ss -tlnp | Comme vu dans la quête “Qui écoute ?”, cette commande vérifie qu’aucun port TCP n’écoute sur 0.0.0.0/[::] à part SSH (22) si besoin. Moins de services exposés donc  moins de cibles. |
fail2ban surveille SSH | sudo fail2ban-client status sshd / "fail2ban" bannit temporairement une IP après plusieurs tentatives de connexion échouées contre le bruteforce SSH. |
