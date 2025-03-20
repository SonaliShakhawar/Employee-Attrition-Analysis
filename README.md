# Employee Attrition Analysis - Power BI Project

## 📌 Project Overview
This Power BI project analyzes employee attrition at **Adecco India**, identifying key factors influencing employee turnover. The dashboard provides insights into attrition rates, department-wise trends, work-life balance, stock options, promotions, and more, helping HR teams make data-driven decisions.

---

## 🚀 Features
- **Overall Attrition Rate Calculation**
- **Department-wise Attrition Analysis**
- **Top Factors Contributing to Attrition**
- **Impact of Marital Status on Attrition**
- **Effect of Stock Options on Employee Retention**
- **Tenure vs. Job Satisfaction Correlation**
- **Promotion vs. Performance Rating Analysis**
- **Training and its Influence on Attrition**
- **Work-Life Balance vs. Employee Performance**
- **Interactive and User-Friendly Dashboard**

---

## 📂 Dataset Details
The dataset consists of employee records with the following key attributes:
- **Employee ID** (Unique identifier)
- **Age**
- **Gender**
- **Department**
- **Attrition (Yes/No)**
- **Monthly Income**
- **Years at Company**
- **Job Satisfaction (Scale 1-4)**
- **Work-Life Balance (Scale 1-4)**
- **Performance Rating (Scale 1-4)**
- **Stock Options (0-3)**
- **Training Times Last Year**
- **Years Since Last Promotion**

## 📊 Data Analysis & DAX Queries

### **1️⃣ Attrition Rate Calculation**
```DAX
EmployeesWhoLeft = COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Yes"))
TotalEmployees = COUNTROWS(EmployeeData)
AttritionRate = DIVIDE([EmployeesWhoLeft], [TotalEmployees]) * 100
```
**📌 Visualization:** Card Visual showing `Attrition Rate`.

---

### **2️⃣ Department-wise Attrition**
```DAX
AttritionRateByDept = DIVIDE(
    COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Yes")),
    COUNTROWS(EmployeeData)
) * 100
```
**📌 Visualization:** Bar Chart (`Department` vs. `Attrition Rate`).

---

### **3️⃣ Top 3 Factors Influencing Attrition**
Using **CORREL() function**, we identify the top factors affecting attrition:
- Age
- Monthly Income
- Years at Company

**📌 Visualization:** Table and Bar Chart showing correlation values.

---

### **4️⃣ Marital Status Impact on Attrition**
```DAX
AttritionByMaritalStatus =
    DIVIDE(
        COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Yes")),
        COUNTROWS(EmployeeData)
    ) * 100
```
**📌 Visualization:** Pie Chart comparing attrition by marital status.

---

### **5️⃣ Stock Options & Attrition**
```DAX
AttritionByStockOptions =
    DIVIDE(
        COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Yes")),
        COUNTROWS(EmployeeData)
    ) * 100
```
**📌 Visualization:** Bar Chart (`StockOptionLevel` vs. `Attrition Rate`).

---

### **6️⃣ Tenure & Job Satisfaction Correlation**
```DAX
AvgJobSatisfactionByTenure = AVERAGE(EmployeeData[JobSatisfaction])
```
**📌 Visualization:** Scatter Plot (`YearsAtCompany` vs. `JobSatisfaction`).

---

### **7️⃣ Promotions & Performance Ratings**
```DAX
AvgPerformanceByPromotion = AVERAGE(EmployeeData[PerformanceRating])
```
**📌 Visualization:** Scatter Plot (`YearsSinceLastPromotion` vs. `Performance Rating`).

---

### **8️⃣ Training & Attrition**
```DAX
AttritionByTraining =
    DIVIDE(
        COUNTROWS(FILTER(EmployeeData, EmployeeData[Attrition] = "Yes")),
        COUNTROWS(EmployeeData)
    ) * 100
```
**📌 Visualization:** Line Chart (`TrainingTimesLastYear` vs. `Attrition Rate`).

---

### **9️⃣ Work-Life Balance & Performance**
```DAX
AvgPerformanceByWorkLife = AVERAGE(EmployeeData[PerformanceRating])
```
**📌 Visualization:** Scatter Plot (`WorkLifeBalance` vs. `Performance Rating`).

---

## 📈 Final Dashboard
The final Power BI dashboard includes:
- **KPI Cards** for attrition rate.
- **Bar Charts** for department-wise attrition and stock options.
- **Scatter Plots** for tenure, job satisfaction, and promotions.
- **Pie Charts** for marital status impact.
- **Line Charts** for training trends.

---

## 📌 Future Enhancements
- Adding **Predictive Analytics** using **Power BI AI Insights**.
- Enhancing **UI/UX** for better interactivity.
- Integrating **Live Data Sources**.

---

## 🛠️ Tools & Technologies Used
- **Power BI Desktop** (Data Visualization)
- **DAX (Data Analysis Expressions)** (Data Modeling)
- **Excel/CSV** (Data Source)
