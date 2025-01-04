League of Legends Champion Data Analysis

This README documents the steps taken and insights derived from the analysis of League of Legends champion data. As an avid gamer and long-time follower of League of Legends—a game I have passionately played and followed, including its world championships—this project was inspired by my interest in understanding player preferences for champions. The analysis aims to investigate which champions are most and least favoured by players and why this might be.

This project uses publicly available data on champion statistics and player preferences, offering insights into what makes a champion appealing or avoided. While new champions frequently emerge following major events, some iconic champions consistently capture players' attention.

In the future, I would like to extend this analysis to include data from my favourite games, Cyberpunk 2077 and Assassin's Creed Valhalla, to explore how player preferences evolve across genres and mechanics.

1. Data Cleaning

Description:

Data cleaning is an essential step to ensure the dataset is ready for analysis. Redundant columns were removed, numerical conversions were handled, and missing values were addressed. This step laid the foundation for reliable and meaningful insights.

Key Steps:

Dropped redundant columns like Unnamed: 0 to declutter the dataset.

Converted non-numeric columns (e.g., AS+) to numeric, handling errors gracefully with coercion.

Filled missing values in the Style column with "Unknown," ensuring categorical completeness.

Cleaned columns like Winrate, Gold, and DamageDealt to ensure consistent numeric formats.

Why it Matters:

As a gamer, I understand how critical it is for stats to be accurate and clean, ensuring analysis reflects true gameplay metrics and trends.

Outputs:







2. Data Loading and Initial Exploration

Description:

Explored datasets to understand their structure and contents, identifying key columns for analysis. This step provided the first look at the data and informed subsequent steps.

Key Steps:

Loaded two datasets: lol_champs.csv and export_lol_champs.csv.

Previewed the first five rows of each dataset to understand their structure.

Assessed column data types and identified missing values to plan cleaning efforts.

Why it Matters:

Exploring data mirrors the early stages of strategizing in a game—knowing your resources is key to crafting a winning plan.

Outputs:



3. Merging Datasets

Description:

The datasets were merged on the Champions column to create a comprehensive dataset for analysis.

Key Steps:

Used an inner join on the Champions column to combine relevant data.

Removed duplicate columns like HP_y, HP5_y, etc., to avoid redundancy.

Why it Matters:

Just like assembling a winning team in League of Legends, merging datasets creates a cohesive whole, combining strengths for better insights.

Outputs:



4. Classification of Preferences

Description:

Champions were categorized into "Preferred," "Neutral," and "Avoided" based on thresholds applied to their composite scores. This classification helps highlight patterns in player preferences.

Key Steps:

Calculated thresholds for "Preferred" and "Avoided" categories based on composite score distribution.

Assigned champions to categories accordingly.

Why it Matters:

Categorizing champions mirrors the decision-making process in gameplay, helping identify meta champions and understanding playstyle trends.

Outputs:



5. Data Visualization

Description:

Visualized key metrics to uncover patterns and relationships within the data.

Key Steps:

Created a histogram of composite scores, marking preferred and avoided thresholds.

Generated a count plot to illustrate the distribution of preference categories.

Constructed a heatmap to analyze correlations between metrics like Winrate and DamageDealt.

Why it Matters:

As a visual learner and gamer, I know the value of visualizing trends to strategize effectively, whether in-game or through data.

Outputs:







6. Normalization of Metrics

Description:

Normalized metrics such as Winrate, Popularity, and KDA for better comparability and to reduce the impact of scale differences.

Key Steps:

Applied min-max normalization to scale values between 0 and 1.

Normalized KDA by considering kills, deaths, and assists proportionately.

Why it Matters:

In gaming, fair comparisons are essential—whether comparing champions or player performance, normalization ensures balance.

Outputs:



7. Group Analysis by Preference

Description:

Grouped champions by preference to calculate average metrics and compare categories. This step quantified differences between "Preferred," "Neutral," and "Avoided" groups.

Key Steps:

Computed mean values for metrics like Winrate and DamageDealt across preference groups.

Identified standout characteristics of each group.

Why it Matters:

Understanding group characteristics aids in identifying why certain champions dominate or fall behind in the meta.

Outputs:



8. Insights and Top Champions

Description:

Highlighted the top 5 preferred and avoided champions based on composite scores. Each category was analyzed for standout metrics.

Key Steps:

Extracted the top 5 champions in the "Preferred" category.

Identified the bottom 5 champions in the "Avoided" category.

Compared metrics like Popularity and Winrate to explain rankings.

Why it Matters:

As a player, understanding the top and bottom champions provides insight into the meta and how to counter or leverage them effectively.

Outputs:





9. Subplot Visualizations for Key Metrics

Description:

Created subplot visualizations for metrics like Winrate, DamageDealt, and Popularity for the top preferred and avoided champions.

Key Steps:

Designed comparative bar charts for multiple metrics in a single figure.

Analyzed patterns to understand what makes a champion "Preferred" or "Avoided."

Why it Matters:

As a gamer, seeing stats side-by-side helps me understand what truly defines a champion's appeal or shortcomings.

Outputs:





Summary:

This analysis provided actionable insights into champion performance and preferences. Through data cleaning, visualization, and detailed analysis, the project highlighted key trends and informed strategies for champion selection, gameplay balance, and future design decisions.

Gaming isn’t just a hobby for me—it’s a passion. This project blends my analytical skills with my love for League of Legends to demonstrate how data can uncover hidden patterns and improve both gameplay and design. Feel free to explore the code and outputs for a detailed understanding of each step!

