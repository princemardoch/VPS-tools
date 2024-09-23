# install-python-in-vps

**Tutoriel simple pour installer Homebrew et Python 3.12 sur Debian**

Suivez ces étapes pour installer Homebrew et utiliser celui-ci pour installer Python 3.12 sur votre système Debian.

---

### **Étape 1 : Créer un utilisateur non-root**

Si vous n'avez pas déjà un utilisateur non-root, créez-en un (par exemple, `utilisateur`) :

```bash
adduser utilisateur
```

```bash
sudo usermod -aG sudo nouvel_utilisateur
```

Suivez les instructions pour définir le mot de passe et les informations de l'utilisateur.

---

### **Étape 2 : Se connecter en tant qu'utilisateur non-root**

Connectez-vous avec le nouvel utilisateur :

```bash
su - utilisateur
```

---

### **Étape 3 : Installer les dépendances nécessaires**

Mettez à jour les paquets et installez les dépendances requises :

```bash
sudo apt update
sudo apt install build-essential curl file git -y
```

---

### **Étape 4 : Installer Homebrew**

Exécutez le script d'installation de Homebrew :

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

---

### **Étape 5 : Configurer Homebrew**

Ajoutez Homebrew à votre environnement :

```bash
echo 'eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"' >> ~/.profile
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"
```

---

### **Étape 6 : Installer Python 3.12 avec Homebrew**

Installez Python 3.12 :

```bash
brew install python@3.12
```

---

### **Étape 7 : Vérifier l'installation**

Vérifiez que Python 3.12 est installé correctement :

```bash
python3.12 --version
```

Vous devriez voir :

```
Python 3.12.0
```

---

**Vous avez maintenant installé Homebrew et Python 3.12 sur votre système Debian !**
