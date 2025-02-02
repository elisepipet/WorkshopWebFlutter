## Workshop : Création d’une application web en Flutter avec authentification

### Objectif

L’objectif de ce workshop est d’apprendre à développer une application web en Flutter intégrant une authentification via une API REST.

---

## Étapes détaillées du Workshop

### **1. Mise en place de l’environnement de développement (40 min)**

#### **Installation de Flutter et des outils nécessaires**

- **Documentation officielle de Flutter** : [https://flutter.dev/docs/get-started/install](https://flutter.dev/docs/get-started/install)

#### **Création et exploration du projet Flutter**

- Créer un projet Flutter :
  ```bash
  flutter create my_app
  cd my_app
  flutter run -d chrome
  ```
- Comprendre la structure d’un projet Flutter (dossier `lib/`, fichier `main.dart`, widgets, etc.).
- Créer une page d’accueil simple (`HomePage`).

---

### **2. Découverte de l’API et gestion des requêtes HTTP (50 min)**

#### **Introduction aux API REST**

- **Introduction aux API REST** : [https://developer.mozilla.org/fr/docs/Learn/JavaScript/Client-side_web_APIs/Introduction](https://developer.mozilla.org/fr/docs/Learn/JavaScript/Client-side_web_APIs/Introduction)

#### **Ajout du package `http` et première requête**

- Ajouter la dépendance au fichier `pubspec.yaml` :
  ```yaml
  dependencies:
    http: ^0.13.4
  ```
- Effectuer une requête GET vers une API publique et afficher les données récupérées dans un `ListView`.

---

### **3. Création des pages de connexion et d’inscription (1h)**

#### **Interface utilisateur pour la connexion et l’inscription**

- Création des pages `LoginPage` et `RegisterPage` avec `TextField` pour l’email et le mot de passe.
- Ajout d’un bouton pour soumettre le formulaire.

#### **Connexion et inscription avec l’API**

- Envoi des données d’authentification via une requête POST.
- Gestion des réponses de l’API (succès, erreurs).

---

### **4. Gestion du token et authentification persistante (50 min)**

#### **Introduction aux tokens JWT**

- **Introduction aux tokens JWT** : [https://jwt.io/introduction](https://jwt.io/introduction)
- Recherche et implémentation d’une solution pour stocker le token après authentification.
- Vérifier si un utilisateur est déjà authentifié au lancement de l’application et le rediriger vers `HomePage` si c’est le cas.

---

### **5. Effectuer des requêtes authentifiées (40 min)**

#### **Ajout du token aux requêtes HTTP**

- Modification des requêtes pour inclure le token dans l’en-tête.
- Récupérer des données protégées par l’API et les afficher dans une nouvelle page.

---

### **6. Déconnexion et gestion avancée des erreurs (40 min)**

- Supprimer le token de la solution de stockage choisie et rediriger l’utilisateur vers la page de connexion.
- Gérer les erreurs de connexion et afficher des messages explicites pour l’utilisateur.

---

### **7. Améliorations et fonctionnalités avancées**

#### **Ajout d’un profil utilisateur**

- Permettre aux utilisateurs de mettre à jour leurs informations personnelles.

#### **Ajout d’un dark mode**

- Permettre aux utilisateurs de basculer entre un mode clair et un mode sombre.
- Sauvegarder la préférence de l’utilisateur.

#### **Optimisation des performances**

- Réduire la consommation de ressources en optimisant les appels réseau et en mettant en cache certaines données.
- Charger les images de manière asynchrone avec un cache local.
