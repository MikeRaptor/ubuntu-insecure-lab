# Identifiants — VM du TP

## Lynis

Indice **Hardening** mesuré sur la VM telle qu’importée (sans vos changements) : **51**.  
Comparer en fin de séance après installation de Lynis (voir [README.md](README.md)).

---

Comptes **volontairement faibles** à traiter pendant le TP :

| Compte     | Mot de passe        | Remarque |
|------------|---------------------|----------|
| `labadmin` | `Labadmin1!`        | `sudo` avec mot de passe. |
| `root`     | `LabRoot_ChangeMe!` | Connexion SSH root autorisée (mauvaise pratique). |
| `student`  | `student`           | `sudo` en NOPASSWD (mauvaise pratique). |

- **Hostname** : `insecure-lab`

Si vous modifiez les mots de passe en groupe, notez ceux en vigueur.
