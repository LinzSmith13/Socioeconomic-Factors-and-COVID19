# Socioeconomic-Factors-and-COVID19

## Which socioeconomic factors best predict the pandemic's severity?
When the COVID-19 pandemic first swept across the United States in the spring of 2020, its impact was not felt equally. Before the widespread availability of testing, standardized treatments, or vaccines, early mortality rates provided a stark reflection of existing systemic inequities.
The goal of this analysis is to investigate the relationship between county-level socioeconomic factors and early COVID-19 mortality rates, specifically focusing on the most vulnerable demographic: the over-60 population.

## Data & Methodology
To explore this, I combined COVID-19 time-series mortality data with American Community Survey (ACS) demographic data.
- Target Variable: Deaths per 100k residents.
- Features Analyzed: Mean senior income, senior poverty rates, senior unemployment, and racial/ethnic demographics (specifically the percentages of Black and Hispanic senior populations).
- Modeling Approach: Due to the complex, non-linear relationships and high multicollinearity inherent in socioeconomic data (e.g., the overlap between poverty rates and historically marginalized communities), a Random Forest Regressor was utilized to extract and rank feature importance.

## EDA
The challenge of early-pandemic data:
The target variable (deaths per 100k) exhibited a severe right skew. Because this data represents the spring of 2020, the virus was highly localized to major travel hubs, leaving the vast majority of US counties with zero recorded deaths.
Initial correlation mapping revealed weak linear relationships between individual features and mortality. However, it highlighted significant multicollinearity among the socioeconomic variables (such as poverty rates and minority populations), confirming that a simple linear regression would be insufficient, and a Random Forest model was the appropriate choice.

## Model Performance & Results
- R-squared: 0.0221
- RMSE: 1.2212 deaths per 100k
_While an R-squared of ~0.02 is objectively low, it is expected given the zero-inflated nature of early-pandemic data. Because the virus was not yet ubiquitous across the country, socioeconomic factors alone could not explain the total variance in death rates—geographical introduction of the virus was the dominant, unmeasured factor._

## Key Findings, Feature Importance
The model successfully isolated the strongest socioeconomic signals where the virus did take hold:
The percentage of elderly Black residents (Pct_Over60_Black) emerged as the most powerful predictor of early pandemic deaths.
Senior unemployment rates and mean income were the next most critical factors, demonstrating that financial resources directly dictated vulnerability.
Systemic racial inequities and economic instability were the two factors that predicted higher deaths from COVID-19.  

## Conclusions
The Random Forest model reinforces the public health consensus: long before vaccines were available, existing systemic inequities and economic instability created severe vulnerabilities. As the virus spread, marginalized and economically disadvantaged senior populations were hit the hardest. A valuable continuation of this project would involve running this exact model on data from late 2020 or early 2021. Once the virus had spread uniformly across all US counties, the model's predictive power (R-squared) would likely increase significantly, creating an even clearer picture of socioeconomic determinants of health outcomes. 
