# Truebridge-Healthcare-EDA
As part of a maternal health analytics initiative, this analysis evaluates whether delayed prenatal care impacts gestational age and identifies which populations face the greatest risk.


# Project Background

Gestational age at birth is a key predictor of infant health. Preterm birth is associated with higher risks of medical complications and long-term health challenges. Despite advances in obstetric care, disparities in birth outcomes persist across socioeconomic and geographic groups in the United States.
Early prenatal care is often considered protective, but access and engagement vary widely based on education, region, and broader social factors. Many analyses focus only on average effects, masking how different populations may experience different levels of risk.
This project examines whether delayed prenatal care is associated with shorter gestational age — and more importantly, which populations are most affected. The goal is to provide healthcare stakeholders with clearer insight into where targeted outreach and intervention strategies may have the greatest impact.

Insights and recommendations are based on the following areas
- Demographic stratification
- Effect modification
- Geographic context
- Risk interpretation
- Policy implications



Interactive dashboard  [here](https://birth-outcomes-lab.base44.app)



Python code here


[Download Maternity Dataset](./Extern%20Maternity%20dataset%2012-17-2025.xlsx)



The slideshow presentation for this analysis can be found [here](https://docs.google.com/presentation/d/172dNhzClbHkm6S5NZ6ZgezhJBNB9bon05y44OQYIPEY/edit?usp=sharing)

 # Data Structure
 The dataset used consist of 6 tables; birth record, census region, prenatal care, mother's education, mother's race, and year.

 The dataset is organized using a relational model centered on the Birth_Records table. This table functions as the primary fact table and contains one row per birth, with outcome and exposure variables including:
- Gestational_Age
- Prenatal_Care_Timing
- Race_ID
- Education_ID
- Region_ID
- Year_ID
  
Each record represents an individual birth event and serves as the foundation for all outcome analysis.

Relational Structure
The Birth_Records table connects to four supporting dimension tables through foreign keys:
- Region – defines geographic grouping of births
- Education – categorizes maternal education level
- Race – standardizes maternal racial classification
- Year – enables time-based trend analysis

  
Each dimension table contains a primary key (e.g., Region_ID, Education_ID) that links back to the Birth_Records table. This structure ensures:
- Normalized data storage
- Reduced redundancy
- Consistent category definitions
- Clean segmentation across demographic and geographic groups
  
Why This Design Matters
This relational structure allows gestational age outcomes to be analyzed across multiple dimensions without duplicating demographic data. 

Because demographic attributes are stored separately and linked through keys, the model supports:
- Stratified comparisons (e.g., by race or education)
- Regional trend analysis
- Effect modification testing
- Time-series evaluation

  
The overall design resembles a simplified star schema commonly used in healthcare analytics and business intelligence environments, where a central outcomes table is joined to descriptive dimension tables for reporting and segmentation.

Cross-Industry Relevance
Although this project focuses on maternal health, the structure reflects patterns widely used across industries:
- Time dimension (Year)
- Geographic segmentation (Region)
- Demographic attributes (Race, Education)
- Measurable outcome variable (Gestational_Age)
- This demonstrates familiarity with relational database concepts and scalable analytical design beyond a single healthcare use case.
 
<img width="550" height="550" alt="image" src="https://github.com/user-attachments/assets/f34dc937-bd62-4b23-92a8-1b93cb7d6166" />

Prior to the beginning of analysis, a variety of checks were conducted for quality control within the dataset. Python was utilized to inspect and control quality checks and can be found HERE.


 

 # Executive Summary

 Overall, while average gestational age remains stable across social groups, delayed prenatal care introduces meaningful risk through increased variability especially among structurally disadvantaged populations and regions with limited healthcare access.
Who should care and why:
Health systems, Medicaid programs, and public health agencies because delayed prenatal care acts as an early warning signal for concentrated risk especially in underserved populations and regions with limited access to obstetric care.

The objective is to support healthcare systems and public health programs in targeting interventions where delayed prenatal care has the greatest measurable impact.


Below is the overview page from the dashboard and more examples are included throughout the report. The entire interactive dashboard can be viewed [here](https://birth-outcomes-lab.base44.app)


<img src="Screenshot%202026-02-18%20at%2011.26.04%20PM.png" alt="Prenatal Care Analysis" width="700" />


### **Gestational Age and Maternal Education**
 
Mean gestational age varies modestly by education level. Mothers with higher educational attainment (bachelor’s and master’s degrees) exhibit slightly longer average gestations, while lower education and “unknown/not stated” categories show shorter averages. Importantly, education alone does not fully explain observed differences, indicating the need to examine interactions with prenatal care timing and region.

### **Regional Differences**
 
Baseline gestational age differs across U.S. regions, with the South consistently exhibiting shorter average gestational age compared to other regions. These differences are evident even before accounting for prenatal care timing, justifying regional stratification in subsequent analyses.

#### **Baseline Population Stability: Low Structural Variance Before Stratification**

<img src="Screenshot%202026-02-18%20at%205.14.19%20PM.png" alt="Mean Gestation" width="650" />


## **Core Analytical Findings**

 ### **Prenatal Care Timing: Main Association**
 
When examined in isolation, prenatal care timing does not show a simple linear relationship with gestational age. In some unadjusted comparisons, delayed care appears associated with slightly longer gestation. However, this pattern reflects confounding by indication high-risk pregnancies often initiate care earlier and are more likely to deliver preterm.
Crucially, absence of prenatal care is associated with the shortest gestational ages across all regions, representing a clinically meaningful reduction of approximately 2–3 weeks.

#### **Delayed Prenatal Care Increases Birth Timing Variability Not Just Earlier Delivery**


<img width="500" height="500" alt="image" src="https://github.com/user-attachments/assets/5ef6d640-ec6c-4cd7-86bb-b3c22794084f" />

 ### **Effect Modification by Maternal Education**
 
Stratified analyses reveal that the association between delayed prenatal care and gestational age varies substantially by education level:
In several education groups, delayed care is associated with statistically significant differences in gestational age.


One education group (high school graduate/GED) shows no significant association, highlighting heterogeneity rather than a uniform effect.


These mixed unadjusted results reinforce the importance of multivariable modeling.


Multivariable regression models with interaction terms confirm that maternal education significantly modifies the effect of delayed prenatal care, with delayed care associated with shorter gestational age in multiple education strata after adjustment.


#### **Lower Education Amplifies the Association Between Delayed Care and Earlier Delivery**


<img width="700" height="700" alt="image" src="https://github.com/user-attachments/assets/38368602-aab0-417d-a823-5c64e59d87f0" />

### **Regional Context Matters**
After adjusting for education, delayed prenatal care is associated with shorter gestational age in every U.S. Census region. The magnitude of this effect varies:

- Stronger associations in the South and Midwest


- Attenuated effects in the West


These findings suggest that regional healthcare infrastructure, access, and policy environments influence how prenatal care timing translates into outcomes.

#### **Southern and Midwestern Regions Exhibit Stronger Negative Associations Between Delayed Care and Gestational Age**


<img width="650" height="650" alt="image" src="https://github.com/user-attachments/assets/d47124ec-68f6-4ccd-a21b-cbcf981b7285" />


Race
...

# Recommendations

- ## Policy and Practice Recommendations

Healthcare systems and public health programs should:


- **Prioritize Early Prenatal Care Outreach**

Focus on lower-education mothers in the South and Midwest, where delayed care shows the strongest association with shorter gestational age.

- **Develop Culturally Tailored Programs**

Create prenatal outreach programs for Black mothers, particularly in regions where gestational age remains low even among college-educated individuals.

- **Improve Data Completeness**

Enhance maternal education and prenatal care timing data collection, as poorer outcomes among mothers with 'Unknown' education suggest missing data disproportionately represents high-risk populations.

- **Conduct Mixed-Methods Studies**

Investigate structural barriers (transportation, provider availability) in the South and Midwest contributing to stronger delayed-care effects.


# Next Steps

- Drive Equitable Prenatal Care Through Targeted, Evidence-Based Actions.

- Combine early care prioritization, tailored outreach, data improvements, and structural reforms.

- Engage policymakers, healthcare providers, and communities.

- Aim for sustainable, measurable improvements in maternal and infant health.













