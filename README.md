# Bastion ONDES

## Membres

| Membre | Rôle |
|---|---|
| Patrick | Chef de guilde |
| Kil | Gardien |
| Kennyonn | Rempart |
| Yassine | Passeur |

## Glitch lundi

### Glitch 1 : modification des droits

Restauration des droits du dossier personnel :

```bash
chmod 750 ~
```

### Glitch 2 : fichier caché

Afficher les fichiers cachés pour repérer `.Glitch` :

```bash
ls -la
```

Supprimer le fichier :

```bash
rm .Glitch
```

### Glitch 3 : fichier `Document/plan-du-glitch.txt`

Accéder au dossier et supprimer le fichier :

```bash
cd Document
rm plan-du-glitch.txt
```