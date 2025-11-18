# 🧠 Students' Mental Health – SQL Analysis

This project analyzes how the **length of stay** impacts the **mental health scores** (PHQ-9, SCS, ASISS) of international students.

## 📌 What the project is
A SQL-based analysis that groups international students by length of stay and calculates:
- Count of international students  
- Average PHQ-9 score (todep)  
- Average SCS score (tosc)  
- Average ASISS score (toas)

## 🛠 Tech Stack
- SQL  
- SQLite / MySQL / PostgreSQL (depending on your environment)

## ✨ Features
- Filtering international students only  
- Aggregation by stay levels  
- Rounded diagnostic score averages  
- Results sorted descending by stay duration  

## 🔍 The SQL Query

```sql
SELECT
  stay,
  COUNT(*)                     AS count_int,
  ROUND(AVG(todep), 2)         AS average_phq,
  ROUND(AVG(tosc), 2)          AS average_scs,
  ROUND(AVG(toas), 2)          AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
