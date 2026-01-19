## 📘 Exploration 01 — Provincial Health, Income & Lifestyle Patterns
This notebook explores a small Canadian health dataset to practice data cleaning, feature engineering, and visualization design. The focus is on building a clear analysis pipeline: fix data quality issues, engineer interpretable features, and use proper visual encodings to reveal patterns.

### 📂 Dataset Overview
The dataset includes self-reported health and lifestyle information for individuals from several provinces in Canada. Key attributes include:
- Age — numeric
- Gender — categorical (inconsistent labels)
- Income — numeric
- BMI — numeric
- StressLevel — ordinal scale
- PhysicalActivity — discrete numeric
- Province — categorical
- SelfRatedHealth — ordered categories from “Poor” to “Excellent”
The dataset contains real-world issues such as missing values, inconsistent category labels, and mixed data types — ideal for practicing data-cleaning workflows.

### 🧹 Data Cleaning Workflow
This exploration focuses heavily on structured cleaning, including:

1. Standardizing categorical values
Gender and Smoking labels contained inconsistencies (e.g., “male”, “M”).
These were normalized to clean, consistent categories.

2. Handling missing data
Different strategies were applied based on data type and lecture rules:
- BMI → mean imputation
- Income → median imputation (more robust to outliers)
- PhysicalActivity → mean imputation
- StressLevel → dropped rows (ordinal → imputation would distort meaning)

3. Enforcing correct data types
Converted Age, Income, BMI, and StressLevel into their proper numeric types to support calculations.

4. Creating derived features
Two analytical categories were engineered to support later visualizations:
- BMI_Category (Underweight / Normal / Overweight / Obese)
- IncomeBracket (<50k / 50–80k / 80–110k / >110k)
These transformations help turn raw values into interpretable groups.

### 📊 Visualizations & Purpose
This exploration focuses on practicing correct visual encoding — matching the type of data to the type of chart.

1. Bar Chart — Average Life/Health Proxy by Province
Converted SelfRatedHealth into a numeric 1–5 scale to compute a provincial average.
A horizontal bar chart was used to compare aggregated values across categories, following proper encoding rules. Sorted bars reduce cognitive load and clarify differences.

2. Scatter Plot — Income vs BMI
Income and BMI are quantitative, making scatter the correct format.
Additional encodings were layered:
- Color → StressLevel (ordinal → sequential colormap)
- Shape → Gender (categorical)
- Colorbar + legend maintain contiguity and reduce interpretation effort.
This chart explores whether income relates to BMI and whether gender or stress level shifts the pattern.

3. Diverging Bar Chart — Life Proxy Difference by Province
Calculated:
ΔLifeProxy = ProvinceMean – OverallMean

A diverging color palette highlights which provinces score above or below the national average.
Centering the scale at zero clarifies positive vs negative deviation.

### 🔍 Key Insights
Some notable patterns observed from the cleaned dataset:
- Self-rated health varies meaningfully by province, with some consistently scoring above the national average.
- Income and BMI show no strong linear relationship, but spread differs by gender.
- Stress level patterns help reveal subtle clusters in the scatter plot.
These insights aren’t meant to be conclusive — the primary goal is practicing analytical thinking and visual principles.

### 🎯 Skills Practiced
This exploration reinforces:
- Working with missing data (imputation vs dropping)
- Standardizing categorical values
- Enforcing correct data types
- Creating derived analytical features
- Grouping and aggregating with pandas
- Using Matplotlib for bar charts, scatter plots, and diverging visuals
- Applying proper visual encoding rules (color, shape, scale, contiguity)
- Structuring an analysis into a clean, repeatable workflow

### 📁 Contents
- notebook.ipynb — Full cleaning pipeline + all visualizations
- report.pdf — Exported version with analysis and figures
- data/ — Raw and cleaned versions of the dataset