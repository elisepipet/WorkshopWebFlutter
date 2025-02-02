# Workshop : Création d’une application en Flutter avec authentification et gestion de posts

## Objectif
L’objectif de ce workshop est d’apprendre à développer une application en Flutter en intégrant une authentification et une gestion de posts via une API REST.

---

## Étapes détaillées du Workshop

### **1. Mise en place de l'environnement de développement**

#### **Installation de Flutter et des outils nécessaires**
- Suivre les instructions d'installation de Flutter selon votre système d'exploitation :
  - Fedora :
    ```sh
    sudo dnf install clang cmake curl git make ninja unzip which
    cd ~ && git clone https://github.com/flutter/flutter.git -b stable
    echo 'export PATH="$HOME/flutter/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc
    flutter doctor
    ```
  - Ubuntu :
    ```sh
    sudo apt update
    sudo apt install curl git unzip xz-utils clang cmake ninja-build pkg-config libgtk-3-dev
    cd ~ && git clone https://github.com/flutter/flutter.git -b stable
    echo 'export PATH="$HOME/flutter/bin:$PATH"' >> ~/.bashrc && source ~/.bashrc
    flutter doctor
    ```
  - macOS avec HomeBrew :
    ```sh
    brew install flutter
    flutter doctor
    ```
  - Plus de détails : [Documentation officielle de Flutter](https://flutter.dev/docs/get-started/install)

#### **Création et exploration du projet Flutter**
- Créer un projet Flutter :
  ```sh
  flutter create my_app
  cd my_app
  flutter run -d chrome
  ```
- Comprendre la structure d’un projet Flutter (dossier lib/, fichier main.dart, widgets, etc.).

---

### **2. Gestion de l'authentification (Login/Register)**

### **Documentation API Workshop**
  - [Documentation de notre API](https://elisepipet.github.io/WorkshopFlutterSwagger/)
  - API Address: http://jepgo.francecentral.cloudapp.azure.com

#### **Création des pages de connexion et d'inscription**
- Interface utilisateur avec TextFields pour l’email et le mot de passe.
- Bouton de soumission du formulaire.

#### **Connexion et inscription via API REST**
- Ajout du package `http` dans `pubspec.yaml` :
  ```yaml
  dependencies:
    http: ^0.13.4
  ```
- Envoi des données d'authentification via une requête `POST`.
- Gestion des réponses API (succès, erreurs).

---

### **3. Recherche et implémentation du stockage du token**

- Utilisation de `shared_preferences` ou `flutter_secure_storage` pour stocker le token.
- Ajout de la vérification de l'authentification à chaque démarrage.
- Redirection de l'utilisateur vers la page d'accueil s'il est déjà connecté.

---

### **4. Affichage des posts existants**

- Récupération des posts via une requête `GET`.
- Affichage des posts dans un `ListView`.
- Utilisation de `FutureBuilder` pour gérer le chargement des données.

---

### **5. Création d'un nouveau post**

- Ajout d'un bouton `+` sur la page d'accueil.
- Lors du clic, redirection vers une page de création de post.

---

### **6. Page de création de post**

- Ajout de `TextFields` pour le titre et le contenu du post.
- Bouton pour soumettre le post via une requête `POST`.
- Retour automatique à la liste des posts après création.

---

### **7. Gestion des commentaires**

#### **Affichage des commentaires**
- Bouton pour afficher les commentaires d'un post.
- Récupération et affichage des commentaires via une requête `GET`.

#### **Ajout d'un commentaire**
- Bouton permettant d'ajouter un commentaire.
- `TextField` pour saisir le commentaire.
- Envoi via une requête `POST`.

---

### **8. Affichage des posts d'un utilisateur**

- Lorsqu'on clique sur le nom d'un utilisateur, affichage de ses posts.
- Requête `GET` pour récupérer les posts filtrés par utilisateur.
