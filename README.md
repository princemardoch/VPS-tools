# install-python-in-vps

### **Étapes pour installer Python 3.12 sur Debian/Ubuntu**

#### **1. Mettre à jour le système**

Commencez par mettre à jour les paquets existants :

```bash
sudo apt update && sudo apt upgrade -y
```

#### **2. Installer les dépendances nécessaires**

Python nécessite plusieurs paquets de développement pour être compilé à partir des sources :

```bash
sudo apt install -y build-essential checkinstall \
libreadline-gplv2-dev libncursesw5-dev libssl-dev \
libsqlite3-dev tk-dev libgdbm-dev libc6-dev libbz2-dev \
libffi-dev zlib1g-dev
```

#### **3. Télécharger la dernière version de Python**

Visitez le site officiel de Python pour vérifier la dernière version disponible. Au moment de la rédaction, Python 3.12.0 est la dernière version stable.

Téléchargez les sources :

```bash
cd /usr/src
sudo wget https://www.python.org/ftp/python/3.12.0/Python-3.12.0.tgz
```

> **Remarque :** Remplacez `3.12.0` par la version souhaitée si nécessaire.

#### **4. Extraire l'archive**

```bash
sudo tar xzf Python-3.12.0.tgz
```

#### **5. Compiler Python à partir des sources**

Entrez dans le répertoire extrait :

```bash
cd Python-3.12.0
```

Configurez la compilation avec des optimisations :

```bash
sudo ./configure --enable-optimizations
```

Compilez et installez Python :

```bash
sudo make altinstall
```

> **Pourquoi `altinstall` ?** L'utilisation de `make altinstall` empêche l'écrasement de la version par défaut de Python fournie par le système.

#### **6. Vérifier l'installation**

```bash
python3.12 --version
```

Vous devriez voir :

```
Python 3.12.0
```

#### **7. Installer pip pour Python 3.12**

Téléchargez le script `get-pip.py` :

```bash
sudo wget https://bootstrap.pypa.io/get-pip.py
```

Installez pip :

```bash
sudo python3.12 get-pip.py
```

#### **8. Vérifier l'installation de pip**

```bash
pip3.12 --version
```

---

### **Alternative : Utiliser un PPA (pour Ubuntu)**

Si vous utilisez Ubuntu, vous pouvez installer Python 3.12 via le PPA `deadsnakes`.

#### **1. Ajouter le PPA**

```bash
sudo apt install software-properties-common -y
sudo add-apt-repository ppa:deadsnakes/ppa
sudo apt update
```

#### **2. Installer Python 3.12**

```bash
sudo apt install python3.12 python3.12-distutils -y
```

#### **3. Installer pip**

```bash
wget https://bootstrap.pypa.io/get-pip.py
sudo python3.12 get-pip.py
```

---

### **Utilisation d'environnements virtuels**

Il est recommandé d'utiliser des environnements virtuels pour gérer vos projets Python.

#### **1. Créer un environnement virtuel**

```bash
python3.12 -m venv myenv
```

#### **2. Activer l'environnement virtuel**

```bash
source myenv/bin/activate
```
