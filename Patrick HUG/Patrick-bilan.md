# Bilan du bastion : Ubuntu, 10/11/2026 à 14:15

Score : **100 / 100** (VERT)

| État | Point | Points | Notes |
|---|---|---|---|
| OK | Système à jour | +15 | Mettre les paquets à jour pour bénéficier des derniers correctifs de sécurité |
| OK | Mises à jour de sécurité automatiques | +10 | Installe automatiquement les correctifs de sécurité |
| OK | Pare-feu actif, connexions entrantes refusées par défaut | +15 | Empêche les connexions entrantes non autorisées |
| OK | Compte root verrouillé | +5 | Empêche la connexion par mot de passe au compte root ; les tâches d'administration passent par sudo |
| OK | Aucun compte sans mot de passe | +5 | Empêche la connexion avec un mot de passe vide |
| OK | Un seul administrateur : toi | +10 | Centralise les privilèges d'administration |
| OK | Verrouillage automatique de l'écran (10 min au plus) | +5 | Empêche l'accès à la session laissée sans surveillance |
| OK | Dossier personnel fermé aux utilisateurs hors du groupe propriétaire (750) | +5 | Améliore la confidentialité du dossier personnel en limitant son accès |
| OK | Aucun serveur SSH installé (rien à attaquer de ce côté) | +15 | Réduit la surface d'attaque en l'absence de service SSH |
| OK | Aucun port TCP ouvert au réseau, sauf SSH | +10 | Un nombre réduit de ports ouverts limite la surface d'attaque |
| Non vérifiable | Fail2ban surveille SSH | Retiré du calcul | |
| Info | AppArmor actif : chaque programme protégé reste dans sa cage | | |
| Info | Disque chiffré (LUKS) : on n'y touche pas cette semaine | | |