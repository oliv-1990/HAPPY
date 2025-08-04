What Makes Nations Happy: A Global Analysis of Happiness and Developmental indicators

Project Setup Instructions
To run this project locally:
1. Clone the Repository
git clone https://github.com/oliv-1990/HAPPY.git
cd HAPPY
2. CREATE AND ACTIVATE A VIRTUAL ENVIRONMENT
On Windows (Command Prompt):
python -m venv venv
venv\Scripts\activate
On macOS/Linux:
python3 -m venv venv
source venv/bin/activate
3. INSTALL REQUIRED DEPENDENCIES
pip install -r requirements.txt
4. RUN THE JUPYTER NOTEBOOK
Jupiter notebook
If you do not have Jupiter notebook
pip install notebook
NOTES:
You have to have Python 3.7 or higher installed.
Use relative file paths (e.g., ./data/file.csv) for dataset loading.
To deactivate the virtual environment, run:
deactivate

Overview
This capstone project explores how national happiness relates to key socio-economic development indicators across developed and developing countries from 2005 to 2022. By combining data from the World Happiness Report and the World Bank Development Indicators, the goal is to understand which factors most correlate citizens' well-being — and how these patterns vary globally.
Objective
Research Question: Which development indicators are most strongly associated with national happiness across a diverse global sample of countries?
While many governments use GDP as a primary signal of national well-being, this project investigates how other factors — such as education, healthcare, military spending, and other indicators — have a positive or negative relationship with happiness. By expanding the scope beyond traditional economic measures, this analysis aims to provide insights that may help inform more holistic and inclusive policy decisions focused on human well-being, especially in both urban and rural contexts.

Key Columns Used for Merging
To combine the datasets from the World Happiness Report and the World Bank Development Indicators, two key columns were used:
- 'country': Identifies the country or geographic region; present in both datasets
- 'year': The calendar year of the data; used to align corresponding records across time

Selected Features
This project combines key variables from the World Happiness Report and the World Bank Development Indicators. These were selected based on relevance to well-being, policy relevance, and data availability from 2005–2022.
From the World Happiness Report:
·   ladder_score(later changed to Happiness_Score): Self-reported life satisfaction on a scale from 0 to 10
·   Log_GDP_per_capita: Logarithm of income per person
·   Country: Identifies the country or geographic region
·   Year: The calendar year of the data
From the World Bank Development Indicators:
·    military_expenditure_percent_gdp: Military spending as a percentage of GDP
·   education_expenditure_percent_gdp: Government education spending as a percentage of GDP
·   health_expenditure_percent_gdp: Government health spending as a percentage of GDP
·   access_to_electricity%: Percentage of the population that has access to electricity
·   renewvable_energy_consumption%: Renewable energy consumption as a % of total final energy consumption.
·   population_density: Population density, measured in people per km^2 of land area. 
        ·   Country: Identifies the country or region (also used for merging)
        ·   Year: Calendar year (also used for merging)
 Note: The datasets originally included many additional indicators. This subset was chosen by me for its explanatory power, interpretability, and completeness across countries and years.
Datasets Used
1.World Happiness Report (2005–2022)
•   Annual happiness scores (Ladder Score) and supporting economic indicators
•    Source: worldhappiness.report
 2.World Bank Development Indicators
•   Global socio-economic and infrastructure data across countries, including GDP, health, education, and internet access
•    Source: databank.worldbank.org
Evaluation Plan
To assess the quality and success of my analysis, I followed a multi-step evaluation strategy:
·   I prioritized interpretability and clarity, ensuring the results are accessible to both technical and non-technical audiences.
·   I have continuously sought feedback from peers and mentors to validate insights and refine my approach.
Tech Stack
Technologies Used
•   Python – This is my main programming language used for all data processing, analysis, and modeling tasks.
•   Pandas – I used to load, clean, merge, and manipulate datasets. I merged our two datasets, the Happiness and Developmental Indicators. I renamed a few important columns to adjust the names across my two datasets before merging, such as 'Year' and 'country'. Also, I created a few columns and changed data types across columns to make the merge more successful. I removed some columns that had a lot of missing data or, in my opinion, did not fit into my research plan, such as 'land area', 'forest land', 'death rate', 'rural population', etc. I also performed the fillna function across some columns to make my merge easier.
•   Matplotlib - I used Matplotlib to explore and present data through a variety of visualizations, including bar charts, a scatter plot where I analyzed Happiness scores with the GDP of a particular country, and a line plot that revealed trends and relationships between happiness and development indicators across years and the chosen countries. In combination with Seaborn, I created a custom-colored heatmap where I explored missing data in the Happiness dataset, using ListedColormap to identify columns with fewer gaps. Pink lines represented missing values, and blue lines indicated present ones. Matplotlib also gave me control over plot formatting, making the visuals readable and effective for both analysis and presentation.
•   Seaborn: I used Seaborn to build horizontal bar charts that compared Happiness Score and Log GDP per Capita, Government health spending as a percentage and Happiness Score, and other developmental indicators for each country from 2005 to 2022. By using color gradients, bright colors, finding averages for each country, and sorting the data, it helped highlight how happiness levels relate to national income levels and other developmental indicators across countries in a more engaging way. Also, as a culmination of my analysis, I used Matplotlib to build a line graph that included the most correlated indicators with happiness in order to see how they correlated across the countries over the period of 2005–2022.
•   SciPy (pearsonr) – Used to compute Pearson correlation coefficients and p-values, providing insight into how strongly each development factor is related to happiness and whether those relationships are statistically significant.
•   SQLite – Used to store the cleaned, merged datasets and run SQL queries efficiently, making data retrieval and analysis faster and more organized. As a result, created merged_sql_df to use it as the main Data Frame in building visuals, performing EDA, and performing correlation analysis.
•   Jupiter Notebooks – Used to write and present my entire project in a clear, interactive, and narrative-driven format.
•   VS Code – Used for coding environment for writing Python scripts, managing version control, and organizing the project files.
•   Git & GitHub – Used for version control and collaboration, allowing project updates and backup throughout development.
•   venv – Used to create a virtual environment ensuring that dependencies are isolated and reproducible across systems.
Conclusion
Through this project, I found that while wealth (GDP per capita) plays a role in national happiness, it’s not the sole factor. Countries that invest more in healthcare, education, and access to infrastructure like electricity tend to report higher happiness scores. My analysis showed that smart, people-centered spending has a stronger and more consistent relationship with well-being than economic wealth alone.
Specifically, GDP per capita, government health expenditure, and access to electricity demonstrated moderate positive correlations with happiness, while education spending showed a weaker but still positive association. This suggests that countries allocating a higher percentage of GDP toward social programs or infrastructure tend to have higher happiness scores. On the other hand, population density was weakly negatively correlated with happiness, and renewable energy use showed a moderate negative correlation—possibly due to economic or infrastructural challenges in implementing renewables. Military spending showed a weak positive correlation, which may reflect broader national security contexts in some cases, though in others, it may divert resources away from social programs.








