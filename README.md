# Food Waste & Nutrition Indicators (FAOSTAT Data)

## Background & Context  
Food loss and waste is a critical global issue with multifaceted impacts. Roughly **30% of food produced for human consumption is lost or wasted each year**, amounting to about **1.3 billion tonnes of food**. This squandered food has enormous implications: **FAO estimates that the food we lose and waste annually could feed 1.26 billion hungry people**. Reducing food wastage is thus not only a matter of resource efficiency but also of improving food security and nutrition. In fact, cutting food loss and waste is enshrined in **Sustainable Development Goal (SDG) 12.3**, which calls for halving per-capita global food waste and reducing losses by 2030.  

![](https://www.mdpi.com/resources/resources-13-00164/article_deploy/html/images/resources-13-00164-g003-550.jpg)

Paradoxically, the world today faces a **“double burden” of malnutrition** – persistent undernourishment in many countries alongside rising obesity in others. **Over 828 million people were undernourished in 2021**, even as obesity rates have climbed worldwide. Understanding how **food waste** relates to **nutrition outcomes** is therefore a pressing analytical challenge. For example, excess food availability might contribute to both **higher obesity and more waste**, while inadequate distribution and access lead to **undernutrition even amid plenty**. Recent research has hypothesized that **greater food losses lead to lower per-capita food supply, thereby reducing a population’s dietary intake**. Empirical findings support some of these links – for instance, studies show that **increases in per-capita food supply are associated with lower prevalence of undernourishment**. This complex relationship may involve **intermediate factors** (e.g., overall food availability) mediating the impact of waste on nutritional status.

Against this backdrop, this week-long challenge asks participants to **explore and model the relationships between food waste and nutrition indicators** using data from FAO’s **FAOSTAT** database. Participants will investigate how variations in food waste/losses correlate with three key nutrition outcomes – dietary energy adequacy, undernourishment, and obesity – and assess whether an abundance of food supply (per capita) mediates these relationships. The goal is to derive insights that could inform policies for reducing waste while improving nutrition. This project is geared toward **postgraduate students** (Masters/PhD level) with **mixed levels of experience** in statistics, data science, and domain knowledge. Over the course of one intensive week, teams will formulate a research question, assemble and analyze a country-level panel dataset from FAOSTAT, apply suitable statistical or machine-learning models, and present their findings in a reproducible Jupyter Notebook.

---

## Challenge Objectives and Core Task  

### Objective  
Determine how **food waste** is related to national-level **nutrition and food-security indicators**, and whether **food supply per capita** mediates these relationships. Participants should use **only FAOSTAT data** for a **panel of countries over time** to ensure consistency and comparability.

### Core Modeling Task  
Analyze how **food waste** relates to each of the following three target nutrition indicators (with potential mediation by per-capita food supply):  

1. **Dietary Energy Adequacy** – The average dietary energy supply as a percentage of the population’s required energy needs.  
2. **Prevalence of Undernourishment** – The share of the population that is chronically undernourished (consuming less than the minimum dietary energy requirement).  
3. **Prevalence of Obesity** – The share of the adult population that is obese (BMI ≥ 30).  

**Mediating Factor:** **Food Supply per Capita** – The average food availability per person, measured in kilocalories per person per day.

Teams are expected to build models (or sets of models) that capture the relationship between **food waste** (independent variable) and the three **nutrition indicators** (dependent variables), while considering **food supply per capita** as a crucial intermediate variable.

---

## Data Source: FAOSTAT Panel Data  

All analysis will be based on **FAOSTAT**, which provides free access to country-level data from 1961 onward. Key domains:

- **Food Waste / Loss:** Use metrics such as **“Losses”** from Food Balance Sheets or the **Food Loss Index** where available.  
- **Nutrition Indicators:** Retrieve dietary energy adequacy, undernourishment, and obesity series from the **Food Security** domain.  
- **Mediator:** Obtain **Dietary Energy Supply per capita** (kcal/person/day) from **Food Balance Sheets**.  
- **Additional Predictors:** Explore ~2000 other FAOSTAT variables (production, trade, prices, demographics, etc.) while avoiding tautologies.

### Data Access  
Participants may download data manually via the FAOSTAT interface or programmatically via the **FAOSTAT API** (or packages like `faostat` in R/Python).

---

## Countries for Analysis  

| Region/Type | Country | Rationale |
|-------------|---------|-----------|
| EU (mandatory) | **Bulgaria** | Transitioning food system, moderate waste issues |
| High-income EU | France | Adequate diets, active waste-reduction policies |
| High-income EU | Germany | High surplus, distinct obesity profile |
| Sub-Saharan Africa | Nigeria | High undernourishment, post-harvest losses |
| South Asia | India | Large undernourished population, growing obesity |
| Latin America | Brazil | Rising obesity, emerging economy |
| North America | USA | Very high obesity & waste, low hunger |
| MENA | Egypt | High obesity, import-reliant, food insecurity |
| Southeast Asia | Vietnam | Rapid dietary shift, changing waste patterns |
| Latin America | Mexico | Obesity crisis, notable waste |

Aim for roughly **20–30 years of data** per country (balanced where possible).

---

## Modeling Approach & Requirements  

1. **Panel-data awareness**  
   - Fixed/random effects, clustered errors, or lagged variables for temporal dynamics.  
2. **Machine-learning focus** (preferred)  
   - **Ensembles** (Random Forest, XGBoost) with grouped/time-series CV.  
   - **Regularized regression** (Lasso/Ridge) for feature selection.  
   - **Recurrent models** (LSTM/GRU) optional for ambitious teams.  
3. **Avoid tautologies**  
   - Do **not** use variables definitionally tied to targets (e.g., kcal supply inside adequacy).  
4. **Thematic feature engineering**  
   - Lag effects, per-capita conversions, supply variability, etc.  
5. **Interpretability**  
   - Mediation analysis or importance plots to explain findings.  
6. **Validation**  
   - Leave-one-country-out or time-split CV to avoid overfitting.

---

## Deliverables  

A **single, self-contained Jupyter Notebook** that includes:

- **Introduction & Research Questions**  
- **Data Preparation** (FAOSTAT retrieval, cleaning, EDA)  
- **Methodology** (model specs, mediator handling)  
- **Results** (tables, coefficient/importance plots, diagnostics)  
- **Discussion** (interpretation, limitations, policy takeaways)  
- **Conclusion** (key insights)  

Notebook must be runnable, well-commented, and written in a clear, narrative style.

---

## Resources and Support Provided  

**FAOSTAT Data Access Guide**   
  – [FAOSTAT Data Explorer](https://www.fao.org/faostat/en/#data)   
  – [FAOSTAT API root](https://fenixservices.fao.org/faostat/api/v1/en)    
**Panel-data Tips Sheet**   
  – [Princeton DSS “Panel Data 101” (PDF)](https://www.princeton.edu/~otorres/Panel101.pdf)   
**Suggested ML Tools**  
  – [XGBoost](https://xgboost.readthedocs.io/en/stable/)  
  – [LightGBM](https://lightgbm.readthedocs.io/en/stable/)   
  – [scikit-learn](https://scikit-learn.org/stable/)   
  – [statsmodels](https://www.statsmodels.org/stable/)   
  – [plm (R package)](https://cran.r-project.org/package=plm)    
**Example Paper**
  – Todorova & Haralampiev (2024), *“What Are the Impacts of Food Losses on Nutrition?”* [Journal of Ecohumanism](https://ecohumanism.co.uk/joe/ecohumanism/article/view/4001)  
**Domain Fact Sheets** 
  – [SOFI 2024 (global kcal norms)](https://www.fao.org/3/cc7748en/cc7748en.pdf)  
  – [UNEP Food Waste Index Report 2021](https://www.unep.org/resources/report/unep-food-waste-index-report-2021)  
  – [UN SDG 12.3 overview](https://www.un.org/sustainabledevelopment/sustainable-consumption-production/)  

