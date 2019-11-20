## Workflow

1. Acquire our data
- Goal: Read the data into our R environment
- `read.csv()`
    - Can be a relative path: `read.csv("data_input/sales_2019_q4.csv")`
    - Can be an absolute path: `read.csv("C:\\Program... \sales.csv")`
    - Can be somewhere online (http, needs internet connection): `read.csv("https://.../data/.csv")`
- Common additional parameters
    - `header=TRUE`
    - `sep=","`
    - `stringsAsFactor=TRUE`
    - `skip=7`
- Important to note:
    R works with all kind of files
        - JPEG, CSV, XML, JSON, API, SQL Connection, XLSX, XLS, SPSS, SAS...

2. Peek at the data
    - `head()` shows you the first n rows of data, default of n is 6
    - `tail()` shows you last n rows of data
        - Example: `head(oilexport, 3)`
    - `str()`: structure of the data
        - Shows you the row (observations), columns (variables) of data
        - Shows you first few values of each columns

3. Dive into the data (get a sense)
    - One dimensional: `table(oilexport$OPEC)`
        - Two dimensional: `table("OPEC"=oilexport$OPEC, oilexport$Continent)`
        - Proportion Table: `prop.table(table1)`
    - `summary(oilexport)`

4. Formulate a plan for data processing (Data Cleansing)
    - Explicit coercion
        - `as.character`, `as.numeric`, `as.Date(x,format="")`
    - Any column is redundant
    - Any column that has no value 
    - Typically, we use columns that are:
        - Numeric
        - Categorical (Factor)
        - Datetime
    - May need to do Feature Engineering
        - Creating new features (variables) out of existing ones
        - Example: `weekday()`, `months()`

5. Exploratory Data Analysis
    - Combine what you learn in (1), (2) and (3) with one more core technique: subsetting
    - Subsetting: `loans[ row, col ]`
        - Example: `loans[ loans$Purpose == "Debt Consolidation",  c("Amount", "Duration", "Risk Level")]`
        - Example: `loans[ loans$Duration > 48, ]`
        - Example: `loans$Duration`
        - Example: `loans[  cond1 & cond2, ]`