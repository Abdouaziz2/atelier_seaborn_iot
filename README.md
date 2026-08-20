# Atelier Seaborn — Analyse exploratoire de capteurs IoT

Analyse exploratoire de données (EDA) réalisée avec **Seaborn**, **Pandas** et **Matplotlib**, sur des relevés de capteurs IoT (température, humidité, pression, consommation énergétique) installés dans plusieurs bâtiments.

Projet réalisé dans le cadre du programme **P1 Intelligence Artificielle — Orange Digital Center**.

## Structure du projet

```
atelier_seaborn_iot/
├── data/
│   └── mesures_capteurs.csv        # Données brutes fournies
├── notebooks/
│   └── atelier_seaborn_iot.ipynb   # Notebook d'analyse
├── exports/
│   ├── temperature.png / .pdf
│   ├── correlation_heatmap.png / .pdf
│   └── pairplot.png
└── README.md
```

## Contenu du notebook

| Étape | Objectif |
|---|---|
| Import & vérification | Chargement du CSV, contrôle des types, des valeurs manquantes et des statistiques descriptives |
| Distributions | `histplot`, `kdeplot`, `boxplot`, `violinplot` sur la température, globalement et par bâtiment |
| Comptages | `countplot` sur l'état des capteurs et leur répartition par bâtiment |
| Relations | `scatterplot`, `regplot`, `lmplot` entre température et consommation |
| Corrélations | Matrice de corrélation (Pandas) et `heatmap` (Seaborn) |
| Analyse multivariée | `pairplot` sur température, humidité, pression et consommation |
| Export | Sauvegarde des graphiques clés dans `exports/` (PNG + PDF) |
| Bonus | Détection automatique des valeurs aberrantes (méthode IQR) |

## Principaux résultats

- **Bâtiment B004** : dispersion de température nettement plus élevée que les autres (écart-type ≈ 5,4 °C contre ≈ 3,0 °C), avec des valeurs physiquement aberrantes (-18,5 °C / 58,7 °C) et le plus grand nombre d'alertes capteur.
- **Corrélations** : seule la paire `temperature` / `consommation` présente une relation notable (r ≈ 0,32), positive mais modérée. Les autres variables ne sont quasiment pas corrélées entre elles.

## Prérequis

- Python ≥ 3.10
- `pandas`, `numpy`, `matplotlib`, `seaborn`, `jupyter`

## Installation et exécution

```bash
git clone <url-du-depot>
cd atelier_seaborn_iot

python -m venv .venv
.venv\Scripts\activate        # Windows
# source .venv/bin/activate   # macOS / Linux

pip install pandas numpy matplotlib seaborn jupyter

cd notebooks
jupyter notebook atelier_seaborn_iot.ipynb
```

Exécuter le notebook dans l'ordre (**Kernel → Restart & Run All**) pour régénérer l'ensemble des graphiques et des exports.

## Baye Abdoul Aziz seck
