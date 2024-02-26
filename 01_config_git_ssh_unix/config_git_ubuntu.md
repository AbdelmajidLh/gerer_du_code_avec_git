Voici le markdown git avec le titre ajouté :

```markdown
# Configuration des clés SSH pour GitHub

# Générer la clé SSH

```bash
ssh-keygen -t ed25519 -C abdelmajid.elhou@gmail.com
```

(Appuyez sur Enter sans entrer de mot de passe jusqu'à la génération de la clé)

# Vérification : sortie attendue : Agent pid 45xxx

```bash
eval "$(ssh-agent -s)"
```

# Ouvrir le fichier de configuration

```bash
nano ~/.ssh/config
```

# Ajouter ceci dans le fichier

```
Host *
 AddKeysToAgent yes
 IdentityFile ~/.ssh/id_ed25519
```

# Ajouter la clé SSH à l'agent

```bash
ssh-add ~/.ssh/id_ed25519
```

# Aller sur votre compte GitHub

- SSH and GPG keys > New SSH Key > Titre et colle la ligne obtenue avec : `cat ~/.ssh/id_ed25519.pub`

# Tester la clé dans votre terminal

```bash
ssh -T git@github.com
```
```

Cela inclut maintenant le titre "Configuration des clés SSH pour GitHub" pour mieux décrire l'ensemble du processus.
