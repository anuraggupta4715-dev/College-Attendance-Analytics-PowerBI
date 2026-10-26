# 📊 College Attendance Analytics Dashboard

### An Interactive Power BI Project

An interactive **College Attendance Analytics Dashboard** developed using Microsoft Power BI, Power Query, and DAX to analyse student attendance, monitor academic performance, and identify attendance shortages.

The project presents attendance insights through five dashboard pages: **Overall, Students, Subjects, Attendance, and Shortage**.

---

## 👨‍💻 Project Information

| Detail | Description |
|---|---|
| **Project Title** | College Attendance Analytics Dashboard |
| **Developed By** | Anurag Gupta |
| **Registration Number** | PIET24CD007 |
| **Institution** | Poornima Institute of Engineering & Technology (PIET) |
| **Visualization Tool** | Microsoft Power BI |
| **Data Preparation** | Power Query |
| **Calculations** | DAX |
| **Departments** | CSE, AI&DS, IoT |
| **Students** | 245 |
| **Subjects** | 10 |

## 📌 Project Overview

The College Attendance Analytics Dashboard transforms student attendance records into meaningful visual insights. It helps users explore attendance patterns across departments, academic years, individual students, and subjects.

The dashboard includes KPI cards, interactive slicers, charts, tables, attendance trends, and shortage analysis. It highlights students below the 75% attendance threshold and critical cases below 65%, helping identify areas that may require attention.

## 🎯 Objectives

- Monitor overall student attendance.
- Analyse attendance across academic years and departments.
- Compare attendance performance across subjects.
- Identify students with attendance below 75%.
- Highlight critical attendance cases below 65%.
- Analyse present and absent attendance records.
- Examine attendance shortages and additional classes required to reach the target.
- Present attendance data through interactive visualizations and filters.

## 🛠️ Technologies Used

- **Microsoft Power BI Desktop** — Dashboard creation and data visualization.
- **Power Query** — Data import and transformation.
- **DAX (Data Analysis Expressions)** — Measures and attendance calculations.
- **Microsoft Excel** — Dataset storage and input.

## 📂 Repository Structure

```text
College-Attendance-Analytics-PowerBI/
│
├── Dataset/
│   └── Attendance_Analytics_PowerBI.xlsx
│
├── PowerBI/
│   └── ANURAG_GUPTA_PBI.pbix
│
├── Report/
│   └── College_Attendance_Analytics_Project_Report_Anurag_Gupta.pdf
│
├── Screenshots/
│   ├── overall_dashboard.png
│   ├── students_dashboard.png
│   ├── subjects_dashboard.png
│   ├── attendance_dashboard.png
│   └── shortage_dashboard.png
│
├── README.md
└── LICENSE
```

## 📸 Dashboard Previews

### 1. Overall Dashboard

Provides a summary of attendance performance through key metrics and visualizations.

**Highlights:**
- Total Students
- Overall Attendance
- Students Below 75%
- Critical Subjects
- Students by Academic Year
- Attendance by Department
- Attendance Trends
- Attendance Category Distribution
- Attendance by Subject

![Overall Dashboard](Screenshots/overall_dashboard.png)

### 2. Students Dashboard

Focuses on student demographics and individual attendance performance.

**Highlights:**
- Total Students
- Male and Female Students
- Average Attendance
- Students Below 75%
- Students by Academic Year
- Students by Department
- Gender Distribution
- Student Attendance Distribution
- Lowest-Attendance Student Table

![Students Dashboard](Screenshots/students_dashboard.png)

### 3. Subjects Dashboard

Provides subject-level attendance analysis and identifies subjects requiring attention.

**Highlights:**
- Total Subjects
- Theory Subjects
- Practical Subjects
- Average Attendance
- Critical Subjects
- Attendance by Subject
- Subject Attendance Heatmap
- Subject-wise Student Count Below 75%
- Critical Subjects Table

![Subjects Dashboard](Screenshots/subjects_dashboard.png)

### 4. Attendance Dashboard

Analyses attendance records and trends across the selected date range.

**Highlights:**
- Total Classes
- Total Present Records
- Total Absent Records
- Present Percentage
- Absent Percentage
- Daily Attendance Trend
- Weekly Attendance Heatmap
- Monthly Attendance Trend
- Attendance by Department
- Students by Academic Year

![Attendance Dashboard](Screenshots/attendance_dashboard.png)

