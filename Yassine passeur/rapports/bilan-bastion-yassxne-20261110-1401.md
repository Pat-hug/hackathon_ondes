# Bilan du bastion : YXN.EXE, 10/11/2026 14:01

Score : **65 / 100** (ORANGE)

| État | Point | Points |
|---|---|---|
| A faire | Système à jour (2 paquets en attente) : sudo apt update puis sudo apt upgrade (quête 3) | 0 / 15 |
| OK | Mises à jour de sécurité automatiques | +10 |
| OK | Pare-feu actif, entrées refusées par défaut | +15 |
| OK | Compte root verrouillé | +5 |
| OK | Aucun compte sans mot de passe | +5 |
| OK | Un seul administrateur : toi | +10 |
| OK | Verrouillage automatique de l'écran (10 min au plus) | +5 |
| OK | Dossier personnel fermé aux autres comptes (750) | +5 |
| A faire | Serveur SSH durci (root : prohibit-password, mot de passe : yes, clavier interactif : no) : PermitRootLogin no et PasswordAuthentication no, après avoir testé ta clé (quête 8) | 0 / 15 |
| OK | Aucun port TCP ouvert au réseau, sauf SSH | +10 |
| A faire | fail2ban surveille SSH : sudo apt install fail2ban, puis la prison sshd (quête 9) | 0 / 5 |
| Info | AppArmor actif : chaque programme protégé reste dans sa cage | |
| Info | Disque non chiffré : on n'y touche pas cette semaine, à signaler au maître du jeu | |
