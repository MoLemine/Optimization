# 📘 Mini-Projet d’Optimisation pour l’Apprentissage Automatique

## 👤 Informations générales

- **Réalisé par** : Mohamed Lemine Abdallahi Tah  
- **Matricule** : C12896  
- **Université** : Université de Nouakchott Al Aasriya  
- **Faculté** : Faculté des Sciences et Techniques (FST)  
- **Département** : Mathématiques et Informatiques  
- **Niveau** : M2 SSD – Statistiques et Sciences des Données  
- **Année universitaire** : 2025–2026  
- **Encadrant** : Dr Elbenany Med Mahmoud  

---

## 🎯 Objectif du projet

Ce mini-projet a pour objectif d’appliquer les **méthodes d’optimisation vues en cours** à des problèmes concrets d’apprentissage automatique, en mettant l’accent sur :

- la formalisation mathématique rigoureuse,
- l’implémentation manuelle des algorithmes,
- l’analyse théorique (convexité, Lipschitzianité, convergence),
- la comparaison expérimentale des méthodes.

Aucun framework de deep learning (PyTorch, TensorFlow, etc.) n’est utilisé afin de mieux comprendre les mécanismes fondamentaux de l’optimisation.

---

## 📚 Concepts et méthodes étudiés

### 🔹 Fonction de perte
- Perte logistique pour la classification binaire
- Régularisation **L2 (Ridge)** et **L1 (Lasso)**

### 🔹 Propriétés théoriques
- Convexité et forte convexité  
- Gradient **L-Lipschitz continu**  
- Stabilité numérique après normalisation  

### 🔹 Méthodes d’optimisation

#### Méthodes déterministes
- Descente de Gradient (GD)
- Gradient Conjugué (CG)

#### Méthodes stochastiques
- Stochastic Gradient Descent (SGD) avec pas décroissant
- RMSProp
- Adam (analyse du momentum)

#### Méthodes proximales (L1)
- ISTA
- FISTA

---

## 📊 Datasets utilisés

- **Breast Cancer Wisconsin** (classification binaire)  
  `sklearn.datasets.load_breast_cancer()`

- **California Housing** (régression)  
  `sklearn.datasets.fetch_california_housing()`

Tous les datasets sont chargés directement depuis `scikit-learn`.

---

## 🛠️ Technologies et outils

- **Langage** : Python 3  
- **Bibliothèques** :
  - NumPy (calcul matriciel, gradients)
  - Matplotlib (visualisation)
  - scikit-learn (datasets, normalisation, métriques)
- **Environnement** : Jupyter Notebook  
- **Rédaction du rapport** : LaTeX (Overleaf)

➡️ Aucune dépendance externe supplémentaire n’est requise.

---

## 🧪 Méthodologie

Le projet suit strictement les phases définies dans l’énoncé officiel :

### Phase 1 – Optimisation déterministe
- Analyse théorique de la perte logistique Ridge
- Implémentation et comparaison de GD et CG

### Phase 2 – Optimisation stochastique
- Passage à l’échelle avec SGD, RMSProp et Adam
- Analyse de la convergence et de la stabilité

### Phase 3 – Méthodes proximales
- Régularisation L1
- Comparaison ISTA vs FISTA
- Étude de la sparsité des coefficients

📌 Les données sont **normalisées avec `StandardScaler`**, garantissant :
- une meilleure stabilité numérique,
- un gradient Lipschitzien avec **L ≈ 3.42**,
- une convergence rapide.

---

## 📈 Résultats principaux

Après normalisation :

- **GD et CG**
  - Convergence très rapide (< 0.1 s)
  - Accuracy ≈ **96.5 %**, AUC ≈ **0.996**

- **Adam et RMSProp**
  - Excellentes performances initiales
  - Adam légèrement supérieur en stabilité

- **SGD**
  - Très compétitif malgré sa simplicité

- **ISTA vs FISTA**
  - FISTA converge nettement plus vite

- **Régularisation L1**
  - Forte sparsité (80–100 % de coefficients nuls pour λ ≥ 0.1)
  - Légère baisse des performances prédictives

👉 La normalisation est indispensable pour éviter les instabilités numériques.

---

## 📁 Structure du dépôt

```text
Optimization/
├── projet/
│   ├── figures/                  # Figures de convergence et comparaisons
│   ├── optimizationML.ipynb      # Notebook principal
│   ├── optimizationML.pdf        # Rapport final
│   └── sujetProjet.pdf           # Énoncé officiel
├── tp/
│   └── tp.ipynb                  # TP complémentaire (régression)
└── README.md                     # Ce fichier
