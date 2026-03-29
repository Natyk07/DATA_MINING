# Synthetic Dataset - University Dropout

## Variable Description
| Variable | Type | Description | Range / Values |
|----------|------|-------------|----------------|
| age | numeric | Student's age | 17-25 years (outliers: 40) |
| gender | categorical | Gender | Male, Female, Other |
| place_of_origin | categorical | Origin area | Urban, Rural |
| high_school_gpa | numeric | High school average (0-100) | 5% nulls |
| admission_score | numeric | Admission test score (0-100) | 3% nulls |
| first_semester_gpa | numeric | First semester average (0-100) | 2% nulls, outliers 0 and 100 |
| socioeconomic_level | categorical | Socioeconomic level | Low, Medium, High |
| scholarship | categorical | Has scholarship | Yes, No |
| loan | categorical | Has educational loan | Yes, No |
| financial_aid | categorical | Receives financial aid | Yes, No |
| dropout | categorical | Target variable: did the student drop out? | Yes, No |

## Null Values Introduction
- `high_school_gpa`: 5% of records randomly set to NaN.
- `admission_score`: 3% of records randomly set to NaN.
- `first_semester_gpa`: 2% of records randomly set to NaN.

## Outliers Introduction
- `age`: 2% of records set to 40 (above typical range).
- `first_semester_gpa`: 1% set to 0 and 1% set to 100.

## Target Variable Logic
Dropout probability was defined with a base of 10%, increased by:
- First semester GPA < 50 → +40%
- High school GPA < 55 → +20%
- Low socioeconomic level and no scholarship → +20%
- No financial aid → +10%