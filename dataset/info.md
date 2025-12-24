# Estimation of Obesity Levels Based on Eating Habits and Physical Condition

## Dataset Overview

The Obesity Levels dataset provides comprehensive data for estimating obesity levels in individuals from Mexico, Peru, and Colombia based on their eating habits and physical condition. Published in 2019 by Fabio Mendoza Palechor and Alexis De la Hoz Manotas, this dataset enables analysis of lifestyle factors contributing to obesity.

**Source:** UCI Machine Learning Repository (ID: 544)  
**DOI:** 10.24432/C5H31Z  
**License:** Creative Commons Attribution 4.0 International (CC BY 4.0)  
**Publication:** Data in Brief, 2019

## Key Dataset Characteristics

| Property                   | Value                                            |
| -------------------------- | ------------------------------------------------ |
| **Number of observations** | 2,111                                            |
| **Number of variables**    | 17 (16 features + 1 target)                      |
| **Missing values**         | None                                             |
| **Analytical tasks**       | Classification, Regression, Clustering           |
| **Data origin**            | 77% synthetic (SMOTE), 23% direct web collection |
| **Geographic scope**       | Latin America (Mexico, Peru, Colombia)           |

## Target Variable

### **NObeyesdad** (Obesity Level)
- **Type:** Categorical (7 levels)
- **Role:** Dependent variable / Target
- **Categories:**
  1. **Insufficient Weight** - BMI < 18.5
  2. **Normal Weight** - BMI 18.5-24.9
  3. **Overweight Level I** - BMI 25-27
  4. **Overweight Level II** - BMI 27-30
  5. **Obesity Type I** - BMI 30-35
  6. **Obesity Type II** - BMI 35-40
  7. **Obesity Type III** - BMI > 40

**Interpretation:** This ordered categorical variable represents the severity of weight status, from underweight to morbid obesity. The classification follows medical standards based on Body Mass Index (BMI) calculations.

---

## Feature Variables

### Demographic Variables

#### **Gender**
- **Type:** Binary categorical
- **Categories:** Male, Female
- **Description:** Biological sex of the individual
- **Analytical relevance:** Gender differences in metabolism, body composition, and obesity prevalence are well-documented in medical literature

#### **Age**
- **Type:** Continuous numeric
- **Unit:** Years
- **Typical range:** 14-61 years (estimated)
- **Description:** Age of the individual
- **Analytical relevance:** Age affects metabolism, activity levels, and obesity risk. Useful for age-stratified analysis

---

### Anthropometric Variables

#### **Height**
- **Type:** Continuous numeric
- **Unit:** Meters
- **Typical range:** 1.45-1.98 m (estimated)
- **Description:** Individual's height
- **Analytical relevance:** Essential for BMI calculation (Weight/Height²). Taller individuals may have different weight distributions

#### **Weight**
- **Type:** Continuous numeric
- **Unit:** Kilograms
- **Typical range:** 39-173 kg (estimated)
- **Description:** Body weight of the individual
- **Analytical relevance:** Primary outcome measure. Direct indicator of obesity when combined with height

---

### Dietary Habit Variables

#### **family_history_with_overweight**
- **Type:** Binary
- **Categories:** yes, no
- **Question:** "Has a family member suffered or suffers from overweight?"
- **Analytical relevance:** Genetic predisposition indicator. Strong predictor of obesity risk due to both genetic and environmental factors

#### **FAVC** (Frequent consumption of high caloric food)
- **Type:** Binary
- **Categories:** yes, no
- **Question:** "Do you eat high caloric food frequently?"
- **Examples:** Fast food, sweets, fried foods, sugary drinks
- **Analytical relevance:** Direct measure of diet quality. High-calorie foods are major contributors to weight gain

#### **FCVC** (Frequency of consumption of vegetables)
- **Type:** Integer (ordinal)
- **Scale:** 1-3
  - 1 = Never or rarely
  - 2 = Sometimes
  - 3 = Always
- **Question:** "Do you usually eat vegetables in your meals?"
- **Analytical relevance:** Vegetable consumption is inversely related to obesity. Indicator of healthy eating patterns

#### **NCP** (Number of main meals)
- **Type:** Continuous (discrete values)
- **Typical range:** 1-4 meals per day
- **Question:** "How many main meals do you have daily?"
- **Analytical relevance:** Meal frequency patterns affect metabolism. Very low (1) or very high (4+) may indicate irregular eating habits

