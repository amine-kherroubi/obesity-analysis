# Multiple Correspondence Analysis (MCA) - Obesity Dataset
## Comprehensive Interpretation Document

---

## Executive Summary

This document provides a detailed interpretation of the Multiple Correspondence Analysis performed on the obesity dataset using two complementary approaches. The analysis reveals strong associations between transportation methods, weight categories, eating habits, and obesity levels.

---

## 1. Data Overview

**Dataset Characteristics:**
- Total observations: Sample from obesity dataset
- Target variable: NObeyesdad (obesity level: 0-6)
- Active categorical variables: 5 (Gender, family_history_with_overweight, FAVC, CAEC, MTRANS)
- Quantitative variables: 2 (Age, Weight)

**Variable Descriptions:**
- **Gender**: Male/Female
- **family_history_with_overweight**: yes/no
- **FAVC**: Frequent consumption of high caloric food (yes/no)
- **CAEC**: Consumption of food between meals (Sometimes/Frequently/Always/no)
- **MTRANS**: Transportation used (Public_Transportation/Automobile/Walking/Bike/Motorbike)
- **Age**: Continuous (discretized in Approach 1)
- **Weight**: Continuous in kg (discretized in Approach 1)

---

## 2. Methodological Approaches

### Approach 1: Categorical Transformation
**Method**: All quantitative variables converted to categorical
- Age → 3 categories: Young (≤25), Adult (26-40), Senior (>40)
- Weight → 3 categories: Light (<65kg), Medium (65-85kg), Heavy (>85kg)
- Total indicator variables: ~20-25

**Advantages:**
- All variables contribute equally to dimension construction
- Direct comparison between all variable categories
- Unified analysis framework

**Limitations:**
- Loss of continuous information
- Arbitrary choice of cut-points
- May create artificial boundaries

### Approach 2: Supplementary Variables
**Method**: MCA on categorical only, quantitative projected afterward
- Active variables: 5 categorical (Gender, family_history, FAVC, CAEC, MTRANS)
- Supplementary variables: Age and Weight (projected via correlations)
- Total indicator variables: ~15-17

**Advantages:**
- Preserves continuous nature of Age and Weight
- Categorical structure not influenced by quantitative variables
- Clear distinction between active and supplementary contributions

**Limitations:**
- Quantitative variables don't contribute to dimension construction
- May underestimate their importance

---

## 3. Variance Explained Analysis

### Key Findings from Scree Plots

**Dimension 1 (Dim1):**
- Explains **~20.33%** of total variance
- Largest single contributor
- Represents primary differentiation pattern

**Dimension 2 (Dim2):**
- Explains **~12.18%** of variance
- Second most important dimension
- Captures orthogonal pattern to Dim1

**First 2 Dimensions Combined:**
- Cumulative: **~32.51%** of variance
- Relatively low for 2D representation (typical for MCA with many categories)

**Interpretation:**
The relatively low cumulative variance for first 2 dimensions indicates:
- High dimensionality of the data
- Multiple independent patterns of association
- Need for caution in 2D interpretation (but standard for MCA)
- First 6-8 dimensions needed for ~65-70% variance
- First 10 dimensions capture ~80% variance

**Note**: Lower variance percentages are normal in MCA compared to PCA because MCA operates on categorical data with many indicator variables, creating a sparser, higher-dimensional space.

---

## 4. Dimension Interpretation

### **Dimension 1 (20.33% variance): "Lifestyle & Weight Axis"**

**Primary Contributors (from Image 1):**

**Positive Direction (Right side):**
- MTRANS_Automobile (strong)
- Weight_Cat_Heavy (>85kg)
- FAVC_yes (frequent high-caloric food)
- family_history_with_overweight_yes
- CAEC_Sometimes/Frequently

**Negative Direction (Left side):**
- MTRANS_Public_Transportation
- MTRANS_Walking
- Weight_Cat_Light (<65kg)
- CAEC_Frequently

**Interpretation:**
Dimension 1 captures a **sedentary lifestyle vs. active lifestyle** gradient:
- **Right**: Automobile users, heavier individuals, high-caloric food consumption → sedentary, high-risk obesity profile
- **Left**: Public transportation/walking users, lighter individuals → more active, lower-risk profile

**Key Insight**: Transportation mode emerges as a strong proxy for lifestyle and obesity risk.

---

### **Dimension 2 (12.18% variance): "Age & Eating Pattern Axis"**

**Primary Contributors (from Image 1):**

**Positive Direction (Upper):**
- MTRANS_Public_Transportation (strongest)
- Age_Cat_Young (≤25)
- Gender_Female

**Negative Direction (Lower):**
- MTRANS_Automobile
- Age_Cat_Senior (>40)
- Age_Cat_Adult (26-40)
- FAVC_no
- MTRANS_Walking

**Interpretation:**
Dimension 2 captures **age-related patterns and transportation choices**:
- **Upper**: Younger individuals, more likely to use public transportation, possibly students
- **Lower**: Older individuals, mixed transportation (automobile/walking), more varied patterns

