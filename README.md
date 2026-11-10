# TP — Durcissement d’une machine Ubuntu

**Contenu de ce dépôt :** consignes, identifiants et lien pour télécharger l’appliance VirtualBox.

## Indice Lynis de référence

La VM fournie a été auditée une fois (Lynis 3.0.x, `lynis audit system`).  
**Hardening index sans modification : 51** (échelle 0–100 : une valeur **plus élevée** indique en général un système **plus durci**).

Inutile d’installer Lynis au début du TP. En fin de séance, vous pourrez mesurer votre propre indice et le comparer à **51**.

## Télécharger et importer l’appliance

Fichiers sur la page **[Releases](https://github.com/MikeRaptor/ubuntu-insecure-lab/releases)** (l’archive est découpée pour respecter la limite de taille par fichier sur GitHub) :

1. Télécharger **`ubuntu-insecure-lab-amd64.ova.part-aa`** et **`ubuntu-insecure-lab-amd64.ova.part-ab`** dans le même dossier.
2. Reconstituer le `.ova` :

```bash
cat ubuntu-insecure-lab-amd64.ova.part-aa ubuntu-insecure-lab-amd64.ova.part-ab > ubuntu-insecure-lab-amd64.ova
```

3. VirtualBox : **Fichier → Importer une appliance…** → sélectionner **`ubuntu-insecure-lab-amd64.ova`**.

Somme de contrôle (optionnel) du fichier `.ova` reconstitué :

```text
eb40dbfafca901005150ea225249b90c8682ef8357c1589bee00576c1fcbd9b3  ubuntu-insecure-lab-amd64.ova
```

## Déroulé du TP

1. Démarrer la VM et se connecter (console VirtualBox ou SSH, selon le mode d’accès disponible).
2. Passer en revue services, comptes, pare-feu, SSH, permissions, écoutes réseau, etc.
3. Appliquer des correctifs et les documenter (commandes, fichiers modifiés, justification).

## Identifiants

Voir **[IDENTIFIANTS.md](IDENTIFIANTS.md)**.

## Accès SSH depuis l’hôte (si NAT avec redirection)

Si le port **22** de la VM est exposé sur **2222** de la machine hôte :

```bash
ssh -p 2222 labadmin@127.0.0.1
```

Sinon, utiliser la console graphique de la VM.

## Lynis en fin de séance (optionnel)

```bash
sudo apt update
sudo apt install -y lynis
sudo lynis audit system
```

Comparer le **Hardening index** obtenu au **51** de référence ; l’audit complet reste indicatif.

## Mise en garde

- Ne pas utiliser cette VM ni ces identifiants sur un réseau de production ou exposé à Internet sans cadre encadré.
- Des services mal configurés (DNS, Redis, etc.) peuvent poser problème en environnement réel : rester en **NAT** ou réseau de cours.
