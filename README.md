# Suite MAE — canal public de mises à jour

Ce dépôt sert **uniquement à distribuer les mises à jour compilées de Suite MAE Studio**.

- Le code source de Suite MAE reste dans un dépôt privé distinct.
- Les romans, paramètres personnels, modèles d'IA et sauvegardes ne sont pas publiés ici.
- Les fichiers d'installation Windows sont distribués dans les **GitHub Releases**, sans GitHub Actions.
- Chaque mise à jour est annoncée par un fichier `latest.json` signé avec une clé Ed25519, et le programme contrôle aussi son empreinte SHA-256 avant installation.
- **Ne jamais déposer ici la clé privée de signature** (`.pem`, archives de clé, secrets ou jetons d'accès).

## État actuel

**Canal de référence publié.** Le fichier `latest.json` est disponible et signé. Il désigne uniquement la version déjà installée sur le PC d'essai : **ne pas la retélécharger comme une nouvelle mise à jour**. La connexion au PC reste à valider.

Le fichier `verification.json` permet de tester que les liens GitHub renvoient du JSON brut, contrairement aux liens Google Drive qui ont échoué sur le PC d'essai.

## Procédure de publication (sans minute GitHub Actions)

1. Compiler et vérifier la version Windows ailleurs ; ne pas publier une archive contenant uniquement les sources.
2. Vérifier l'archive Windows et conserver une copie dans Google Drive.
3. Créer une nouvelle **Release** GitHub ; joindre le ZIP compilé comme *asset* (pas comme fichier du dépôt).
4. Préparer `latest.json` avec l'URL HTTPS **exacte** de cet asset, sa révision, son SHA-256 et une signature Ed25519 valide. La signature dépend notamment de l'URL du ZIP.
5. Publier `latest.json` **en dernier**, après vérification que le ZIP est téléchargeable.
6. Tester le bouton de Suite MAE et l'installation sous Windows avec des copies de romans.

**Attention :** le paquet de référence du 17 octobre 2026 est déjà installé sur le PC d'essai. Il ne doit pas être annoncé comme une nouvelle mise à jour à installer.

## Liens

- Vérification JSON brute : `https://raw.githubusercontent.com/dominiaquedeubras-glitch/Suite-MAE-Updates/main/verification.json`
- Canal signé : `https://raw.githubusercontent.com/dominiaquedeubras-glitch/Suite-MAE-Updates/main/latest.json`
- Fichiers Windows : onglet **Releases** de ce dépôt.
