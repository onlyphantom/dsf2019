# Class Summary

## Background of R
Rules of R:
1. Case-sensitive
2. Items in the same vector have to share the same class

Classes in R:
1. Character
2. Numeric
3. Logical (T/F)
4. Integer
5. Complex

In Practice: We are not concerned with characters. We are interested in numeric values or factor values.

In Machine Learning, what we predict is either:
1. Numeric in value
    - Regression Problem 
2. Factor (Category)
    - Classification Problem

## Data Analysis Workflow

1. Goal is to understand your data, structure, and take a peek at your data

Taking a peek:
```r
telemarketing <- read.csv("..")

head(telemarketing)
tail(telemarketing)
```

2. Inspect the structure:

```r
str(telemarketing)
anyNA(telemarketing)
summary(telemarketing)
```

`summary` goes through each column in your data. 
    - If numeric: 5 number summary (min, max, median, 1st, 3rd quantil)
    - If factor: table (counts how many each category is represented)

3. Form a mental checklist
List the actionable items including any preprocessing steps, missing values treatment, outlier treatment