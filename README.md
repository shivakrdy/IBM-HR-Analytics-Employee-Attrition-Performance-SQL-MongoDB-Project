# IBM HR Analytics - Employee Attrition & Performance (SQL + MongoDB Project)

This project explores employee attrition and performance insights using structured and unstructured databases. It combines SQL-based relational modeling with MongoDB's flexible document-based analysis to derive key business intelligence for HR decision-making.

---

## Project Reports
All SQL queries, MongoDB queries, ER diagrams, assumptions, and detailed analysis are documented in the following PDF reports:

- Phase 1 Project.pdf
- Phase 2 Project.pdf

These PDFs serve as the final consolidated reports for the project, summarizing the entire data modeling, SQL coding, business logic, and MongoDB querying process.

⚠️ Note: SQL and MongoDB code are embedded within the PDFs. No separate .sql or .txt files have been uploaded.

---


## Project Overview

- **Course:** BUAN 6320 – Database Foundations  
- **Dataset:** IBM HR Analytics Employee Attrition & Performance  
- **Team:** Group 8  
- **Tools:** MySQL, MongoDB  
- **Focus:** Data modeling, analysis, normalization, and querying  

---

## Objectives

- Design a normalized database (3NF) using the IBM HR dataset
- Implement SQL queries to analyze attrition, job satisfaction, pay disparity, and more
- Use MongoDB aggregations to answer flexible business questions
- Extract HR insights to support decision-making

---

## Data Modeling

**Key Tables:**

- Lookup Tables:  
  `Gender`, `Education`, `Department`, `JobRole`, `MaritalStatus`, `BusinessTravel`,  
  `JobSatisfaction`, `WorkLifeBalance`, `PerformanceRating`, `EnvironmentSatisfaction`, `RelationshipSatisfaction`

- Fact Tables:  
  `Employee`, `Experience`, `JobReviewDetails`, `SalaryDetails`

**Normalization:**  
All tables are normalized to 3NF with label encoding for categorical values (e.g., education levels, departments, etc.)

---

## Sample SQL Queries

**Q: Which department has the shortest commute?**
```sql
SELECT d.DepartmentName, AVG(DistanceFromHome) AS AverageCommute
FROM employee e
JOIN department d ON d.DepartmentID = e.DepartmentID
GROUP BY d.DepartmentName
ORDER BY AverageCommute ASC;