#### **CAEC** (Consumption of food between meals)
- **Type:** Categorical (4 levels)
- **Categories:** no, Sometimes, Frequently, Always
- **Question:** "Do you eat any food between meals?"
- **Common examples:** Snacks, chips, cookies, fruits
- **Analytical relevance:** Snacking behavior significantly impacts total caloric intake. Frequent snacking often associated with weight gain

---

### Lifestyle and Substance Use Variables

#### **SMOKE**
- **Type:** Binary
- **Categories:** yes, no
- **Question:** "Do you smoke?"
- **Analytical relevance:** Smoking affects metabolism and appetite. Paradoxically, smokers may have lower BMI but worse health outcomes

#### **CH2O** (Daily water consumption)
- **Type:** Continuous (discrete values)
- **Unit:** Liters per day
- **Scale:** 1-3
  - 1 = Less than 1 liter
  - 2 = 1-2 liters
  - 3 = More than 2 liters
- **Question:** "How much water do you drink daily?"
- **Analytical relevance:** Adequate hydration supports metabolism. Water intake may replace sugary beverages

#### **SCC** (Calories consumption monitoring)
- **Type:** Binary
- **Categories:** yes, no
- **Question:** "Do you monitor the calories you eat daily?"
- **Analytical relevance:** Self-monitoring behavior indicates health consciousness. Associated with weight management success

#### **CALC** (Consumption of alcohol)
- **Type:** Categorical (4 levels)
- **Categories:** no, Sometimes, Frequently, Always
- **Question:** "How often do you drink alcohol?"
- **Analytical relevance:** Alcohol provides empty calories (7 kcal/g) and reduces inhibition around food choices. High consumption linked to weight gain

---

### Physical Activity Variables

#### **FAF** (Physical activity frequency)
- **Type:** Continuous (discrete values)
- **Scale:** 0-3
  - 0 = No physical activity
  - 1 = 1-2 days per week
  - 2 = 2-4 days per week
  - 3 = 4-5 days per week
- **Question:** "How often do you have physical activity?"
- **Analytical relevance:** Exercise is crucial for weight management. Creates caloric deficit and improves metabolic health

#### **TUE** (Time using technology devices)
- **Type:** Integer
- **Unit:** Hours per day
- **Scale:** 0-2+
- **Question:** "How much time do you use technological devices such as cell phone, videogames, television, computer and others?"
- **Analytical relevance:** Proxy for sedentary behavior. Screen time inversely related to physical activity and associated with obesity

#### **MTRANS** (Transportation used)
- **Type:** Categorical (5 levels)
- **Categories:** Automobile, Motorbike, Bike, Public_Transportation, Walking
- **Question:** "Which transportation do you usually use?"
- **Analytical relevance:** Transportation mode indicates daily physical activity level. Walking/biking = active transport = higher energy expenditure

---

## Variable Classification Tables

### By Data Type

| Type                        | Variables                                                | Count  |
| --------------------------- | -------------------------------------------------------- | ------ |
| **Continuous**              | Age, Height, Weight, NCP, CH2O, FAF                      | 6      |
| **Integer (Ordinal)**       | FCVC, TUE                                                | 2      |
| **Binary Categorical**      | Gender, family_history_with_overweight, FAVC, SMOKE, SCC | 5      |
| **Multi-level Categorical** | CAEC, CALC, MTRANS, NObeyesdad                           | 4      |
| **TOTAL**                   |                                                          | **17** |

### By Thematic Category

| Category                 | Variables                             | Purpose                        |
| ------------------------ | ------------------------------------- | ------------------------------ |
| **Demographic**          | Gender, Age                           | Population characteristics     |
| **Anthropometric**       | Height, Weight                        | Body measurements              |
| **Diet**                 | family_history, FAVC, FCVC, NCP, CAEC | Eating patterns                |
| **Hydration/Substances** | CH2O, SMOKE, CALC                     | Beverage/substance use         |
| **Physical Activity**    | FAF, TUE, MTRANS, SCC                 | Activity levels and monitoring |
| **Outcome**              | NObeyesdad                            | Target variable                |

### Qualitative Variables with >2 Categories

