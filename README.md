# League of Legends Champion Preference Analysis

## Executive Summary

This project explores the relationship between player preferences and champion attributes in the popular game League of Legends. By analyzing key metrics such as win rate, damage dealt, and popularity, the study aims to uncover trends that influence player decisions. Challenges such as integrating and cleaning multiple datasets were overcome to produce actionable insights. The analysis highlights champions preferred due to balanced attributes and others avoided due to high complexity, offering recommendations for developers and players alike.

## Introduction

League of Legends is a globally renowned multiplayer online battle arena game with a rich roster of champions. As an avid gamer and fan of the League of Legends World Championship, this project combines personal interest with data science techniques to analyze champion preferences. By exploring quantitative metrics, the project seeks to identify patterns in champion selection, aiming to answer: What attributes make champions preferred or avoided?

## Data Source and Preparation

The analysis relies on two datasets:
1. `export_lol_champs.csv`: Contains champion stats (e.g., health, damage, movement speed).
2. `lol_champions.csv`: Provides additional attributes like win rate, popularity, and ban rate.

### Key Steps:
- **Cleaning**: Removed duplicates and irrelevant columns.
- **Merging**: Integrated datasets using the champion name as a key.
- **Feature Engineering**: Created a composite score to quantify champion preference, combining win rate and popularity.

## Analysis Documentation

### Exploratory Data Analysis
Initial exploration revealed:
- A wide range of win rates (42.6% to 53.2%) and damage dealt metrics.
- Popularity varied significantly, highlighting disparities in player preferences.

### Correlation Analysis
A heatmap visualized relationships between metrics, identifying significant positive correlations between damage dealt and composite score.

### Classification
Champions were classified into `Preferred`, `Neutral`, and `Avoided` based on composite scores:
- **Preferred**: Champions with balanced attributes and higher win rates.
- **Avoided**: High skill-cap champions, despite dealing significant damage.
- **Neutral**: Average-performing champions.

## Visualizations and Dashboards
- **Scatter Plots**: Showcased the relationship between composite score and win rate.
- **Bar Charts**: Highlighted top `Preferred` and `Avoided` champions with associated metrics.
- **Distribution Graphs**: Displayed the spread of composite scores and damage dealt.

Snapshots of visualizations are stored in the `/snapshots` folder for easy reference.

## Discussion and Recommendations
### Findings
1. Preferred champions had win rates above 50%, while avoided champions, though dealing more damage, had lower popularity.
2. High skill-cap champions require advanced mechanics, deterring average players.

### Recommendations
1. Developers should consider tutorials or balancing updates for high skill-cap champions.
2. Future iterations could analyze new champions post-major updates to observe evolving trends.

## Acknowledgements
Data was sourced from online repositories such as Kaggle, and the analysis leveraged Python libraries (pandas, matplotlib, seaborn) and Google Colab.

## Future Work
In future projects, data from games like Cyberpunk 2077 or Assassin's Creed Valhalla could be analyzed to broaden insights into player behavior across genres.

## Screenshots
Snapshots of the analysis and outputs can be found in the `/snapshots` folder:
- `distribution_chart.png`
- `scatterplot.png`
- `top_preferred.png`
- `top_avoided.png`

## Project Structure
```
|-- code/
|   |-- data_cleaning.py
|   |-- analysis.py
|-- snapshots/
|   |-- distribution_chart.png
|   |-- scatterplot.png
|   |-- top_preferred.png
|   |-- top_avoided.png
|-- README.md
|-- data/
|   |-- export_lol_champs.csv
|   |-- lol_champions.csv
```

## Links
- [Google Colab Notebook](https://colab.research.google.com/)
- [GitHub Repository](https://github.com/IwannaChatz/BPP_Projects)
