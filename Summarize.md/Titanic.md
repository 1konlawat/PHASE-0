

# 🛳️ Titanic Survival Analysis (Mini Project)
### Exploratory Data Analysis (EDA) using Python

This project analyzes the famous Titanic dataset to find patterns related to passenger survival rates.  
It is part of Phase 0 learning for Data Science & Machine Learning roadmap.

---

## 📊 Objectives / วัตถุประสงค์
- Perform data cleaning and preprocessing  
- Explore relationships between features and survival rate  
- Visualize key findings  
- Practice Python, Pandas, and Matplotlib for real-world data analysis

---

## 📁 Dataset / ข้อมูลที่ใช้
**File:** `titanic.csv`  
Contains passenger information such as:
- `Pclass` – Passenger class (1 = First, 3 = Third)
- `Sex` – Gender
- `Age` – Age of passenger
- `Fare` – Ticket price
- `Survived` – Survival status (1 = Survived, 0 = Not survived)

---

## ⚙️ Steps / ขั้นตอนที่ทำ
1. **Data Cleaning**  
   - Filled missing `Age` and `Fare` with mean values  
   - Checked column info and datatypes  

2. **Exploratory Analysis**  
   - Survival rate by class and gender  
   - Average age by passenger class  
   - Survival rate by age group  
   - Survival rate by fare group (Low / Medium / High / VIP)  
   - Survival rate by embarkation port (C, Q, S)  
   - Extracted title from names (Mr., Mrs., Miss, etc.) to analyze survival rate

3. **Visualization**  
   - Used `matplotlib` and `seaborn` for bar charts, line plots, and scatter plots  

---

## 📈 Example Insights / ผลการวิเคราะห์
- **Female passengers** had a much higher survival rate than males  
- **1st class passengers** survived more often than 3rd class  
- **Children** (under 10 years old) had the highest survival rate  
- **Higher fare tickets** correlated with higher survival chances  
- **Titles like “Mrs.” and “Miss”** had higher survival rates compared to “Mr.”

---

## 🧩 Libraries Used / ไลบรารีที่ใช้
```bash
pandas
numpy
matplotlib
seaborn
