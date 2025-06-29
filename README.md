# 🎮 Video Game Sales & User Ratings Analysis

This project presents a comprehensive data visualization and statistical analysis of the global video game industry. Using the `vgsales.csv` dataset, the goal was to support a retail company in optimizing its sales strategy for the upcoming summer season by uncovering market trends, user preferences, and performance differences across platforms.

The analysis is structured in two parts:

- **Part 1** answers targeted business questions using visualizations.
- **Part 2** investigates a statistically significant pattern using ANOVA and data storytelling techniques.

---

## 📁 Dataset Overview

- File: `vgsales.csv`
- Contains game titles, platforms, genres, developers, publishers, user scores, and regional/global sales figures.

---

## 📌 Part 1 – Exploratory Analysis with Visualizations

### 🏆 What are the top 5 publishers by global sales?

- Missing publishers replaced with `'Unknown'` for consistency.
- Data grouped and aggregated to compute total sales.
- **Horizontal bar chart** used for clear ranking.
- **Blue gradient color palette** reflects publisher ranks.
- Bold titles and labels ensure clarity for stakeholders.

### 🌍 Is there a correlation between NA and EU sales (2010–2014)?

- Filtered dataset by valid `Year_of_Release` values from 2010 to 2014.
- Calculated yearly correlation between `NA_Sales` and `EU_Sales`.
- **Bubble scatter plot** used:
  - X = NA sales
  - Y = EU sales
  - Size = Global sales
  - Color = Year
- Included a **correlation summary box** and **viridis palette** for accessibility.

### 🎮 What is the distribution of user scores for the top 3 genres?

- Filtered valid `User_Score` entries and computed genre averages.
- Selected top 3 genres by mean user score.
- **Stacked histogram** visualizes user rating distributions.
- Used **Viridis** palette for color blindness accessibility.
- Design includes bold titles, rotated axis labels, and compact legends.

### 🕹️ Do older games (≤2005) have higher median EU sales?

- Split dataset into two groups: ≤2005 vs >2005.
- Median `EU_Sales` computed for each group.
- **Vertical bar chart** used with color-coded bars:
  - Blue = older games
  - Orange = newer games
- Labels placed inside bars, grid lines aid comparison.

### 👨‍💻 Who are the 3 most common developers?

- Cleaned data by dropping rows with missing `Developer`.
- Counted games developed per company.
- **Horizontal bar chart** for top 10 (highlighting top 3).
- **Green gradient** reflects developer frequency.
- Axis and font styles chosen for clarity and accessibility.

---

## 📊 Part 2 – Statistical Analysis: Does Platform Influence User Ratings?

### 📌 Research Question

> Does the platform influence user scores?

### 🧼 Data Preparation

- Removed rows with missing `User_Score` or `Platform`.
- Converted scores to numeric.
- Filtered platforms with at least 100 titles to ensure reliability.

### 📈 Statistical Test

- Applied **ANOVA (one-way)** via `scipy.stats.f_oneway`.
- Result:
  - F-statistic = **37.995**
  - P-value = **0.0000**
- Indicates **significant variation** in user ratings across platforms.

### 📊 Visualization: Boxplot

- Shows score distribution per platform.
- **Coolwarm palette** used to emphasize high/low scores.
- Median score values highlighted:
  - 🟢 Green = highest (e.g. PS – 8.30)
  - 🔴 Red = lowest (e.g. XOne – 6.80)
- Added global median as a dashed reference line.
- Labels, rotated axes, and legend enhance readability.

---

## 🧠 Conclusion

This project delivered a full analysis of video game market trends, from publisher performance and user preferences to platform-based differences in user ratings.

### Part 1:
- Cleaned, transformed, and visualized sales and rating data.
- Answered key business questions using bar charts, histograms, scatter plots, and color theory.
- Provided clear, audience-friendly visuals for strategic insights.

### Part 2:
- Used ANOVA and a boxplot to prove that **platform does influence user ratings**.
- Visual storytelling helped surface deeper patterns and opened the door to further questions, such as:
  - Are some genres better rated on specific platforms?
  - How do ratings vary by release year?
  - Is there rating bias tied to platform loyalty?

Every design and analysis decision was made with clarity, accessibility, and business value in mind.

---

## 🔗 References

- Rudis, B., Ross, N., & Garnier, S. (2024). *The viridis color palettes*. [CRAN](https://cran.r-project.org/web/packages/viridis/vignettes/intro-to-viridis.html)
- Yi, M. (2025). *A Complete Guide to Bubble Charts*. [Atlassian](https://www.atlassian.com/data/charts/bubble-chart-complete-guide)

