# Bilan de la borne : YXN.EXE, 10/11/2026 14:15

Score : **90 / 100** (VERT)

| État | Point | Points |
|---|---|---|
| OK | Mot de passe administrateur défini | +15 |
| OK | Wi-Fi principal allumé, nom personnalisé (Mercator) | +5 |
| OK | Chiffrement WPA3 ou WPA2/WPA3 (sae-mixed) | +20 |
| OK | Clé Wi-Fi d'au moins 12 caractères | +10 |
| OK | Réseau invité séparé et isolé | +15 |
| OK | Administration fermée côté Internet (WAN) | +10 |
| A faire | SSH de la borne par clé seulement : ajoute ta clé, teste-la, puis coupe les mots de passe (quête 13) | 0 / 10 |
| OK | Interface web en HTTPS | +10 |
| OK | Configuration de la borne sauvegardée | +5 |
| Info | Version d'OpenWrt : 25.12.6 (vérifie sur openwrt.org qu'elle est encore suivie) | |



---

## 📊 Analyse du bilan et actions réalisées

Ce tableau évalue le niveau de durcissement et la configuration de ma borne Wi-Fi fonctionnant sous **OpenWrt (version 25.12.6)**. Avec un score global de **90 / 100 (VERT)**, l'infrastructure respecte les bonnes pratiques de sécurité réseau et d'administration.

### ✅ Actions mises en place (Points validés)

* **Sécurisation de l'administration (`+35 pts`) :** 
  * Définition d'un mot de passe administrateur robuste (`+15`) pour empêcher tout accès non autorisé à la configuration.
  * Activation du protocole **HTTPS** (`+10`) afin de chiffrer les échanges sur l'interface web et éviter l'interception des identifiants sur le réseau.
  * Fermeture de l'accès d'administration côté **WAN / Internet** (`+10`) pour limiter l'exposition de la borne aux attaques externes.

* **Protection du réseau Wi-Fi principal (`+35 pts`) :** 
  * Activation et personnalisation du SSID sous le nom *Mercator* (`+5`) pour l'identifier clairement.
  * Mise en place du chiffrement **WPA3 / WPA2-WPA3 (`sae-mixed`)** (`+20`), offrant une protection moderne contre le cassage de clés tout en restant compatible avec les appareils plus anciens.
  * Configuration d'une clé de sécurité complexe d'au moins **12 caractères** (`+10`) pour contrer les attaques par force brute.

* **Cloisonnement et continuité (`+20 pts`) :** 
  * Création et isolation d'un **réseau invité** (`+15`) afin de séparer le trafic des visiteurs du réseau local principal et protéger les machines internes.
  * Réalisation d'une **sauvegarde complète** de la configuration (`+5`) pour permettre une restauration rapide en cas d'incident ou de mauvaise manipulation.

### ⏳ Point restant à finaliser

* **Durcissement de l'accès SSH (`0 / 10`) :** Le service SSH de la borne autorise encore la connexion par mot de passe. Pour atteindre les **100 / 100**, il reste à déployer ma clé publique SSH sur l'équipement, vérifier que l'authentification par clé fonctionne correctement, puis désactiver totalement la connexion par mot de passe (étape prévue dans la **quête 13**).