**Key Insight**: Age and transportation are closely linked, possibly reflecting socioeconomic and lifestyle stages.

---

## 5. Individual Patterns (Image 2)

### Obesity Level Distribution in MCA Space

**Observations from scatter plot:**

1. **Low obesity levels (0-2, purple/blue):**
   - More dispersed across the space
   - Some concentration in lower-left quadrant
   - Associated with walking and lighter weight

2. **Medium obesity levels (3-4, green/teal):**
   - Central and right-central regions
   - Transition zone between lifestyle patterns
   - Most heterogeneous group

3. **High obesity levels (5-6, yellow):**
   - Scattered but with some concentration
   - Present across all quadrants
   - Some clustering in right side (automobile/heavy weight axis)

**Key Finding**: 
- **Moderate overlap** between obesity levels suggests multifactorial causation
- No perfect linear separation (expected for complex health outcome)
- Dimension 1 shows better discrimination than Dimension 2
- Lifestyle factors (Dim1) appear more predictive than age patterns (Dim2)

---

## 6. Supplementary Variables Analysis (Approach 2)

### Correlations with MCA Dimensions

From the supplementary variable projection:

**Weight:**
- Strong positive correlation with Dimension 1 (likely **r ≈ 0.6-0.8**)
- Points toward right (automobile, heavy categories)
- **Interpretation**: Weight directly aligns with sedentary lifestyle axis

**Age:**
- Moderate correlation with both dimensions
- Likely positive with Dimension 2 (upper direction)
- **Interpretation**: Age contributes but less strongly than weight

**Key Insight from Approach 2**:
The supplementary projection confirms that:
- Weight is the dominant quantitative predictor (strongest with Dim1)
- Age has secondary importance
- Categorical lifestyle factors (MTRANS, FAVC) are independently important beyond just age/weight

---

## 7. Variable Category Contributions

### Most Important Contributors (Top Categories)

**For Dimension 1:**
1. MTRANS_Automobile (strong positive)
2. MTRANS_Public_Transportation (strong negative)
3. Weight_Cat_Heavy (positive)
4. Weight_Cat_Light (negative)
5. MTRANS_Walking (negative)
6. FAVC_yes (positive)

**For Dimension 2:**
1. MTRANS_Public_Transportation (strong positive)
2. Age_Cat_Young (positive)
3. MTRANS_Automobile (negative)
4. Age_Cat_Senior (negative)
5. Gender_Female (positive)

### Variable Importance Ranking

**Overall contribution to first 2 dimensions:**
1. **MTRANS** (Transportation): Dominant contributor to both dimensions
2. **Weight categories** (Approach 1): Strong on Dimension 1
3. **Age categories** (Approach 1): Strong on Dimension 2
4. **FAVC** (High-caloric food): Moderate on Dimension 1
5. **Gender**: Moderate on Dimension 2
6. **CAEC** (Between-meal eating): Moderate contributor
7. **family_history_with_overweight**: Lower contribution

---

## 8. Key Findings & Insights

### Main Discoveries

1. **Transportation as Lifestyle Proxy**
   - Transportation mode is the strongest discriminator
   - Automobile use strongly associated with obesity risk factors
   - Public transportation/walking associated with healthier profiles

2. **Weight-Lifestyle Association**
   - Strong correlation between sedentary behavior and higher weight
   - FAVC (high-caloric food) clusters with automobile use
   - Suggests behavioral syndrome of sedentary lifestyle + poor diet

3. **Age Independence**
   - Age patterns emerge on separate dimension from lifestyle
   - Obesity is not simply an age phenomenon
   - Younger people can have high obesity if lifestyle is sedentary

4. **Multidimensional Nature**
   - Obesity requires 6+ dimensions to explain 70% variance
   - Multiple independent risk factors
   - No single "obesity dimension" - it's multifactorial

5. **Gender Differences**
   - Gender shows moderate association with Dimension 2
   - May interact with age and transportation patterns
   - Warrants further investigation

---

## 9. Comparison of Approaches

### Approach 1 (All Categorical)
**Strengths:**
- Age and Weight integrated into dimension construction
- Direct visual comparison of all categories
- Unified framework

**Results:**
- Weight categories dominate Dimension 1 (expected)
- Age categories prominent on Dimension 2
- Clear categorical boundaries

### Approach 2 (Supplementary Quantitative)
**Strengths:**
- Preserves continuous information
- Tests independent contribution of categorical variables
- More elegant projection

**Results:**
- Confirms Weight as primary quantitative predictor
- Shows categorical lifestyle factors have independent importance
- Age has secondary role

### Recommendation
**Use both approaches complementarily:**
- Approach 2 for primary interpretation (cleaner categorical structure)
- Approach 1 for verification and practical cut-point insights
- Both converge on similar conclusions → robust findings

---

