# Business-Analytics-Project

# Predictive Analysis of Sustainability Reporting Quality Using Web-Scraped Textual Disclosures: Evidence from the European Automotive Sector (2017–2024)

## Project Overview
This project investigates whether the quality and credibility of corporate sustainability reporting can be assessed using web-scraped textual disclosures. Using Natural Language Processing (NLP) and supervised machine learning, the study analyses sustainability and annual reports published by BMW Group, Porsche AG, and Volkswagen Group between 2017 and 2024. The primary objective is to evaluate whether ESG-related narrative disclosures contain measurable informational signal capable of predicting third-party ESG evaluations.

The analysis integrates ESG-specific feature engineering, exploratory data analysis, interpretable regression modelling, and robustness checks using alternative ESG rating providers.

## Research Objectives
- To assess whether ESG-related textual disclosures can predict external ESG ratings.
- To identify which disclosure features are most predictive of ESG performance and in what direction.

## Data Description

### Datasets Used
- Web-scraped ESG disclosure features at the company-year level.
- Environmental, Social, and Governance keyword frequency datasets.
- S&P Global ESG scores used as the primary benchmark target variable.
- Sustainalytics ESG Risk scores used for sensitivity and cross-rater comparison.

### Sample Characteristics
- Companies: BMW Group, Porsche AG, Volkswagen Group  
- Period: 2017–2024  
- Unit of analysis: Company-year  

All datasets are aligned at the company-year level to ensure consistency across textual features and external ESG benchmarks.

## Feature Engineering
Textual disclosure features were extracted and normalised per 1,000 words to control for document length and improve cross-firm comparability. The feature set includes:

- Disclosure volume indicators (number of pages, word count).
- ESG intensity measures (environmental, social, and governance keywords per 1,000 words).
- Transparency and credibility indicators (framework references, assurance mentions).
- Risk acknowledgement metrics.
- Forward-looking commitment indicators (e.g. targets referencing 2030).


## Methodology
The analytical pipeline consists of the following steps:

- ESG-specific keyword frequency extraction using NLP techniques.
- Exploratory Data Analysis to assess distributional properties and inter-feature relationships.
- Supervised regression modelling to predict ESG scores.
- Model comparison between a baseline Support Vector Regression model and a Random Forest regression model.
- Feature importance analysis to support interpretability.

### Models Applied
- Support Vector Regression (RBF kernel) as a non-linear baseline model.
- Random Forest Regression as the primary model for prediction and interpretability.


## Model Evaluation
Model performance is evaluated using:
- R² (coefficient of determination)
- Root Mean Squared Error (RMSE)

Feature importance scores from the Random Forest model are used to identify the most influential disclosure characteristics.

## Additional Analyses
To extend beyond prediction accuracy, the project includes:

- An honesty gap analysis comparing predicted ESG scores with observed S&P ESG ratings.
- Sentiment analysis using the VADER framework to assess disclosure tone.
- Identification of potential positive bias where optimistic language coexists with weaker ESG performance.
- Cross-rater comparison between S&P Global ESG scores and Sustainalytics ESG Risk ratings to assess rating divergence.


## Repository Structure
├── data/
│ ├── FINAL_AUTOMOTIVE_DATASETS.csv
│ ├── ENVIRONMENTAL_FREQUENCY.csv
│ ├── Social_Frequency.csv
│ ├── Governmental_Frequency.csv
│ ├── S&P.csv
│ └── Sustainalytics ESG Risk.csv
├── code/
│ └── Project_Coding.ipynb
├── figures/
│ └── treemaps_and_plots/
├── README.md

## Reproducibility Notes
- All analyses were conducted in Python.
- Fixed random states were used to ensure reproducibility.
- Feature scaling was applied only where methodologically appropriate.
- Tree-based models were trained on unscaled but imputed data.

## Ethical and Methodological Limitations
- The analysis relies on self-disclosed corporate sustainability narratives, which may reflect strategic reporting behaviour.
- ESG ratings are subject to methodological differences across providers.
- The sample is limited to three automotive firms, constraining generalisability.
- Results reflect association rather than causal inference.

## Author and Academic Context
MSc Business Analytics Project  
University of Greenwich  

Author: Zarin Tasnim
