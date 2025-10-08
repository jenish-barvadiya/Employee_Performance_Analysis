# Employee_Performance_Analysis

#  Data Overview – INX Future Inc Employee Performance Dataset

## Business Case:-

* INX Future Inc. is a growing analytics-driven company that believes its employees are the backbone of success. With a diverse workforce across multiple departments, management has observed varying levels of employee performance. To stay competitive and ensure long-term growth, the company needs to understand what drives employee performance and how it can proactively manage talent.

1. **Dataset Size**

   * Number of rows (employees): `N`
   * Number of columns (features): `M`

2. **Feature Types**

   * **Categorical Features:** e.g., `Employee_ID`, `Dept`, `EducationBackground`, `Gender`, `JobRole`, `MaritalStatus`
   * **Numerical Features:** e.g., `Age`, `Experience`, `TrainingHours`, `PreviousYearRating`, `Attrition_rate`
   * **Target Variable:** `Attrition` (YES \ NO)

3. **Missing Values**

   * Some columns may have missing entries (e.g., `Experience`, `PreviousYearRating`).
   * Handling will be required using imputation or removal.

4. **Sample Columns (Common in this dataset version)**

   * `EmpNumber`: Unique ID for each employee
   * `Age`: Age of the employee
   * `Gender`: Male/Female
   * `EducationBackground`: Field of education
   * `Dept`: Department name
   * `JobRole`: Specific role/designation
   * `Experience`: Total years of experience
   * `TrainingHours`: Number of training hours completed
   * `PreviousYearRating`: Rating from previous year
   * `Awards`: Number of awards received
   * `PerformanceRating`: Current year performance (Target)

5. **Data Characteristics**

   * Combination of **demographics, job-related, and performance-related attributes**.
   * Suitable for **EDA** (to find patterns) and **Predictive Modeling** (classification).
  


  # Final Report: Employee Attrition Analysis

## 1. Business Case & Objective
The organization aims to understand the factors influencing **employee attrition** (whether an employee stays or leaves).  
High attrition can cause:
- Increased recruitment and training costs,
- Loss of experienced talent,
- Reduced employee morale and productivity.

The objective of this analysis is:
- To explore employee demographics and work-related factors,
- To identify key drivers of attrition,
- To recommend data-driven HR policies to improve retention.

---

## 2. Data Overview
Dataset: **INX Future Inc Employee Performance Data**

- **Rows (Employees):** ~1470  
- **Columns (Features):** 35+ (including demographic, job role, income, work experience, satisfaction levels, and attrition status).  
- **Target Variable:** `Attrition` (Yes / No)

---

## 3. Key Insights from Exploratory Data Analysis (EDA)

### Categorical Features
- **Gender:** ~65% Male, ~35% Female → gender imbalance.  
- **Education:** Majority from **Life Sciences (500)** and **Medical (380)** backgrounds.  
- **Department:** Most employees in **Research & Development (≈480)**, followed by **Sales (≈320)**.  
- **Business Travel:** ~70% travel rarely, ~20% frequently.  
- **OverTime:** ~28% of employees work overtime.  
- **Attrition:** ~200 employees (≈17%) have left → **class imbalance** in target variable.

### Numerical Features
- **Age:** Most employees are between **30–40 years**.  
- **Distance From Home:** Right-skewed; majority live within **0–10 km**.  
- **Monthly Income:** Right-skewed; most earn **2k–8k**, a few senior staff earn >15k.  
- **Years at Company:** Majority have **<10 years of tenure**, fewer are long-tenured.  
- **Years Since Last Promotion:** Most promoted **1–3 years ago**; few haven’t been promoted for >10 years.  
- **Performance Rating & Employee Ratio:** Very low variance → less useful for prediction.

---

## 4. Problems Faced
1. **Data Imbalance**
   - Attrition classes are imbalanced (Yes ≈17%, No ≈83%), making it harder for models to detect leavers.
   - Requires resampling techniques (e.g., **SMOTE, SMOTETomek**).

2. **Low-Variance Features**
   - Features like `EmployeeCount`, `PerformanceRating`, and `EmployeeNumber` add little predictive power and may be dropped.

3. **Skewed Distributions**
   - Many numerical variables (e.g., Monthly Income, DistanceFromHome) are right-skewed, requiring transformation or scaling.

4. **Correlations**
   - Some features are highly correlated (e.g., Monthly Income & Job Level), which could cause multicollinearity in models.

5. **Overfitting Risk**
   - With many categorical and numerical variables, models may overfit unless regularization or feature selection is applied.

---

## 5. Conclusion & Recommendations

### Conclusion
- **Key Attrition Drivers Identified:**
  - **OverTime:** Employees working overtime are at higher risk.  
  - **Business Travel:** Frequent travelers more prone to leave.  
  - **Tenure & Promotions:** Employees without recent promotions or new hires (<2 years) show higher attrition.  
  - **Job Role/Department:** Attrition is more critical in R&D due to workforce concentration.  

### Recommendations
1. **HR Policy Improvements**
   - Reduce excessive **overtime** to prevent burnout.  
   - Provide **career growth opportunities** (regular promotions & training).  
   - Monitor **frequent travelers** for stress and provide travel support.  
   - Improve **work-life balance policies** for high-risk groups.

2. **Diversity & Inclusion**
   - Encourage hiring of **female candidates** and employees from diverse educational backgrounds to balance workforce.

3. **Retention Strategy**
   - Focus retention efforts on **R&D employees** since they form the largest department.  
   - Use predictive modeling to **flag at-risk employees early** and conduct retention interviews.

4. **Data Science Applications**
   - Apply **resampling (SMOTE)** to handle class imbalance before modeling.  
   - Scale numerical features (`StandardScaler`) for algorithms like ANN/MLP.  
   - Use **GridSearchCV/RandomizedSearchCV** for hyperparameter tuning.

---

## Final Note
This analysis provides both **HR-level business insights** and a foundation for **predictive modeling**.  
By implementing these recommendations, the company can **reduce attrition**, **retain top talent**, and **lower HR costs**.