| Variable       | # Categories | Categories                                   | Analytical Importance |
| -------------- | ------------ | -------------------------------------------- | --------------------- |
| **NObeyesdad** | 7            | Insufficient → Obesity III                   | Target variable       |
| **MTRANS**     | 5            | Automobile, Motorbike, Bike, Public, Walking | Activity indicator    |
| **CAEC**       | 4            | no, Sometimes, Frequently, Always            | Snacking behavior     |
| **CALC**       | 4            | no, Sometimes, Frequently, Always            | Alcohol intake        |

---

## Data Generation Methodology

### Real Data (23% - 485 observations)
- **Collection method:** Web-based survey platform
- **Geographic distribution:** Mexico, Peru, Colombia
- **Participant recruitment:** Voluntary participation
- **Data quality:** Self-reported measurements (potential bias)

### Synthetic Data (77% - 1,626 observations)
- **Generation tool:** Weka machine learning software
- **Technique:** SMOTE (Synthetic Minority Over-sampling Technique)
- **Purpose:** 
  - Balance class distribution of NObeyesdad
  - Increase dataset size for machine learning
  - Preserve statistical relationships between variables
- **Implication:** Data represents plausible combinations of features but not necessarily real individuals

---

## Calculated Metrics

### Body Mass Index (BMI)
Although not explicitly included, BMI can be calculated from Height and Weight:

**BMI = Weight (kg) / [Height (m)]²**

**WHO Classification:**
- **< 18.5:** Underweight (Insufficient Weight)
- **18.5-24.9:** Normal weight
- **25.0-29.9:** Overweight
- **30.0-34.9:** Obesity Class I
- **35.0-39.9:** Obesity Class II
- **≥ 40.0:** Obesity Class III (Morbid Obesity)

The NObeyesdad variable appears to be derived from BMI calculations.

---

## Statistical Analysis Opportunities

### 1. **Descriptive Statistics**
- Distribution of obesity levels across countries
- Gender differences in obesity prevalence
- Age-stratified obesity rates
- Frequency tables for categorical variables

### 2. **Inferential Statistics**
- **Chi-square tests:** Associations between categorical variables
  - Example: Gender × NObeyesdad, MTRANS × NObeyesdad
- **ANOVA:** Group differences in continuous variables
  - Example: Mean Weight across CALC categories
- **T-tests:** Binary group comparisons
  - Example: Weight difference between smokers and non-smokers

### 3. **Multivariate Analysis**
- **Multiple Correspondence Analysis (MCA):** Relationships among categorical variables
- **Principal Component Analysis (PCA):** Dimensionality reduction of continuous variables
- **Cluster Analysis:** Identification of behavioral profiles

### 4. **Regression Modeling**
- **Linear Regression:** Predict Weight from lifestyle factors
- **Logistic Regression:** Predict obesity status (binary: obese vs. not obese)
- **Ordinal Regression:** Predict NObeyesdad ordered categories
- **Multiple Regression:** Model Weight as function of Age, FAF, FCVC, CH2O, etc.

### 5. **Classification**
- **Decision Trees:** Interpretable classification rules
- **Random Forest:** Ensemble prediction of obesity level
- **Support Vector Machines:** Non-linear classification

---

## Key Research Questions

This dataset can address multiple research questions:

1. **What lifestyle factors are most strongly associated with obesity?**
   - Compare effect sizes of FAVC, FAF, MTRANS, CALC

2. **Do dietary habits or physical activity have stronger impact on obesity?**
   - Compare R² or odds ratios between diet variables vs. activity variables

3. **How does family history interact with lifestyle choices?**
   - Stratified analysis: family_history = yes vs. no

4. **Are there distinct behavioral profiles leading to different obesity levels?**
   - Cluster analysis identifying high-risk vs. low-risk profiles

5. **Can we predict obesity level from self-reported behaviors?**
   - Classification models with accuracy evaluation

6. **What is the role of transportation mode in obesity?**
   - Compare obesity rates: Walking/Bike vs. Automobile users

---

## Data Quality Considerations

### Strengths
- ✓ No missing values (complete cases)
- ✓ Balanced representation across obesity levels
- ✓ Multiple dimensions captured (diet, activity, demographics)
- ✓ Ordinal scales allow for graded responses
- ✓ Real-world applicability to public health

