# Analyzing Student's Mental Health  

![Student Mental Health](https://github.com/ch-garcia/01-datacamp-sql-students-mentalhealth/blob/main/mentalhealth.jpg)

## Project Overview

Does going to university in a different country affect your mental health? A Japanese international university surveyed its students in 2018 and published a study the following year that was approved by several ethical and regulatory boards.

The study found that international students have a higher risk of mental health difficulties than the general population, and that social connectedness (belonging to a social group) and acculturative stress (stress associated with joining a new culture) are predictive of depression.

Explore the students data using PostgreSQL to find out if you would come to a similar conclusion for international students and see if the length of stay is a contributing factor.

| Field Name    | Description                                      |
| ------------- | ------------------------------------------------ |
| `inter_dom`     | Types of students (international or domestic)   |
| `japanese_cate` | Japanese language proficiency                    |
| `english_cate`  | English language proficiency                     |
| `academic`      | Current academic level (undergraduate or graduate) |
| `age`           | Current age of student                           |
| `stay`          | Current length of stay in years                  |
| `todep`         | Total score of depression (PHQ-9 test)           |
| `tosc`          | Total score of social connectedness (SCS test)   |
| `toas`          | Total score of acculturative stress (ASISS test) |

## Repository Files

- `students.csv` - The dataset used for this analysis.

- `notebook.ipynb` - My completed notebook from DataCamp.

## Project Instructions

Explore and analyze the `students` data to see how the length of stay (`stay`) impacts the average mental health diagnostic scores of the **international** students present in the study.

Return a table with **nine** rows and **five** columns.

The five columns should be aliased as: `stay`, `count_int`, `average_phq`, `average_scs`, and `average_as`, **in that order**.

The average columns should contain the average of the `todep` (PHQ-9 test), `tosc` (SCS test), and `toas` (ASISS test) columns for each length of stay, **rounded to two decimal places**.

The `count_int` column should be the number of international students for each length of stay.

Sort the results by the length of stay in **descending order**.

Note: Creating new cells in the workbook will rename the DataFrame. Make sure that your final solution uses the name `df`.

## Code Overview

```sql
SELECT
	stay,
	COUNT(*) AS count_int,
	ROUND(AVG(todep),2) AS average_phq,
	ROUND(AVG(tosc),2) AS average_scs,
	ROUND(AVG(toas),2) AS average_as
FROM students
WHERE inter_dom = 'Inter'
GROUP BY stay
ORDER BY stay DESC;
```

## About the Project

This is the 1st SQL project in the SQL Skill Track from DataCamp.

Visit [DataCamp](https://www.datacamp.com/).
