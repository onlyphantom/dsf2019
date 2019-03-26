1. Read our dataset in
  - `read.csv("~/Desktop/Datasets/bankloans.csv")`
    - This will transform any character to a factor by default
    - To disable this, set `stringsAsFactor=FALSE`

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
  
