# League of Legends Champion Preference Analysis

## Executive Summary
This project explores the fascinating world of player preferences in League of Legends, focusing on champions that are favored or avoided based on their statistical performance. Leveraging data from Kaggle, the analysis integrates exploratory data analysis (EDA), composite scoring, and impactful visualizations to uncover insights. The project identifies key patterns, including the role of skill cap in champion selection and recommendations for improving the accessibility of complex champions. The project faced challenges such as cleaning datasets with redundant information and adapting visual storytelling for crowded data. Future iterations may expand this work to other iconic games such as Cyberpunk 2077 and Assassin's Creed Valhalla.

## Introduction
As an avid gamer with a deep interest in League of Legends, this project was inspired by my passion for understanding how players choose their champions. League of Legends, a global phenomenon, features a diverse roster of champions, each with unique abilities and complexities. Over the years, new champions emerge following significant events, yet some maintain their enduring popularity. This project aims to investigate the factors influencing champion preference, leveraging publicly available data to explore trends and provide actionable recommendations.

## Data Source and Preparation
### Data Source
The data was sourced from Kaggle, comprising two datasets: `export_lol_champs.csv` and `lol_champions.csv`. These datasets included detailed information on champion statistics, popularity, and performance metrics.

### Data Preparation
Data cleaning involved:
- Removing duplicate columns such as `HP_y` and `HP+_y`.
- Filling missing values in features like `Style` with default labels.
- Creating a composite score to quantify champion performance based on key metrics like damage dealt and win rate.
- Adding a `Preference` classification column to categorize champions into `Preferred`, `Neutral`, or `Avoided`.

## Analysis Documentation
The analysis began with EDA to understand the distribution of key metrics such as win rate, damage dealt, and popularity. Correlation matrices and scatterplots were employed to identify relationships among variables. Key steps included:
- Visualizing the distribution of champions by preference classification.
- Calculating average win rates, damage dealt, and other metrics for each category.
- Identifying top 5 `Preferred` and `Avoided` champions based on composite scores.

Key findings include:
- Preferred champions like `Thresh` and `Jhin` balance high win rates and accessibility.
- Avoided champions, such as `Azir`, often exhibit high damage potential but require significant skill to play effectively.

## Visualizations and Dashboards
Interactive visualizations were created using Matplotlib and Seaborn to present findings effectively. Highlights include:
- Scatterplots illustrating the relationship between win rate and composite score.
- Bar charts comparing average metrics across `Preferred`, `Neutral`, and `Avoided` categories.
- A distribution plot showing the spread of composite scores among champions.

## Discussion and Recommendations
### Key Observations
- Skill cap significantly influences champion preference. Champions requiring intricate mechanics are less favored despite their statistical strengths.
- Neutral champions occupy a stable middle ground, appealing to a wide range of players.

### Recommendations
1. **For Players:** Leverage tutorials to master high skill cap champions, potentially increasing their playability.
2. **For Developers:** Balance avoided champions by simplifying mechanics or improving usability.
3. **Future Research:** Explore longitudinal data to examine the impact of game updates on champion preference.

## Conclusion
This project provides valuable insights into player preferences in League of Legends, highlighting the interplay between champion complexity and performance. By addressing the challenges identified, game developers can foster a more inclusive and engaging gaming experience.

## Acknowledgements
Special thanks to Kaggle for providing the datasets and to the open-source community for tools like Python, Pandas, and Matplotlib, which were indispensable for this analysis.

## Future Work
Building on this foundation, future iterations could expand to other games or delve deeper into the psychological factors influencing player choices. Leveraging real-time API data and integrating machine learning could further enhance the analysis.

---

**Links:**
- [Colab Notebook](https://colab.research.google.com/)
- [GitHub Repository](https://github.com/IwannaChatz/BPP_Projects)
