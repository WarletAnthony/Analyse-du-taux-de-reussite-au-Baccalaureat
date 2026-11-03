# 📊 Analyse Statistique de la Réussite au Baccalauréat en France

## 📌 Présentation du Projet
Ce projet propose une analyse exploratoire des données (EDA) et une étude statistique des taux de réussite au baccalauréat français par département. L'objectif est d'identifier les disparités de réussite à l'échelle nationale et de comprendre l'impact des facteurs géographiques et des voies de formation sur les résultats.

## 🛠️ Stack Technique
* **Langage :** Python 3
* **Librairies :** Pandas (Manipulation), NumPy (Calcul), SciPy (Statistiques), Matplotlib & Seaborn (Visualisation)

## 🔍 Découvertes Majeures & Storytelling

### 1. Segmentation nette par Voie de formation
La voie de formation est le premier facteur discriminant de la réussite. La voie générale présente un effet de plafond avec une concentration extrême des établissements au-dessus de 95% de réussite. À l'inverse, la voie professionnelle affiche une dispersion beaucoup plus grande et des performances globales inférieures.

Voici la distribution des taux de réussite observée :
![Distribution des voies](distribution_voies.png)

### 2. Analyse des Outliers : L'impact insulaire et l'effet banlieue
En appliquant la méthode de l'Écart Interquartile (IQR), l'algorithme a identifié une multitude d'établissements hors-normes (outliers inférieurs), visibles sous forme de points isolés sous les trois boîtes. 

L'analyse croisée de ces points avec nos agrégations départementales révèle deux réalités distinctes :

* **L'isolement insulaire (Les outliers extrêmes) :** Les points situés au niveau le plus bas du graphique (sous la barre des 66% pour la voie professionnelle) matérialisent un décrochage unique. Après vérification dans le dataset, ce signal statistique strict correspond exclusivement à des lycées professionnels des territoires ultramarins (Mayotte et la Guyane se classant d'ailleurs en queue de peloton national).
* **Le facteur grande couronne (Les outliers intermédiaires) :** La longue traînée de points sous les filières générale et technologique (s'étalant de 70% à 85%) montre un phénomène de masse. En recoupant ces points avec notre classement par département, on constate qu'il s'agit principalement des lycées de la banlieue parisienne (93, 95, 91, 77), qui trustent le bas du classement de la France métropolitaine.


Ces observations sont matérialisées par les points isolés tout en bas du Boxplot ci-dessous :
![Boxplot des voies](boxplot_voies.png)

## 🧼 Méthodologie et Rigueur Statistique
* Nettoyage du dataset (vérification des types, suppression des doublons géographiques).
* Analyse de la distribution et application du **test de Shapiro-Wilk** pour évaluer la normalité des variables quantitatives.
* Agrégation des données (`groupby`) pour synthétiser un fichier de plusieurs milliers de lignes en 101 entités départementales propres.
