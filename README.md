# Students' Mental Health SQL Analysis

A small SQL analysis project exploring how length of stay relates to mental-health scores for international students. The repository contains one query that groups international students by stay duration and calculates average PHQ-9, SCS, and ASISS scores.

## Project Status

This is a compact SQL learning project. It is useful for showing aggregation, filtering, and query readability, but it is not a full application.

## Tech Stack

- SQL
- SQLite, MySQL, or PostgreSQL-compatible concepts

## Features

- Filters international students only
- Groups records by length of stay
- Counts students in each stay group
- Calculates rounded average diagnostic scores
- Sorts results by stay duration in descending order

## SQL Query

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
```

## Project Structure

```text
.
|-- query.sql
`-- README.md
```

## How to Use

Run `query.sql` against a database that contains a `students` table with the expected columns: `stay`, `inter_dom`, `todep`, `tosc`, and `toas`.

## Learning Focus

- Filtering rows with `WHERE`
- Aggregating grouped records with `COUNT` and `AVG`
- Rounding numeric outputs
- Writing readable SQL aliases

## License

No license file has been added yet.
