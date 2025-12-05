# Analyse en Composantes Principales (ACP) - Profils d'athlètes de décathlon

## Description du projet

Ce projet réalise une Analyse en Composantes Principales (ACP) sur les performances d'athlètes de décathlon pour identifier des groupes d'individus aux profils similaires.

## l'objectif

Identifier et visualiser les similitudes entre les profils de performance des athlètes de décathlon en réduisant la dimensionnalité des données tout en conservant l'information essentielle.

## Structure du projet

```
sport-profiles-acp/
├── decathlon.csv          # Données des performances des athlètes
├── analyse_acp.ipynb      # Notebook principal d'analyse
├── requirements.txt       # Dépendances Python
└── README.md             # Ce fichier
```

## Installation

### Prérequis

- Python 3.8+
- pip

### Installation des dépendances

```bash
pip install -r requirements.txt
```

## Analyses réalisées

### 1. Exploration des données
- Chargement du dataset avec 41 athlètes et 13 variables
- Exclusion des colonnes non pertinentes : `Competition`, `Points`, `Classement`
- Vérification de l'intégrité des données

### 2. Standardisation
- Standardisation des performances (moyenne = 0, écart-type = 1)
- Nécessaire car les épreuves ont des unités différentes (secondes, mètres, etc.)

### 3. Application de l'ACP
- Réduction de dimensionnalité de 10 variables à 2-3 composantes principales
- Conservation de ~60-70% de la variance totale avec les 2 premières composantes

## Visualisations clés

### Scree Plot - Variance expliquée

Le **scree plot** montre la part de variance expliquée par chaque composante principale. Il permet de déterminer combien de composantes conserver pour l'analyse.

- **PC1** : Capture la plus grande partie de la variabilité (~40-50%)
- **PC2** : Capture la deuxième plus grande variabilité (~15-20%)
- **Critère** : On conserve généralement les composantes jusqu'à atteindre 70-80% de variance cumulée

**Interprétation** : Les deux premières composantes suffisent pour représenter la majorité de l'information.

---

### Projection 2D des athlètes

Cette visualisation projette tous les athlètes dans l'espace des deux premières composantes principales (PC1 et PC2).

**Comment lire ce graphique :**
- Chaque point représente un athlète
- Les athlètes proches ont des profils de performance similaires
- Les athlètes éloignés ont des profils différents
- Les axes indiquent le pourcentage de variance expliquée

**Insights attendus :**
- Identification de clusters naturels d'athlètes
- Détection d'outliers (profils uniques)
- Comparaison visuelle des performances globales

---

### Cercle des corrélations

Le **cercle des corrélations** montre comment chaque épreuve du décathlon contribue aux composantes principales.

**Comment lire ce graphique :**
- Chaque flèche représente une épreuve du décathlon
- La direction indique la corrélation avec PC1 et PC2
- La longueur indique la qualité de représentation
- Les flèches proches sont corrélées positivement
- Les flèches opposées sont corrélées négativement

**Interprétations possibles :**
- **PC1** pourrait représenter la performance globale/athlétisme général
- **PC2** pourrait distinguer les spécialités (force vs vitesse, technique vs explosivité)
- Les épreuves de course regroupées ensemble
- Les épreuves de lancer regroupées ensemble


## Variables analysées

Les 10 épreuves du décathlon :
- `100m` : Sprint court
- `Longueur` : Saut en longueur
- `Poids` : Lancer du poids
- `Hauteur` : Saut en hauteur
- `400m` : Sprint long
- `110m H` : 110m haies
- `Disque` : Lancer du disque
- `Perche` : Saut à la perche
- `Javelot` : Lancer du javelot
- `1500m` : Course de demi-fond

## Technologies utilisées

- **Python 3.14**
- **pandas** : manipulation de données
- **numpy** : calculs numériques
- **scikit-learn** : algorithme PCA et standardisation
- **matplotlib** : visualisations
- **seaborn** : graphiques statistiques

## Auteur

Projet réalisé dans le cadre d'une étude sur les profils d'athlètes de décathlon par End_Writer



# (à venir)

- Clustering (K-means) pour identifier automatiquement les groupes
- Analyse des profils types par cluster
- Prédiction de performances
