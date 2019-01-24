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

## Key Responsibilities of a Data Scientist
1. Data Visualization 
Acquire Data -> Preprocess -> Data Cleansing / Transformation -> Exploratory Data Analysis (EDA) -> Data Visualization -> Productionize

2. Machine Learning (AI)
Acquire Data -> Preprocess -> Data Cleansing / Transformation -> Exploratory Data Analysis (EDA) -> Model Development -> Test / Optimize

In EDA: often times it is helpful to perform Feature Engineering

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

4. Pre-processing things you do
- `as.character()`
- `as.integer()`
- `as.numeric()`
- `as.Date(x, format="%d-%m-%y")`
- `complete.cases()` drops any row where the values are not complete

5. EDA (Exploratory Data Analysis)
- `table(x)`
- `table(loan$purpose, loan$employed)`
- `xtabs( amount ~ purpose, data=internalrisk )`
- `xtabs( amount ~ purpose + duration, data=internalrisk )`
- Often times, you want to combine that with:
    - Subsetting
        - `data[ row, column ]` 
    - Feature Engineering

```r
data$risky <- ifelse(data$debttoincome > 0.3 & data$credithistory == "bad", "risky", "non-critical")
```

6. Data Visualization
- If x and y are numeric: scatterplot
- If x is a factor (categorical) and y is numeric: box plot
- If x and y are both factor: stacked column plot

```r
plot(x=loan$purpose, 
     y=loan$amount,
     main="Loan Amount breakdown by purpose",
     sub="Source: National Debt Collection Report, 2018",
     col="hotpink4",
     pch=19,
     cex=0.6
     xlab="Loan Purpose",
     ylab="Loan Amount"
)
```