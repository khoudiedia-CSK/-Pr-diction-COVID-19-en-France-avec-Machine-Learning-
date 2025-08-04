# 📊 Prédiction COVID-19 dans le monde précisément en France avec Machine Learning

🧠 Contexte


Depuis le début de la pandémie de COVID-19, les données sanitaires se sont multipliées, rendant possible leur exploitation à des fins d’analyse et de prévision. Ce projet vise à explorer ces données pour mieux comprendre l’évolution du virus à l’échelle mondiale, puis à développer des modèles prédictifs appliqués à la situation en France.

En combinant analyse exploratoire et modélisation machine learning, le projet permet d’identifier les pays les plus touchés, de visualiser les courbes d’évolution des cas, et de prédire les tendances futures en France à l’aide de deux approches :

une régression linéaire simple pour modéliser la croissance des cas confirmés,

un modèle Random Forest multi-sortie pour prédire simultanément les cas confirmés, les décès et les guérisons.

Ce projet démontre comment des outils de data science peuvent aider à anticiper l’évolution d’une crise sanitaire mondiale et fournir un appui décisionnel pour la gestion de la pandémie.


## 🎯 Objectif

Analyser l'évolution de la pandémie COVID-19 dans différents pays, puis prédire les cas en France à l’aide de deux modèles :
- Régression Linéaire simple
- randomForest Multi-sortie

---

## 🧾 Données utilisées

Fichier : `covid_19_clean_complete.csv`  
Colonnes principales : Date, Pays, Cas Confirmés, Décès, Rétablis

---

## 🔍 Partie 1 – Analyse exploratoire

### 🌍 Top 10 pays les plus touchés (en cumulé)

Un graphique a été généré pour afficher les **10 pays avec le plus grand nombre de cas confirmés**.

📈 Exemple de visualisation :

But : Visualiser les 10 pays avec le plus de cas confirmés à la dernière date disponible.

Graphique : Barre verticale (bar chart)

<img width="1123" height="547" alt="image" src="https://github.com/user-attachments/assets/1073ddff-feea-40cf-b874-9be1fd522fb1" />


---

### 📐 Modélisation : Régression Linéaire (France)

- Objectif : prédire les cas confirmés en fonction du temps (jours depuis le début)
- Modèle : `LinearRegression` (scikit-learn)
- Limite : modèle très simple, assume une progression linéaire

📈 Visualisation :

But : Modéliser l’évolution des cas confirmés en France dans le temps avec une régression linéaire.

Graphique : Courbe des cas réels vs prédits (droite de tendance)

<img width="914" height="544" alt="image" src="https://github.com/user-attachments/assets/a89fa79a-4202-41ee-abc6-35a2a0ec8970" />

---
<img width="923" height="543" alt="image" src="https://github.com/user-attachments/assets/27f5f7ef-6347-4f8e-9094-6720d41ee95e" />

Un petit apercu sur le Modèle Machine Learning ARIMA

<img width="1108" height="543" alt="image" src="https://github.com/user-attachments/assets/1032ffa7-9803-4361-999c-c2b7a3f91370" />



## 🤖 Partie 2 – Modèle Machine Learning Random Forest

### 🇫🇷 Données filtrées pour la France

- Agrégation par jour
- Création d’une variable `Day` = nombre de jours depuis le début

### ⚙️ Modèle : Random Forest Regressor (multi-sortie)

- Entrée : `Day`  
- Sorties : `Confirmed`, `Deaths`, `Recovered`

### 🔍 Résultats

| Variable    | MSE         | R² Score |
|-------------|-------------|----------|
| Confirmed   | 12530.45    | 0.95     |
| Deaths      | 430.76      | 0.92     |
| Recovered   | 2350.88     | 0.88     |

📊 Graphiques des résultats :

But : Utiliser RandomForest pour prédire simultanément :

Cas confirmés

Décès

Rétablis

Graphiques : 3 sous-graphiques (confirmés, décès, rétablis)

Données affichées : Données réelles + prédictions sur 7 jours  

<img width="1103" height="230" alt="image" src="https://github.com/user-attachments/assets/fd5b2f1c-8360-48d6-81e3-2701e6b2d6bb" />


<img width="1097" height="236" alt="image" src="https://github.com/user-attachments/assets/eac5cdb7-d495-4e67-9555-1608c50347c3" />


<img width="1084" height="249" alt="image" src="https://github.com/user-attachments/assets/65ad1fb2-5c72-4fc2-8de7-da37fa8281e3" />


---

## 🔮 Prédictions pour les jours futurs

Le modèle est utilisé pour prédire les 7 prochains jours en France :

But : Afficher dans la console les prédictions numériques pour :

Jour +1 à Jour +7

Avec le détail : Confirmés, Décès, Rétablis
<img width="1093" height="408" alt="image" src="https://github.com/user-attachments/assets/4df968f4-b62b-4165-96f8-8e8043f6f218" />
<img width="1092" height="203" alt="image" src="https://github.com/user-attachments/assets/baa96b0d-c4e1-4c89-a862-36573c1def0f" />


