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

# Extra Materials
## Data Visualization
- https://github.com/onlyphantom/safeskies
- https://github.com/onlyphantom/rgraphics
- https://samuelc.shinyapps.io/Quadrant/
