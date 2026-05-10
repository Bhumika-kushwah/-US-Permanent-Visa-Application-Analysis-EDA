# 🇺🇸 US Permanent Visa Application Analysis – EDA

## 🔍 Project Overview
This project focuses on performing Exploratory Data Analysis (EDA) on US Permanent Visa application data to uncover trends related to visa approvals, denials, employers, job titles, countries of citizenship, and economic sectors.

The goal of this analysis is to understand the factors associated with US visa applications and prepare the dataset for future machine learning classification models.

---

## 📁 Dataset Information
- Source: Kaggle – us_perm_visas.csv  
- Total Raw Records: 374,362 applications  
- Records After Cleaning: ~367,000 applications  

### Target Variable
- Certified (Approved Visa)  
- Denied (Rejected Visa)  

### Key Features Used
- case_status  
- decision_date  
- employer_name  
- employer_city  
- employer_state  
- job_info_job_title  
- country_of_citizenship  
- us_economic_sector  
- class_of_admission  
- foreign_worker_info_education  
- pw_soc_code  
- pw_amount_9089  

- Dataset Type: Mixed (Numerical + Text/Categorical)  
- Nature: Large-scale real-world immigration dataset  

---

## 🧹 Data Cleaning & Feature Engineering

### 🔢 Merged Duplicate Columns
Merged:
```python
case_no + case_number
```

into a single unified column.

### 🎯 Cleaned Target Variable
- Removed:
```python
Withdrawn
```

- Merged:
```python
Certified-Expired → Certified
```

Final encoding:
```python
Certified = 1
Denied = 0
```

### 📅 Datetime Processing
Used:
```python
pd.to_datetime()
```

to extract:
- Year  
- Month  
- Day  

from the decision_date column.

### 💼 Job Title Standardization
Applied extensive string preprocessing:
- Lowercasing  
- Removing suffixes  
- Splitting titles  
- Cleaning spaces & symbols  

Example:
```python
"SOFTWARE ENGINEER - III"
"Sr. Software Engineer"
```

→ standardized into clean categories.

### 🏙️ City & State Cleaning
- Converted city names to uppercase  
- Standardized state names  
- Handled missing values using mode imputation  

### 💰 Salary & SOC Code Cleaning
- Removed commas & symbols from salary columns  
- Converted SOC codes into clean numerical format  

### 🤖 ML Preprocessing
Applied:
```python
LabelEncoder
```

to categorical variables for ML readiness.

---

## 📊 Exploratory Data Analysis

### 🔹 Univariate Analysis
- Visa approval distribution  
- Country-wise applications  
- Education level distribution  

### 🔹 Bivariate Analysis
- Employer vs Applications  
- Job Title vs Approval Trends  
- Sector vs Application Volume  

### 🔹 Multivariate Analysis
- Year-wise trends  
- Economic sector analysis  
- Employer city analysis  

---

## 📌 Key Insights

### ✅ Visa Approval Analysis
- 92.8% applications were certified  
- Only 7.2% applications were denied  

⚠️ Strong class imbalance observed.

### 📈 Application Trends
- Applications increased steadily from 2008 → 2016  
- 2016 recorded the highest visa volume  

### 💻 Technology Sector Dominance
- 52.4% applications came from Computer & Math sector  
- Software Engineer was the most common job title  

### 🏢 Top Sponsoring Employers
Top companies:
- Infosys  
- Wipro  
- TCS  
- Cognizant  
- HCL  

### 🌏 Country-Wise Analysis
Top applicant countries:
1. India  
2. China  
3. South Korea  

India alone contributed 45%+ of applications.

### 🎓 Education Analysis
Most applicants had:
- Bachelor’s Degree  
- Master’s Degree  

indicating a highly skilled applicant pool.

### 🔗 Job Title Engineering
String preprocessing significantly improved grouping accuracy for job title analysis.

---

## 💡 Key Learnings

- Real-world datasets require heavy text preprocessing  
- Feature engineering is essential for meaningful analysis  
- Target variables often need cleaning before modeling  
- Class imbalance must be handled carefully in ML workflows  
- EDA helps uncover hidden workforce and immigration patterns  

---

## 🛠️ Tools & Technologies Used
- Python  
- Pandas  
- NumPy  
- Matplotlib  
- Seaborn  
- Scikit-learn  


Examples:
- Visa Approval Distribution  
- Country-wise Applications  
- Top Employers Analysis  
- Job Title Distribution  
- Economic Sector Pie Chart  

---

## 🚀 How to Run the Project

### 1️⃣ Clone the Repository
```bash
git clone https://github.com/your-username/us-visa-eda.git
```

### 2️⃣ Install Required Libraries
```bash
pip install pandas numpy matplotlib seaborn scikit-learn
```

### 3️⃣ Run Jupyter Notebook
```bash
jupyter notebook
```

---

## 📌 Project Status
✅ Completed  
🔄 Open for improvements and feedback  

---

## 🤝 Connect With Me
I’m currently learning Data Analytics and building real-world projects.


## ⭐ If You Found This Useful
Give this repository a star ⭐ and share your feedback!