### Limitations
- ⚠ 77% synthetic data (may not reflect real population distributions)
- ⚠ Self-reported measurements (Height/Weight may have reporting bias)
- ⚠ Cross-sectional design (cannot establish causality)
- ⚠ Limited to three Latin American countries (generalizability concerns)
- ⚠ No temporal data (cannot assess changes over time)

### Recommendations for Analysis
- Acknowledge synthetic data proportion in methodology section
- Use appropriate statistical tests for ordinal variables (e.g., Spearman correlation, not Pearson)
- Consider treating NObeyesdad as ordinal rather than nominal
- Validate findings with external obesity research literature

---

## Importing the Dataset

### Method 1: Python (ucimlrepo package)

```python
# Install package
# pip install ucimlrepo

from ucimlrepo import fetch_ucirepo 

# Fetch dataset
obesity_data = fetch_ucirepo(id=544) 

# Extract features and target
X = obesity_data.data.features  # 16 features
y = obesity_data.data.targets   # NObeyesdad

# View metadata
print(obesity_data.metadata) 

# View variable information
print(obesity_data.variables)

# Convert to pandas DataFrame
import pandas as pd
df = pd.concat([X, y], axis=1)
print(df.shape)  # (2111, 17)
print(df.head())
```

### Method 2: Direct CSV Download

**File:** `ObesityDataSet_raw_and_data_sinthetic.csv` (257.5 KB)  
**URL:** https://archive.ics.uci.edu/dataset/544

```python
import pandas as pd

df = pd.read_csv('ObesityDataSet_raw_and_data_sinthetic.csv')
print(df.info())
print(df['NObeyesdad'].value_counts())
```

### Method 3: R

```r
# Install and load package
install.packages("RCurl")
library(RCurl)

# Download from UCI
url <- "https://archive.ics.uci.edu/ml/machine-learning-databases/00544/ObesityDataSet_raw_and_data_sinthetic.csv"
obesity_data <- read.csv(url)

# View structure
str(obesity_data)
summary(obesity_data)
table(obesity_data$NObeyesdad)
```

---

## Expected Data Structure

Sample rows (hypothetical values):

| Gender | Age | Height | Weight | family_history | FAVC | FCVC | NCP | CAEC       | SMOKE | CH2O | SCC | FAF | TUE | CALC      | MTRANS     | NObeyesdad     |
| ------ | --- | ------ | ------ | -------------- | ---- | ---- | --- | ---------- | ----- | ---- | --- | --- | --- | --------- | ---------- | -------------- |
| Female | 21  | 1.62   | 64     | yes            | no   | 2    | 3   | Sometimes  | no    | 2    | no  | 0   | 1   | no        | Public     | Normal_Weight  |
| Male   | 32  | 1.75   | 98     | yes            | yes  | 1    | 3   | Frequently | no    | 2    | no  | 1   | 2   | Sometimes | Automobile | Obesity_Type_I |
| Female | 28  | 1.58   | 52     | no             | no   | 3    | 4   | no         | no    | 3    | yes | 3   | 0   | no        | Walking    | Normal_Weight  |

---

## Citation

**Dataset Citation:**  
Mendoza Palechor, F., & De la Hoz Manotas, A. (2019). Estimation of Obesity Levels Based On Eating Habits and Physical Condition [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5H31Z

**Paper Citation:**  
Mendoza Palechor, F., & De la Hoz Manotas, A. (2019). Dataset for estimation of obesity levels based on eating habits and physical condition in individuals from Colombia, Peru and Mexico. *Data in Brief*, 25, 104344. https://doi.org/10.1016/j.dib.2019.104344

---

## Summary

This obesity dataset is well-suited for educational statistical analysis projects because it:
- Contains sufficient observations (2,111) for robust analysis
- Includes balanced mix of categorical and continuous variables
- Addresses relevant public health topic (obesity epidemic)
- Enables multiple analytical approaches (descriptive, inferential, multivariate, predictive)
- Has no missing values (simplifies preprocessing)
- Provides ordinal outcome variable with 7 clinically meaningful levels

The dataset supports comprehensive analysis of how lifestyle factors (diet, physical activity, transportation, substance use) relate to obesity levels, making it ideal for demonstrating statistical methods in a real-world health context.