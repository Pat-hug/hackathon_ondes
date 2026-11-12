# Bilan du bastion : ubuntu, 10/11/2026 14:15

Score : **100 / 100** (VERT)
| État | Point | Points | Notes |
|---|---|---|---|
| OK | Système à jour | +15 | Mettre les paquets à jour pour bénéficier des derniers correctifs de sécurité |
| OK | Mises à jour de sécurité automatiques | +10 | |
| OK | Pare-feu actif, connexions entrantes refusées par défaut | +15 | Empêche les connexions entrantes non autorisées |
| OK | Compte root verrouillé | +5 | |
| OK | Aucun compte sans mot de passe | +5 | Empêche la connexion avec un mot de passe vide |
| OK | Un seul administrateur : toi | +10 | Centralise les privilèges d'administration |
| OK | Verrouillage automatique de l'écran (10 min au plus) | +5 | Empêche l'accès à la session laissée sans surveillance |
| OK | Dossier personnel fermé aux autres comptes (750) | +5 | |
| OK | Aucun serveur SSH installé (rien à attaquer de ce côté) | +15 | |
| OK | Aucun port TCP ouvert au réseau, sauf SSH | +10 | Moins de ports ouverts réduit la surface d'attaque |
| Non vérifiable | Fail2ban surveille SSH | Retiré du calcul | |
| Info | AppArmor actif : chaque programme protégé reste dans sa cage | | |
| Info | Disque chiffré (LUKS) : on n'y touche pas cette semaine | | |