### 5. Shortage Dashboard

Focuses on attendance risk, critical cases, and shortage analysis.

**Highlights:**
- Students Below 75%
- Critical Students Below 65%
- Average Additional Classes Required
- Total Subjects at Risk
- Percentage of Students at Risk
- Shortage Distribution
- Students by Shortage Category
- Shortage Trend
- Top 5 Students with Highest Shortage
- Subject-wise Shortage Analysis

![Shortage Dashboard](Screenshots/shortage_dashboard.png)

## 🧮 Key DAX Measures

### 1. Overall Attendance %

```dax
Overall Attendance % =
DIVIDE(
    SUM(FactAttendance[PresentFlag]),
    COUNTROWS(FactAttendance),
    0
)
```

Calculates the proportion of present attendance records in the current filter context.

### 2. Total Students

```dax
Total Students =
DISTINCTCOUNT(DimStudent[StudentID])
```

Counts distinct student IDs.

### 3. Students Below 75%

```dax
Students Below 75% =
COUNTROWS(
    FILTER(
        VALUES(DimStudent[StudentID]),
        CALCULATE([Overall Attendance %]) < 0.75
    )
)
```

Counts students whose calculated attendance percentage is below 75%.

### 4. Critical Students

```dax
Critical Students =
COUNTROWS(
    FILTER(
        VALUES(DimStudent[StudentID]),
        CALCULATE([Overall Attendance %]) < 0.65
    )
)
```

Counts students whose calculated attendance percentage is below 65%.

### 5. Total Classes

```dax
Total Classes =
COUNTROWS(
    SUMMARIZE(
        FactAttendance,
        FactAttendance[SessionDate],
        FactAttendance[SessionNumber]
    )
)
```

Counts unique combinations of session date and session number in the current filter context.

**Note:** Unique class sessions and student attendance records are different metrics. A single class session can contain attendance records for multiple students.

### 6. Percentage of Students at Risk

```dax
Percentage of Students at Risk =
DIVIDE([Students Below 75%], [Total Students], 0)
```

Calculates the proportion of students below 75% attendance.

## 📈 Key Findings

Based on the supplied dashboard screenshots:

- The Overall dashboard displays **245 students**.
- Overall attendance is displayed as **81.3%** on the Overall dashboard.
- **58 students below 75% attendance** are displayed on the Overall dashboard.
- The Overall dashboard displays **9 critical subjects**.
- The project covers **10 subjects**, comprising 6 theory subjects and 4 practical/lab subjects.
- The Subjects dashboard highlights PDS and DVR in its critical-subject table.
- The Attendance dashboard displays approximately 65K attendance records, including around 53K present records and 12K absent records.

Displayed values can vary with the selected filters and calculation context.

## 🚀 How to Run the Project

1. Clone or download this repository.
2. Install or open **Microsoft Power BI Desktop**.
3. Open `PowerBI/ANURAG_GUPTA_PBI.pbix`.
4. If Power BI requests the source file, locate `Dataset/Attendance_Analytics_PowerBI.xlsx` and update the data source path if necessary.
5. Refresh the data if the source is available.
6. Navigate through the five dashboard pages and explore the available slicers and visualizations.

## 📁 Project Resources

- **[Power BI Dashboard](PowerBI/ANURAG_GUPTA_PBI.pbix)** — Interactive report.
- **[Excel Dataset](Dataset/Attendance_Analytics_PowerBI.xlsx)** — Dataset used by the project.
- **[Project Report PDF](Report/College_Attendance_Analytics_Project_Report_Anurag_Gupta.pdf)** — Project documentation.
- **[Dashboard Screenshots](Screenshots/)** — Images of the five dashboard pages.

## 🎓 Learning Outcomes

This project demonstrates practical experience with:

- Data preparation using Power Query.
- DAX measures and attendance calculations.
- KPI cards and interactive data visualization.
- Student, department, and subject-level analysis.
- Attendance shortage and risk analysis.
- Multi-page dashboard design in Power BI.

## 👤 Author

**Anurag Gupta**  
Registration Number: `PIET24CD007`  
Poornima Institute of Engineering & Technology (PIET)

## 📄 License

This repository includes an MIT License. Refer to the [`LICENSE`](LICENSE) file for details.

---

⭐ If you find this project useful for learning Power BI and attendance analytics, consider giving this repository a star.
