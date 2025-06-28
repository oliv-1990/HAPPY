What Makes Nations Happy: A Global Analysis of Happiness and Development 

This capstone project explores how national happiness relates to key socio-economic development indicators across developed and developing countries from 2005 to 2022. By combining data from the World Happiness Report and the World Bank Development Indicators, the goal is to understand which factors most influence citizens' well-being — and how these patterns vary globally.

Objective
Research Question:Which development indicators are most strongly associated with national happiness across a diverse global sample of countries?
While many governments use GDP as a primary signal of national well-being, this project investigates how other factors — such as education, healthcare, internet access, military spending, and rural population — contribute to happiness. By expanding the scope beyond traditional economic measures, this analysis aims to provide insights that may help inform more holistic and inclusive policy decisions focused on human well-being, especially in both urban and rural contexts.

Key Columns Used for Merging
To combine the datasets from the World Happiness Report and the World Bank Development Indicators, two key columns were used:
- `country`: Identifies the country or geographic region; present in both datasets
- `year`: The calendar year of the data; used to align corresponding records across time

Selected Features
This project combines key variables from the World Happiness Report and the World Bank Development Indicators. These were selected based on relevance to well-being, policy relevance, and data availability from 2005–2022.
From the World Happiness Report:
·	ladder_score: Self-reported life satisfaction on a scale from 0 to 10
·	log_gdp_per_capita: Logarithm of income per person
·	country: Identifies the country or geographic region
·	year: The calendar year of the data
 From the World Bank Development Indicators:
·	military_expenditure_percent_gdp: Military spending as a percentage of GDP
·	internet_access_percent: Percentage of population with internet access
·	education_expenditure_percent_gdp: Government education spending as a percentage of GDP
·	health_expenditure_percent_gdp: Government health spending as a percentage of GDP
·	rural_population_percent: Percentage of population living in rural areas
·	country: Identifies the country or region (also used for merging)
·	year: Calendar year (also used for merging)
 Note: The datasets originally included many additional indicators. This subset was chosen for its explanatory power, interpretability, and completeness across countries and years.


Datasets Used
1.World Happiness Report (2005–2022)
•	Annual happiness scores (Ladder Score) and supporting economic indicators
•	 Source: worldhappiness.report
 2.World Bank Development Indicators
•	Global socio-economic and infrastructure data across countries, including GDP, health, education, and internet access
•	 Source: databank.worldbank.org

Methods & Tools
Data Collection & Cleaning
·	Cleaned and standardized datasets by country and year
·	Handled missing values and inconsistent entries
·	Trimmed to ~48 countries (2 developed + 2 developing per continent) based on data completeness and representation
Feature Engineering
·	Created a new binary feature: development_status (Developed vs. Developing)
1	Initial classification based on GDP per capita
2	Cross-referenced with World Bank/IMF classification
·	Selected Indicators:
·	ladder_score: Self-reported life satisfaction on a scale from 0 to 10
·	log_gdp_per_capita: Logarithm of income per person
·	country: Identifies the country or geographic region
·	year: The calendar year of the data
·	military_expenditure_percent_gdp
·	internet_access_percent
·	education_expenditure_percent_gdp
·	health_expenditure_percent_gdp
·	rural_population_percent
·	Prepared for potential subregional analysis (e.g., Eastern vs. Western Europe)
SQL Integration
·	Stored merged and cleaned data in SQLite
·	Performed SQL joins on country and year
·	Queried finalized tables using SQL for modeling and EDA
Exploratory Data Analysis (EDA)
·	Descriptive stats, trend analysis, and correlations
·	Visualizations:
1	Bar plots (country-level comparisons)
2	Line charts (trends over time)
3	Scatterplots (pairwise correlations)
·	Grouped countries by development_status and region
 Modeling & Evaluation
·	Simple Linear Regression: to understand direct relationships
·	Random Forest Regression: to capture non-linear effects and assess feature importance
·	Performance Evaluation:
1	Mean Squared Error (MSE)
2	R² score
3	Train/test split for model validation
 Visualization
·	Correlation heatmaps
·	Feature importance bar plots
·	Actual vs. predicted scatter plots
·	Comparative visuals by region and development status

Evaluation Plan
To assess the quality and success of my analysis, I follow a multi-step evaluation strategy:
·	I evaluate predictive performance using Mean Squared Error (MSE) and R² score to understand how well the models explain variation in happiness scores.
·	I use feature importance rankings from the Random Forest model to identify which development indicators most strongly influence national happiness.
·	I prioritize interpretability and clarity, ensuring the results are accessible to both technical and non-technical audiences.
·	I continuously seek feedback from peers and mentors to validate insights and refine my approach.
Tech Stack
·	Python (pandas, matplotlib, seaborn, scikit-learn, sqlite3)
·	SQLite for database storage and queries
·	Jupyter Notebooks for EDA, modeling, and reporting
·	VS Code as IDE
·	Git + GitHub for version control and collaboration
·	venv for a reproducible virtual environment
Project includes:
·	requirements.txt for dependencies
·	.gitignore to exclude unnecessary files (e.g., .db, .ipynb_checkpoints)













