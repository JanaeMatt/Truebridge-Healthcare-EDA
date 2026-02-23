# Truebridge-Healthcare-EDA
This project analyzes how prenatal care timing, maternal education, race/ethnicity, and U.S. Census region are associated with gestational age at birth.


# Project Background

Gestational age at birth is one of the most critical predictors of infant health. Preterm birth is associated with increased risks of respiratory complications, developmental delays, and long-term morbidity. Despite advances in obstetric care, substantial disparities in birth outcomes persist across socioeconomic and geographic lines in the United States.
Early prenatal care is widely regarded as a protective factor; however, access to and utilization of prenatal services vary considerably depending on maternal education, region, and broader social determinants of health (SDOH). Importantly, many prior studies focus on average effects, overlooking how social context may modify the relationship between prenatal care and birth outcomes.
This analysis addresses that gap by examining who is most affected when prenatal care is delayed, rather than assuming uniform effects across populations.

Insights and recommendations are based on the following areas
Demographic stratification
Effect modification
Geographic context
Risk interpretation
Policy implications

An interactive dashboard can be downloaded [here](https://birth-outcomes-lab.base44.app)



The python code utilized to clean, organize, and prepare data for analysis can be found here

Raw dataset

The slideshow presentation for this analysis can be found [here](https://docs.google.com/presentation/d/172dNhzClbHkm6S5NZ6ZgezhJBNB9bon05y44OQYIPEY/edit?usp=sharing)

 # Data Structure
 Thee dataset used consist of 6 tables; birth record, census region, prenatal care, mother's education, mother's race, and year.
 
<img width="885" height="570" alt="image" src="https://github.com/user-attachments/assets/f34dc937-bd62-4b23-92a8-1b93cb7d6166" />

Prior to the beginning of analysis, a variety of checks were conducted for quality control within the dataset. Python was utilized to inspect and control quality checks and can be found HERE.


 

 # Executive Summary

 Overall, while average gestational age remains stable across social groups, delayed prenatal care introduces meaningful risk through increased variability especially among structurally disadvantaged populations and regions with limited healthcare access.
Who should care and why:
Health systems, Medicaid programs, and public health agencies because delayed prenatal care acts as an early warning signal for concentrated risk especially in underserved populations and regions with limited access to obstetric care.


Below is the overviw page from the dashboard and more examples are included throughout the report. The entire interactive dashboard can be viewed [here](https://birth-outcomes-lab.base44.app)


![Prenatal Care Analysis](Screenshot%202026-02-18%20at%2011.26.04%20PM.png)


### **Gestational Age and Maternal Education**
 
Mean gestational age varies modestly by education level. Mothers with higher educational attainment (bachelor’s and master’s degrees) exhibit slightly longer average gestations, while lower education and “unknown/not stated” categories show shorter averages. Importantly, education alone does not fully explain observed differences, indicating the need to examine interactions with prenatal care timing and region.

### **Regional Differences**
 
Baseline gestational age differs across U.S. regions, with the South consistently exhibiting shorter average gestational age compared to other regions. These differences are evident even before accounting for prenatal care timing, justifying regional stratification in subsequent analyses.

#### **Baseline Population Stability: Low Structural Variance Before Stratification**

![Mean Gestation](Screenshot%202026-02-18%20at%205.14.19%20PM.png)

## **Core Analytical Findings**

 ### **Prenatal Care Timing: Main Association**
 
When examined in isolation, prenatal care timing does not show a simple linear relationship with gestational age. In some unadjusted comparisons, delayed care appears associated with slightly longer gestation. However, this pattern reflects confounding by indication high-risk pregnancies often initiate care earlier and are more likely to deliver preterm.
Crucially, absence of prenatal care is associated with the shortest gestational ages across all regions, representing a clinically meaningful reduction of approximately 2–3 weeks.

#### **Delayed Prenatal Care Increases Birth Timing Variability Not Just Earlier Delivery**


<img width="1117" height="679" alt="image" src="https://github.com/user-attachments/assets/5ef6d640-ec6c-4cd7-86bb-b3c22794084f" />

 ### **Effect Modification by Maternal Education**
 
Stratified analyses reveal that the association between delayed prenatal care and gestational age varies substantially by education level:
In several education groups, delayed care is associated with statistically significant differences in gestational age.


One education group (high school graduate/GED) shows no significant association, highlighting heterogeneity rather than a uniform effect.


These mixed unadjusted results reinforce the importance of multivariable modeling.


Multivariable regression models with interaction terms confirm that maternal education significantly modifies the effect of delayed prenatal care, with delayed care associated with shorter gestational age in multiple education strata after adjustment.


#### **Lower Education Amplifies the Association Between Delayed Care and Earlier Delivery**


<img width="1124" height="616" alt="image" src="https://github.com/user-attachments/assets/38368602-aab0-417d-a823-5c64e59d87f0" />

### **Regional Context Matters**
After adjusting for education, delayed prenatal care is associated with shorter gestational age in every U.S. Census region. The magnitude of this effect varies:

- Stronger associations in the South and Midwest


- Attenuated effects in the West


These findings suggest that regional healthcare infrastructure, access, and policy environments influence how prenatal care timing translates into outcomes.

#### **Southern and Midwestern Regions Exhibit Stronger Negative Associations Between Delayed Care and Gestational Age**


<img width="1121" height="662" alt="image" src="https://github.com/user-attachments/assets/d47124ec-68f6-4ccd-a21b-cbcf981b7285" />


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













