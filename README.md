League of Legends Champion Preference Analysis

Executive Summary

This project explores the relationship between player preferences and champion attributes in the popular game League of Legends. By analyzing key metrics such as win rate, damage dealt, and popularity, the study aims to uncover trends that influence player decisions. Challenges such as integrating and cleaning multiple datasets were overcome to produce actionable insights. The analysis highlights champions preferred due to balanced attributes and others avoided due to high complexity, offering recommendations for developers and players alike.

Introduction

League of Legends is a globally renowned multiplayer online battle arena game with a rich roster of champions. As an avid gamer and fan of the League of Legends World Championship, this project combines personal interest with data science techniques to analyze champion preferences. By exploring quantitative metrics, the project seeks to identify patterns in champion selection, aiming to answer: What attributes make champions preferred or avoided?

Data Source and Preparation

The analysis relies on two datasets:

export_lol_champs.csv: Contains champion stats (e.g., health, damage, movement speed).

lol_champions.csv: Provides additional attributes like win rate, popularity, and ban rate.

Key Steps:

Data Cleaning: Redundant columns were removed, and missing values were addressed.

Data Merging: Datasets were merged on the Champions column to create a unified dataset.

Analysis Documentation

Exploratory Data Analysis:

Visualized the distribution of player preferences using count plots.

Analyzed correlations between metrics such as Winrate, Popularity, and DamageDealt using heatmaps.

Classification:

Champions were categorized into Preferred, Neutral, and Avoided based on composite scores.

Insights into player behavior and meta trends were derived from this classification.

Visualizations and Dashboards

Distribution of Preferences: Count plot showcasing the split between Preferred, Neutral, and Avoided champions.

Correlation Heatmap: Highlights relationships between key metrics like Winrate and KDA.

Top Champions: Subplots for the top 5 Preferred and Avoided champions, detailing metrics like Popularity and DamageDealt.

Discussion and Recommendations

Key Findings:

Preferred Champions: Typically exhibit balanced attributes, high win rates, and consistent performance.

Avoided Champions: Often have high complexity or situational utility.

Recommendations:

For Developers: Simplify underused champions or balance attributes to increase engagement.

For Players: Focus on mastering champions with balanced metrics for a competitive edge.

Conclusion

This study provides a deeper understanding of player preferences in League of Legends, highlighting the factors that contribute to champion popularity or avoidance. The findings are valuable for both developers aiming to enhance gameplay experience and players seeking to optimize their strategies.

Acknowledgements

This project utilized datasets sourced from Kaggle, with analysis conducted using tools such as Pandas, Seaborn, and Matplotlib.

Future Work

Extend the analysis to games like Cyberpunk 2077 and Assassin's Creed Valhalla.

Investigate how player preferences evolve with new game mechanics or updates.

Social Links

GitHub Repository

Colab Notebook

Outputs

Download the Full Report (PDF)

View the README File (Markdown)

