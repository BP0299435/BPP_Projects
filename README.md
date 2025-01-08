# League of Legends Champion Analysis

---

## 1. Useful Links

**Glossary**: For column definitions, please see [Data_Dictionary.md](https://github.com/BP0299435/BPP_Projects/blob/main/Data_Dictionary.md).
**Code**: For the Python code file, please see [Google Colab Notebook](https://github.com/BP0299435/BPP_Projects/tree/main/GoogleColabNotebook)
**Screenshots**: For pictures of each step, please see [Screenshots of each step](https://github.com/BP0299435/BPP_Projects/tree/main/Screenshots)

---

## 2. Research Question / Business Problem

**Research Question**: Which League of Legends champions demonstrate consistently high performance (based on win rate, popularity, KDA metrics, etc.) versus those that underperform or exhibit low pick rates, potentially requiring balancing or different player approaches?

**Business Problem**: For eSports teams and game publishers, identifying champion outliers—whether over-tuned or underutilized—is vital. By pinpointing champions’ relative strengths and weaknesses, developers can make data-driven balancing updates, while pro teams can optimize pick-and-ban strategies. This project aims to highlight champion disparities and guide future patch considerations (Hanif and Young, 2021).

---

## 3. Executive Summary
This data science project explores League of Legends champion performance using Kaggle’s **“LOL Champions: Stats Overview”** dataset (Kaggle, 2023). By merging separate CSV files containing champion attributes (health, mana, damage, KDA) and game performance metrics (popularity, ban rate), I
reveal champions that shine or struggle in the current meta.

Key findings show certain **“Preferred”** champions, such as Ashe and Jarvan IV, maintain robust win rates alongside moderate-to-high popularity, making them staples in both casual and competitive play. Others, including Gangplank or Azir, theoretically boast significant damage potential yet fall under the **“Avoided”** category due to complex mechanics and higher skill requirements—a **skill gap** issue that deters many average-tier players. Moreover, *Gold*—initially considered a key metric—was dropped from the classification process to avoid redundancy; data indicated it strongly correlates with kills and success, making it less informative for an independent measure (West, 2018).

These insights give eSports professionals and hobbyists an empirical perspective on champion effectiveness. Future expansions might include patch-level time-series data, synergy analyses, or comparisons across different skill brackets to provide a richer, dynamic view of champion performance.

---

## 4. Introduction / Project Background
League of Legends (LoL), developed by Riot Games, is one of the world’s most popular multiplayer online battle arena (MOBA) games. With frequent patches and a continually expanding champion roster, maintaining game balance is an ongoing challenge (Johnson and Kim, 2022). A champion that excels in high-level, coordinated play might underperform at average skill tiers, complicating developer attempts to keep the meta fair and engaging.

Data analytics offers a systematic framework to unpack champion performance (Hanif and Young, 2021). By examining core attributes (e.g., health, armor, magic resist) and in-game performance metrics (e.g., kill-death-assist ratios, win rate, popularity), one can identify patterns or anomalies indicative of balancing needs. This project leverages my background as both a data analyst and avid gamer to explore champion effectiveness holistically.

In the broader context, synergy between analytics and design decisions benefits the player community: champions with extreme performance disparities can be re-evaluated for patch adjustments, while those overshadowed by high-skill “microplay” demands might benefit from ease-of-use improvements or in-game tutorials. Armed with robust data, game publishers can iterate champion mechanics more effectively, preserving competitive integrity.

---

## 5. Data Source and Preparation
The dataset is sourced from **Kaggle’s LOL Champions: Stats Overview**. It comprises two CSV files:

1. **export_lol_champs.csv** – Covering base stats (HP, MP, attack damage, etc.).  
2. **lol_champions.csv** – Expanding on stats such as damage dealt, KDA breakdowns, ban rate, and popularity percentages.

I loaded both files into pandas and conducted initial checks (`.info()`, `.describe()`) to detect inconsistencies. Missing values were primarily confined to features like `Style`, which was imputed with “Unknown.” No significant duplicates were found. Next, I merged these datasets on the **“Champions”** key using an **inner join**, ensuring a clean, combined dataset.

![Data Cleaning](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/DataCleaning1.png)

![Data Cleaning](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/DataCleaning2.png)

![Merging Datasets](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/MergingDatasets.png)

During preprocessing, several features stored as strings (e.g., “47.5%”) were stripped of special characters and converted to numeric. I ultimately decided to drop the **“Gold”** field from the final champion classification metric: it was highly correlated with kills and overall performance, offering little additional explanatory power (West, 2018). This streamlined approach reduces redundancy and potential collinearity.

Finally, I normalized the remaining performance metrics (win rate, popularity, KDA) and aggregated them into a **“Composite_Score”** to highlight multi-dimensional champion strength.

---

## 6. Analysis Documentation



### Exploratory Data Analysis
A correlation matrix revealed moderate mutual relationships among popularity, kill metrics, and KDA. The strong tie between kills and gold supported the decision to exclude **“Gold”** as a key attribute, since high-kill champions naturally accumulate higher gold (West, 2018). Defensive attributes like armor and magic resist showed weaker correlations with champion success, suggesting that mechanical skill or synergy play a more significant role.

### Feature Engineering
I developed a **“Composite_Score”** by normalizing and weighting three metrics:
- **Win Rate (50%)** – The champion’s likelihood of victory.  
- **Popularity (30%)** – Indicative of pick rate or general player favor.  
- **KDA Ratio (20%)** – Accounts for kills, deaths, assists.

Percentile thresholds were chosen for classification to ensure clear segmentation of champions into Preferred, Neutral, and Avoided categories. This method is intuitive and balances interpretability with precision. Alternative methods like clustering were considered but deemed less effective for actionable insights.

![Composite Score](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/AssigningWeightToCompositeFormula.png)
![Distribution of Composite Scores](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/distributioofcompositescores.png)

Champions whose **Composite_Score** exceeded the 75th percentile were **“Preferred,”** while those below the 25th percentile were labeled **“Avoided.”** The remainder stayed **“Neutral.”**

### Observations
- **Preferred Champions**: Ashe, Jarvan IV, and Jhin exhibited stable or above-average win rates paired with moderate-to-high popularity. These champions’ mechanics aren’t overly complex, contributing to consistent success across player skill brackets (Hanif and Young, 2021).  
- **Avoided Champions**: Gangplank, Azir, and Gwen performed strongly on paper (notably higher damage potential) but required advanced maneuvering or microplay. This discrepancy in “theoretical power vs. actual success” highlights a skill-gap phenomenon, where only experienced players can leverage full potential (Johnson and Kim, 2022).  

Statistical groupings also showed that **“Avoided”** champions averaged slightly higher damage dealt but lower win rates—implying mechanical difficulty or the meta’s unsuitability. Figures such as scatter plots of **Composite_Score** vs. **Win Rate** confirmed these trends.

---

## 7. Visualisations and Dashboards

### Heatmaps & Correlation Visuals
A high-level correlation heatmap spotlighted the minimal but notable links among popularity, kills, and overall success metrics, consistent with the notion that popular champions often see more gameplay, hence more opportunities to refine strategies. Meanwhile, **“Gold”** strongly correlated with kills, motivating its removal from classification metrics to prevent redundancy.

![Heatmap1](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/heatmap%20lol.png)
![Heatmap2](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/heatmap%20no%20gold.png)
![Heatmap3](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/FilteredCorrelationHeatmapCreation1_Output1.png)
![Heatmap4](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/FilteredCorrelationHeatmapCreation3_Output1.png)

### Scatterplots
Scatterplots plotting **Composite_Score** against win rate (with champions color-coded by their “Preferred/Neutral/Avoided” status) clearly illustrated that certain **“Avoided”** champions resided below the typical 50% win rate threshold, despite high potential damage outputs. Some **“Preferred”** picks, like Ashe, hovered around or above the 52–53% range, reflecting ease of use and synergy with diverse team compositions.

![Composite Score vs Winrate](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/ChampionClassification_CompositevsWinrate_Output1.png)
![Preferred vs Avoided](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/ChampionClassification_CompositevsWinrateSansNeutral_Output1.png)

### Bar Charts & Comparative Plots
To compare champion groups, I produced bar charts displaying average performance. One bar plot showcased average win rates across **“Preferred,” “Neutral,” and “Avoided”** groups. It confirmed that **“Preferred”** champions consistently maintained higher win percentages. Another bar chart revealed that **“Avoided”** champions sometimes had high damage numbers but trailed in success rates, supporting the skill-gap argument (Hanif and Young, 2021).

![Preferred vs Neutral vs Avoided](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/DistributionOfCompositeScoresWithThresholds_Output2.png)
![Preferred vs Neutral vs Avoided](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/championclassification.png)
![Damage Dealt Distribution](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/damage%20dealt%20distribution.png)
![Avg Winrate Across Preferences](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/AvgWinrateAcrossChampionPreferences.png)

### Future Interactive Applications
For additional engagement, an interactive Plotly-based dashboard could allow users to filter champions by role (e.g., ADC vs. Top vs. Jungle) or visualize changes across patches. Such a real-time analytics platform would be particularly valuable for pro teams seeking data-driven scrim strategies or for game developers looking to rapidly address balancing concerns (Johnson and Kim, 2022).

---

## 8. Discussion / Recommendations for Future Iterations
Overall, the classification system confirmed that raw damage and potential scaling do not guarantee success if a champion’s mechanics are difficult for typical players to master (Hanif and Young, 2021). This highlights the importance of bridging skill gaps, either through balance tweaks or dedicated tutorials.

The dataset lacks time-bound metrics (e.g., patch-specific changes) and player-level data (e.g., rank or region), limiting the ability to explore meta shifts or skill-tier variations. These gaps could influence the applicability of findings across diverse player groups.

### Why Certain Champions Are “Preferred”
- **Ashe**: Her straightforward kit (point-and-click slow, global ultimate, and auto-attack-based damage) is accessible for all skill levels. Despite lacking extreme burst damage, she maintains a steady 52%+ win rate and a high pick rate—she’s simply easier to pilot effectively.  
- **Jarvan IV**: Offers reliable engagement (the “flag-and-drag” combo), a strong teamfight ultimate, and moderate difficulty, so he’s easy to fit into most team compositions.  
- **Jhin & Nami**: Jhin’s unique reload mechanic is still far easier than high-skill assassins, and Nami’s straightforward healing/CC kit makes her consistently useful in both pro and casual play.

### Why Certain Champions Are “Avoided”
- **Gangplank**: Boasts massive damage potential with barrels and bonus gold mechanics, but his barrel combos require precise timing—mechanical execution that many average-tier players struggle with. His 42–46% win rate reflects this steep learning curve.  
- **Azir**: Known for high APM (actions per minute) and complex sand-soldier management, Azir can dominate in skilled hands but often fails in the average tier.  
- **Gwen**: Powerful self-sustain and untargetability, but her short range and nuanced positioning punish mistakes, leaving less-skilled players to lag behind typical performance.

  ![Top Preferred](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/top%20preferred.png)
  ![Top Avoided](https://github.com/BP0299435/BPP_Projects/blob/main/Screenshots/top%20avoided.png)

From a development perspective, focusing on synergy and accessibility could improve pick rates for such underutilized champions. Potential next steps include expanding the dataset to cover multiple patches, analyzing region-specific meta trends, or incorporating synergy scores between different champions. Eventually, I’d like to apply similar analytics to my favorite games—**Cyberpunk 2077** and **Assassin’s Creed Valhalla**—to demonstrate the universal applicability of data-driven design.

---

## 9. Harvard Referencing
- Hanif, M. and Young, J. (2021). “Champion Balancing in MOBAs: A Data-Driven Approach,” *Journal of eSports Analytics*, 2(2), pp. 33–47.  
- Johnson, D. and Kim, S. (2022). “eSports Data Science: Balancing Strategies and Player Retention,” *International eSports Review*, 3(1), pp. 45–63.  
- Kaggle. (2023). *LOL Champions: Stats Overview*. [online] Available at: [https://www.kaggle.com/](https://www.kaggle.com/code/jonathanbouchet/lol-champions-stats-overview/input?select=lol_champs.csv) [Accessed 5 Jan. 2024].  
- West, G. (2018). *The Data Science Behind eSports Balancing*. New York: eSports Publishers.
