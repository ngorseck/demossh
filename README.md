# README : Générer une clé SSH pour GitHub sur macOS et Windows

Ce guide vous guidera à travers les étapes pour générer une clé SSH pour GitHub sur macOS et Windows. Pour une documentation détaillée, vous pouvez consulter la documentation officielle de GitHub [ici](https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent).

## Table des matières

1. [Générer une clé SSH sur macOS](#générer-une-clé-ssh-sur-macos)
2. [Ajouter la clé SSH à l'agent ssh sur macOS](#ajouter-la-clé-ssh-à-lagent-ssh-sur-macos)
3. [Générer une clé SSH sur Windows](#générer-une-clé-ssh-sur-windows)
4. [Ajouter la clé SSH à l'agent ssh sur Windows](#ajouter-la-clé-ssh-à-lagent-ssh-sur-windows)
5. [Ajouter la clé SSH à GitHub](#ajouter-la-clé-ssh-à-github)

---

## Générer une clé SSH sur macOS

1. **Ouvrir le Terminal** :
   Ouvrez l'application Terminal.

2. **Générer une nouvelle clé SSH** :
   Exécutez la commande suivante, en remplaçant `your_email@example.com` par votre adresse email GitHub :
   ```sh
   ssh-keygen -t ed25519 -C "your_email@example.com"
   ```
   - Vous serez invité à "Entrer un fichier dans lequel enregistrer la clé." Appuyez sur Entrée pour accepter l'emplacement de fichier par défaut.

## Ajouter la clé SSH à l'agent ssh sur macOS

1. **Assurez-vous que ssh-agent est en cours d'exécution** :
   Démarrez l'agent ssh en arrière-plan :

   ```sh
   eval "$(ssh-agent -s)"

   ```

2. **Ajouter votre clé privée SSH à l'agent ssh** :
   Exécutez la commande suivante, en supposant l'emplacement de fichier par défaut (~/.ssh/id_ed25519) :
   ```sh
   ssh-add ~/.ssh/id_ed25519"
   ```

## Générer une clé SSH sur Windows

1. **Ouvrir Git Bash** :
   Ouvrez l'application Git Bash.

2. **Générer une nouvelle clé SSH** :
   Exécutez la commande suivante, en remplaçant your_email@example.com par votre adresse email GitHub :

   ```sh
   ssh-keygen -t ed25519 -C "your_email@example.com"

   ```

- Vous serez invité à "Entrer un fichier dans lequel enregistrer la clé." Appuyez sur Entrée pour accepter l'emplacement de fichier par défaut.
- Entrez une phrase secrète sécurisée lorsqu'on vous le demande.

## Ajouter la clé SSH à l'agent ssh sur Windows

1. **Assurez-vous que ssh-agent est en cours d'exécution** :
   Démarrez l'agent ssh en arrière-plan :

   ```sh
   eval "$(ssh-agent -s)"

   ```

2. **Ajouter votre clé privée SSH à l'agent ssh** :
   Exécutez la commande suivante, en supposant l'emplacement de fichier par défaut (~/.ssh/id_ed25519) :

   ```sh
   ssh-add ~/.ssh/id_ed25519

   ```

   ## Ajouter la clé SSH à GitHub

3. Copier la clé SSH dans votre presse-papiers :
   Utilisez la commande suivante pour copier la clé dans votre presse-papiers :

   ```sh
   pbcopy < ~/.ssh/id_ed25519.pub

   ```

Pour Windows :

```sh
clip < ~/.ssh/id_ed25519.pub

```

2. Ajouter la clé à votre compte GitHub :

- Allez sur GitHub et connectez-vous.
- Dans le coin supérieur droit de n'importe quelle page, cliquez sur votre photo de profil, puis cliquez sur Settings.
- Dans la barre latérale gauche, cliquez sur SSH and GPG keys.

![sshTab](https://utfs.io/f/c0588128-615e-419f-9352-8c9c7e28c176-vrydv4.png)

- Cliquez sur New SSH key ou Add SSH key.

![ssh](https://utfs.io/f/8fe87100-8b1b-40ab-9f8c-484685d5db08-2g3s.png)

- Dans le champ "Title", ajoutez une étiquette descriptive pour la nouvelle clé.
- Collez votre clé dans le champ "Key".
- Cliquez sur Add SSH key.
- Confirmez votre mot de passe GitHub si demandé.

```

```
