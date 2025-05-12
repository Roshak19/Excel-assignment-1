# Employee Work Productivity Analysis

This project analyzes employee productivity using Excel functions and visualizations. The objective is to identify high-performing employees, analyze department-wise consistency, and derive actionable insights from the dataset.

📊 **Dataset Source**: [Google Sheets Dataset](https://docs.google.com/spreadsheets/d/1BIBEB_GRlxxK8t0klT3kQPUWqZRsOsuY_SIbRSRavc8/edit?usp=sharing)

## 📁 Files Included
- `excel assignment.xlsx` – Contains the completed analysis and visualizations.
- `67f8fef7f4e1d248a7ca3393.pdf` – Original assignment questions.
- `README.md` – Project documentation and answers to the assignment.

---

## ✅ Assignment Tasks & Answers

### 1. **Top 5 Productive Employees**
- **Method**: Used `SORT` and `FILTER` functions on the `Productivity_Score` column.
- **Visualization**: Created a bar chart to display the top 5 employees with the highest scores.

```excel
=SORT(FILTER($A$2:$G$26,$F$2:$F$26>MIN(LARGE(F2:F26,5))),6,-1)
![Screenshot 2025-05-12 065154](https://github.com/user-attachments/assets/da878176-b50f-4777-ade3-027b0f7263ae)


---

### 2. **Department-Wise Productivity Consistency**
- **Goal**: Identify department with least variation.
- **Method**: Created a PivotTable and used `STDEV.P` on `Productivity_Score` grouped by `Department`.

```excel
=STDEV.P(range)

- **Result**: Department with the lowest standard deviation: **Marketing**
![Screenshot 2025-05-12 065324](https://github.com/user-attachments/assets/132de993-c929-47d9-a9e2-3153ef6b9634)

---

### 3. **Productivity Efficiency Index (PEI)**
- **Formula**:

```excel
= (Productivity_Score * Performance_Rating) / Hours_Worked
```

- **Task**: Added PEI column, then sorted and ranked employees.
- **Top 3 PEI Employees**: Identified using `RANK`, `SORT`, and/or `FILTER`.

  ![Screenshot 2025-05-12 065449](https://github.com/user-attachments/assets/d52e31cb-1333-4b9f-966f-907db9d33d76)


---

### 4. **Correlation Analysis**

#### Q1: What influences performance more — Hours Worked or Tasks Completed?
- **Method**: Used `CORREL` function:
```excel
==-CORREL('Productive employees'!$D$2:$D$26,'Productive employees'!$G$2:$G$26)  // Hours_Worked vs Performance_Rating
==CORREL('Productive employees'!E$2:E$26,'Productive employees'!$G$2:$G$26)  // Tasks_Completed vs Performance_Rating
```
![Screenshot 2025-05-12 065841](https://github.com/user-attachments/assets/5039b5a6-a43a-471f-a3a2-8ef6e4dd128b)

- **Conclusion**: Tasks_Completed vs Performance_Rating correlation was stronger based on values

#### Q2: Work Hours and Productivity Correlation
- **Method**: Created a scatter plot of `Hours_Worked` vs `Productivity_Score`.
- **Observation**: the correlation was positive

![Screenshot 2025-05-12 065852](https://github.com/user-attachments/assets/772fd6ac-7c8f-41a3-ab46-9a4c71ddf381)

---

### 5. **Underutilized High Performers**
- **Criteria**:
  - Performance Rating ≥ 4
  - Hours Worked < Average Hours

- **Method**:

```excel
=FILTER($A$2:$G$26,($G$2:$G$26>=4)*($D$2:$D$26<AVERAGE($D$2:$D$26)))
```
![Screenshot 2025-05-12 070125](https://github.com/user-attachments/assets/55840b88-e8ca-4f96-824a-ceb142739dc2)

- **Insight**: Employees identified here are efficient but potentially underutilized.

---

### 6. **Tasks per Hour Efficiency**
- **Formula**:

```excel
= Tasks_Completed / Hours_Worked
```

- **Method**: Created a new column `Tasks_per_Hour`, found the highest value using:

```excel
**Using Index/Match**  =INDEX($A$2:$H$26,MATCH(MAX($H$2:$H$26),$H$2:$H$26,0),{1,2,3,4,5,6,7,8})
**Using Xlookup**      =XLOOKUP(MAX($H$2:$H$26),$H$2:$H$26,$A$2:$H$26,,0)
```
![Screenshot 2025-05-12 070520](https://github.com/user-attachments/assets/94d55fec-5d65-4d07-ac30-1942b5020621)

- **Result**: Most task-efficient employee: **Arjun** from **Marketing**.

---

## 📌 Conclusion

This Excel-based analysis provides insights into employee productivity patterns, high performers, department consistencies, and underutilized talent. The use of Excel functions like `SORT`, `FILTER`, `CORREL`, and PivotTables enabled comprehensive evaluation.

---

## 📎 Tools Used
- Microsoft Excel
- Basic Statistics & Data Analysis
- Data Visualization (Bar charts, Scatter plots)
