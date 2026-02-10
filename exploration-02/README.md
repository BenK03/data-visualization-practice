## 📘 Exploration 02 — Global Emissions, Economic Scale & PCA Analysis
This notebook explores a global emissions dataset to practice aggregation, proportional visualization, time-series analysis, and dimensionality reduction. The focus is on applying lecture-based visualization principles, handling missing data correctly, and using PCA to summarize multi-variable environmental and economic patterns.

### 📂 Dataset Overview
The dataset contains country-level environmental and economic indicators across multiple years. Key attributes include:

- Year — numeric  
- Country — categorical  
- Continent — categorical  
- CO2_Emissions — numeric  
- Methane_Emissions — numeric  
- Nitrous_Emissions — numeric  
- GDP — numeric  
- Population — numeric  

The dataset contains missing values in CO2, Methane, and GDP, requiring structured preprocessing before analysis.

### 🧹 Data Cleaning Workflow

1. Handling missing data  
Rows with missing values in CO2_Emissions, Methane_Emissions, and GDP were removed to preserve statistical validity for aggregation and PCA.

2. Year filtering  
For comparative and dimensionality analysis, the dataset was filtered to:
- Year = 2020  

3. Aggregation by continent  
Countries were grouped by continent and averaged across:
- CO2_Emissions  
- Methane_Emissions  
- Nitrous_Emissions  
- GDP  
- Population  

Each continent is represented as a 5-dimensional feature vector for PCA.

### 📊 Visualizations & Purpose

1. Bar Chart — Top 10 Countries by CO2 (2020)  
Horizontal bar chart displaying the highest emitters. Bars start at zero and are sorted descending to preserve proportional ink and clarity.

2. Stacked Bar Chart — Emission Composition (Top 10)  
Displays CO2, Methane, and Nitrous emissions stacked per country to visualize composition.

3. Scatter Plot — GDP vs CO2 (Color = Continent)  
Examines the association between economic output and emissions. Position encodes magnitude; color distinguishes continent.

4. Bubble Chart — GDP vs CO2 (Bubble Size = Population)  
Extends scatter to include population. Bubble area scales proportionally to population.

5. Correlogram — Correlation Matrix (2020)  
Visualizes correlation among CO2, Methane, Nitrous, and GDP. Circle size represents magnitude; color represents direction.

6. Stacked Proportion Chart — Emission Share by Continent (2020)  
Each bar sums to 100%, showing relative contribution of CO2, Methane, and Nitrous within each continent.

7. Pie Chart — Emission Contribution by Continent  
Displays continent-level share of total emissions using proportional area encoding.

8. Time Series — CO2 Emissions (2000–2024)  
Line charts for Canada, South Korea, Japan, China, and Brazil.  
A 5-year moving average was applied to smooth fluctuations and highlight long-term trends.

9. PCA — Dimensionality Reduction (2020)  
After standardization, PCA was applied to continent-level feature vectors.  
PC1 captures the dominant variance direction.  
PC2 captures the second orthogonal variance pattern.  
The 2D projection visualizes structural differences in emission–economic profiles across continents.

### 🔍 Key Insights
- Greenhouse gases are strongly positively correlated.  
- GDP alone does not perfectly predict emissions.  
- China and South Korea show strong upward emission trends.  
- Canada and Japan show more fluctuation and stabilization.  
- Continents differ both in magnitude (PC1) and structural composition (PC2).  

### 🎯 Skills Practiced
- Handling missing values appropriately  
- Filtering and aggregating data  
- Applying proportional ink principles  
- Creating scatter, bubble, stacked, and time-series visualizations  
- Implementing moving averages  
- Computing and interpreting PCA  
- Structuring a clean, reproducible analysis workflow  

### 📁 Contents
- notebook.ipynb — Full analysis pipeline + all visualizations  
- report.pdf — Exported submission  
- data/ — Cleaned dataset used for analysis  