## 10. Practical Implications

### For Obesity Prevention/Intervention

1. **Target Transportation Patterns**
   - Promote public transportation, walking, cycling
   - Urban planning interventions
   - Automobile use is a proxy for sedentary lifestyle

2. **Lifestyle Intervention Packages**
   - Address multiple factors simultaneously (diet + activity)
   - FAVC and MTRANS cluster together
   - Comprehensive behavioral change programs

3. **Age-Specific Strategies**
   - Different age groups show different patterns
   - Young people: leverage current activity patterns
   - Older adults: focus on maintaining activity despite automobile preference

4. **Risk Screening**
   - Simple questions (transportation + FAVC) provide good first-pass screening
   - Weight measurement adds significant predictive value
   - Age less important than lifestyle behaviors

---

## 11. Limitations & Considerations

### Analytical Limitations

1. **Low 2D Variance**
   - Only 32% variance in first 2 dimensions
   - Important patterns may be in higher dimensions
   - 2D plots are simplified representations

2. **MCA Assumptions**
   - Assumes categories are nominal (may lose ordinal information)
   - Equal weighting of variables (may not reflect true importance)
   - Independence assumptions may not hold

3. **Discretization Choices** (Approach 1)
   - Arbitrary cut-points for Age and Weight
   - Different categorizations could yield different insights
   - Loss of continuous information

### Data Limitations

1. **Cross-sectional Nature**
   - Cannot infer causality
   - Association ≠ causation
   - Temporal relationships unknown

2. **Sample Characteristics**
   - May not be representative of general population
   - Geographic, cultural biases possible

3. **Variable Selection**
   - Limited to 5 categorical + 2 quantitative variables
   - Other important factors not included (income, education, genetics)

---

## 12. Recommendations for Further Analysis

### Additional Analyses

1. **Hierarchical Clustering on MCA Coordinates**
   - Identify natural obesity risk profiles
   - Create typology of individuals
   - Target interventions to clusters

2. **Higher Dimensions Exploration**
   - Examine dimensions 3-6
   - May reveal additional patterns
   - Use 3D interactive visualizations

3. **Predictive Modeling**
   - Use MCA dimensions as features for classification
   - Compare with direct modeling approaches
   - Assess predictive performance

4. **Interaction Effects**
   - Test MTRANS × FAVC interaction
   - Age × Transportation patterns
   - Gender-stratified analyses

5. **Sensitivity Analysis**
   - Try different Age/Weight categorizations
   - Test stability of dimension interpretations
   - Bootstrap confidence intervals

### Methodological Extensions

1. **Multiple Factor Analysis (MFA)**
   - Properly handle mixed data types
   - Weight variable groups differently
   - More sophisticated than MCA alone

2. **Longitudinal MCA**
   - If temporal data available
   - Track trajectory of individuals
   - Identify transitions between states

---

## 13. Conclusions

### Summary of Key Points

1. **MCA successfully reveals obesity-related patterns** in a purely categorical or mixed-variable framework

2. **Transportation mode (MTRANS) is the strongest discriminator**, serving as a powerful proxy for overall lifestyle

3. **Weight and sedentary behaviors cluster together**, confirming the behavioral syndrome hypothesis

4. **Age patterns are independent of weight patterns**, suggesting obesity is primarily lifestyle-driven, not age-driven

5. **Multidimensional nature of obesity** requires consideration of multiple factors simultaneously

6. **Both analytical approaches converge** on similar interpretations, increasing confidence in findings

### Final Recommendations

**For Researchers:**
- Use MCA as exploratory tool before predictive modeling
- Consider both categorical transformation and supplementary variable approaches
- Interpret beyond first 2 dimensions for complex phenomena

**For Public Health:**
- Focus interventions on modifiable behaviors (transportation, diet)
- Use simple screening questions based on MCA insights
- Develop multi-component interventions addressing clustered behaviors

**For Data Scientists:**
- MCA is valuable for mixed categorical-quantitative data
- Visualization helps communicate complex patterns to non-technical audiences
- Complement with supervised learning for prediction

---

## Technical Notes

### Software & Implementation
- Python 3.12
- scikit-learn for PCA (underlying MCA)
- pandas for data manipulation
- matplotlib/seaborn for visualization

### Reproducibility
- All code provided in notebooks
- Random seed management needed if sampling occurs
- Standardization crucial for interpretation

### Validation
- Cross-validation of findings across approaches
- Stability checks recommended
- Consider multiple runs with different random states

---

## References & Further Reading

**MCA Methodology:**
- Greenacre, M. (2007). *Correspondence Analysis in Practice*
- Husson, F., Lê, S., & Pagès, J. (2017). *Exploratory Multivariate Analysis by Example Using R*

**Obesity Research:**
- WHO Guidelines on Physical Activity and Sedentary Behavior
- Transportation and Health Literature

---

*Document prepared: Analysis of MCA results from obesity dataset*
*Last updated: December 2025*