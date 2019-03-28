## Data Analysis and EDA

1. Read our dataset in
  - `read.csv("~/Desktop/Datasets/bankloans.csv")`
    - This will transform any character to a factor by default
    - To disable this, set `stringsAsFactor=FALSE`
    - By default, it assume file is separated by comma (`,`). 
        - To change / set this, use `sep="|"`

2. Take a peek at the data
  - `head()` and `tail()`
    - By default, prints the first or last 6 rows
    - To override this, use `head(x, 4)` to print 4 rows
    
3. Inspect the structure of our data
  - `str()`prints the structure
    - Includes number of observations (rows) and variables (columns)
    - Show first 5 values of every column
    
4. Get a summary of the data
  - `summary()` returns a table for Factor variables
      - and return 5-number summary for Numeric variables (Min, Max, Median, 1, 3)
  - `summary(estate$city, maxsum=8)` to get 7 largest levels + 1 "Others"
  
5. Simple visuals
  - `plot()`
  - `hist()`: use it with Numeric!
  - `pie()`: use it on a Table!
      
6. Tables (use it with Factors!)
  - `table(insurance$type)`
    - Two-dimensional tables: `table(x$type, x$construction)`
  - `prop.table`: use it on a Table!

7. Other misc functions:
  - `nrow` (number of rows), `ncol` (number of cols), `dim` (dimension), `colnames` (column names)
  
8. Subsetting
    - Basic construct: `data[ row, column ]`
    - `loans[loans$applicant == "unemployed", ]`
    - `loans[loans$applicant == "unemployed" & loans$amount > 100000, ]`
    - `customers[customers$origin == "Bangkok" | customers$origin == "Singapore", ]`
    ```r
    c1 <- shipment$destination == "Bangkok"
    c2 <- shipment$destination == "Phuket"

    shipment[c1 | c2, ]
    ```
    - Often, this is a useful technique to combine with `nrow()` or aggregation function like `mean()` and `sum()`

9. Cross Tabulation (`xtabs`)
    - Basic construct: `xtabs(formula=y~x, data)`
    - Eg. What is the total amount of convicts breakdown by crime type (how many are in jail because of murder, how many because of robbery, how many because of theft...)
    - `xtabs(convicts ~ crime_type + location, data=crime)`

10. Aggregate
    - Basic construct: `aggregate(formula=y ~ x1 + x2 + x3, data, FUN=mean)`

## Machine Learning
### Regression Models
1. Read our dataset in
  - `risk <- read.csv("insurance_risk.csv")`

2. Decide on the ML problem at hand
  - Regression or Classification
  - Which is your target variable?

3. Decide on the predictors
  - Predictors are the variables you use to make prediction
  - `cor()` is correlation
    - Correlation does not imply causation?
    - Also doesn't tell you about direction
  - You may need to use a lot of EDA techniques 

4. Create our linear model
  - `insurance_mod <- lm(risk~claims, insurance)`: linear model if a LINEAR relationship exist
  - `summary(insurance_mod)`
  - Could be useful to take a look at your residuals: `resid(insurance_mod)`
  - To get only the coefficients: `coef(insurance_mod)`

5. To predict using our model
  - `predict(insurance_mod, data)`

6. Final job:
  - Your job ends when you have proof that your model cannot be further improved upon
  - Good step is to always check your errors
    - `hist(resid(model))`
    - `plot(predict(model), resid(model))`
    - Residuals should be normally distributed 
    - Residuals should appear random



# Extra Materials
## Data Visualization
- https://github.com/onlyphantom/safeskies
- https://github.com/onlyphantom/rgraphics
- https://samuelc.shinyapps.io/Quadrant/
