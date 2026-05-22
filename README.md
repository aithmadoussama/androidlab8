# LAB 8 — Android Multithreading & AsyncTask

## 📌 Description

Ce projet Android démontre l’utilisation du **multithreading** en Java avec :

- `Thread`
- `Handler`
- `AsyncTask`

L’objectif principal est de comprendre comment exécuter des tâches longues en arrière-plan sans bloquer l’interface utilisateur (**UI Thread**).

---

# 🎯 Objectifs pédagogiques

Ce TP permet de :

- Comprendre le fonctionnement du **UI Thread**
- Utiliser un **Thread** pour exécuter des tâches longues
- Mettre à jour l’interface avec un **Handler**
- Utiliser **AsyncTask** pour gérer les traitements en arrière-plan
- Manipuler :
  - `ProgressBar`
  - `ImageView`
  - `Toast`
  - `TextView`

---

# 🛠 Technologies utilisées

- Java
- Android Studio
- Android SDK
- Thread
- Handler
- AsyncTask

---

# 📂 Structure du projet

```text
lab8/
│
├── app/
│   ├── src/
│   │   ├── main/
│   │   │   ├── java/com/example/lab8/
│   │   │   │   └── MainActivity.java
│   │   │   ├── res/
│   │   │   └── AndroidManifest.xml
│
├── build.gradle.kts
├── settings.gradle.kts
└── gradle.properties
```

---

# 🚀 Fonctionnalités

## 1️⃣ Chargement d’image avec Thread

Lorsqu’on clique sur le bouton :

- un `Thread` démarre
- une tâche longue est simulée
- l’image est chargée en arrière-plan
- l’interface reste réactive

### Concepts utilisés

- `Thread`
- `Handler`
- `Bitmap`
- `ImageView`

---

## 2️⃣ Calcul lourd avec AsyncTask

Lorsqu’on clique sur le bouton :

- un calcul intensif démarre
- la progression est affichée
- la barre de progression se met à jour
- le résultat final est affiché

### Concepts utilisés

- `AsyncTask`
- `doInBackground()`
- `publishProgress()`
- `onProgressUpdate()`
- `onPostExecute()`

---

## 3️⃣ Test de réactivité UI

Le bouton Toast permet de vérifier que :

✅ l’interface utilisateur ne se bloque pas pendant l’exécution des tâches longues.

---

# 🖥 Interface utilisateur

L’application contient :

- un `TextView`
- une `ProgressBar`
- une `ImageView`
- trois boutons :
  - Charger image (Thread)
  - Calcul lourd (AsyncTask)
  - Tester UI

---

# 📖 Explication du fonctionnement

## 🔹 Thread

Le `Thread` est utilisé pour exécuter du code en arrière-plan.

```java
new Thread(() -> {
    // traitement long
}).start();
```

---

## 🔹 Handler

Le `Handler` permet de revenir vers le thread principal pour modifier l’interface.

```java
mainHandler.post(() -> {
    txtStatus.setText("Image chargée");
});
```

---

## 🔹 AsyncTask

`AsyncTask` simplifie l’exécution des tâches longues.

### Méthodes importantes

| Méthode | Rôle |
|---|---|
| onPreExecute() | Avant le traitement |
| doInBackground() | Travail en arrière-plan |
| onProgressUpdate() | Mise à jour progression |
| onPostExecute() | Après le traitement |

---

# ▶️ Exécution du projet

## 1️⃣ Ouvrir le projet

Dans Android Studio :

```text
File → Open → lab8
```

---

## 2️⃣ Synchroniser Gradle

Android Studio télécharge automatiquement les dépendances.

---

## 3️⃣ Lancer l’application

- connecter un téléphone Android
- ou utiliser un émulateur

Puis cliquer sur :

```text
Run ▶
```

---

# 📸 Résultat attendu

- l’image se charge sans bloquer l’application
- la ProgressBar affiche la progression
- l’interface reste fluide
- le Toast apparaît instantanément

---

# ⚠️ Remarque importante

`AsyncTask` est aujourd’hui obsolète dans les versions récentes d’Android.

Pour les nouveaux projets, Google recommande :

- `Executors`
- `Coroutines`
- `WorkManager`

Mais `AsyncTask` reste utile pour l’apprentissage du multithreading.

---



# 👨‍💻 Auteur

AIT HMAD OUSSAMA 
---
