# Bilan de la borne : kenyonn-Laptop-12-13th-Gen-Intel-Core, 12/11/2026 14:19

Pour la plupart des objectifs, j'ai simplement repris les commanandes à appliquer dans la guilde. Sachant que la solution se trouvait souvent sur l'interface LuCi 
Score : **100 / 100** (VERT)

| État | Point | Points |
|---|---|---|
| OK | Mot de passe administrateur défini | via l’interface LuCI (Système → Administration) | Un mot de passe root fort empêche l’accès non autorisé à la configuration complète de la borne. |
| OK | Wi-Fi principal allumé, nom personnalisé (Bastion-Archaon) | Le SSID Bastion-Archaon (pas le nom par défaut du fabricant) évite de révéler le modèle exact de la borne, ce qui limiterait la recherche de failles connues par un attaquant. |
| OK | Chiffrement WPA3 ou WPA2/WPA3 (sae-mixed) | Le chiffrement foit afficher "encryption='sae-mixed'" ou "sa"e. SAE (Simultaneous Authentication of Equals) remplace l’ancien WPA2-PSK, résistant aux attaques hors-ligne par dictionnaire. |
| OK | Clé Wi-Fi d'au moins 12 caractères | Plus la clé est longue et plus une attaque par bruteforce est longue à réussir. |
| OK | Réseau invité séparé et isolé | Le réseau invité doit être sur un VLAN/SSID distinct, sans accès au réseau principal (dont l'isolation réseau). Ainsi, un visiteur compromis ne peut pas atteindre mes appareils personnels. |
| OK | Administration fermée côté Internet (WAN) | Principe est que l’interface d’administration ne doit jamais être exposée directement sur Internet. Sinon n’importe qui dans le monde peut tenter de s’y connecter. |
| OK | SSH de la borne par clé seulement | Comme vu dans ma quête précédente, cela permet d'éliminer le risque de bruteforce par mot de passe, seule la possession de la clé privée permet l’accès. |
| OK | Interface web en HTTPS | Elle chiffre les échanges entre mon navigateur et LuCI contre l’interception sur le réseau. |
| OK |Configuration de la borne sauvegardée | En cas de panne/reset de la borne, je peux restaurer toute la config sans tout reconfigurer |.
