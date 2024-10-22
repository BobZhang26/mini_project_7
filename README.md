[![CI](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml/badge.svg)](https://github.com/BobZhang26/Bob_PythonTemplate1/actions/workflows/cicd.yml)
## Miniproject 6: Python Script interacting with SQL Database

## Summary
This project is aimed to create an ETL-Query pipeline with an external cloud database. Databricks is used here. Then we used the dataset extracted from FiveThrityEight's public datasets to perform extracting, transforming and complex query.
<img width="977" alt="Screenshot 2023-10-02 at 11 25 47" src="https://github.com/nogibjj/mini_project_5/assets/141781876/94018e4a-0a3c-418a-8900-3bd898cff266">

## Structure

* in `mylib`directory, `extract.py` extract raw data from online url source. `transform_load.py` transform the original raw data format from `.csv` to `.db` SQLite database and builds connection.
* `query.py` contains CRUD queries to perform the basic SQL executions.

## Steps
1. In my.lib, create three files that perform several functions. Extract.py extract a dataset from a URL. Transform.py cleans and fliters the dataset. Query.py retrieves from the data.
2. Create a main.py script to run each step.
3. Use test_main.py to test each file and step.
4. Save the process in the log file.

## Complex query
The query retrieves data from two births table, joins on the same year, and groups by month, returns each month's total births and sort by month.
```md
SELECT t1.month, t1.SUM(births)
            FROM default.births2000DB t1 JOIN default.births1994DB t2
            ON t1.year=t2.year
            GROUP BY t1.month
            ORDER BY t1.month
            LIMIT 10

```
## Test
<img width="964" alt="Screenshot 2023-10-11 at 12 27 57" src="https://github.com/nogibjj/mini_project_5/assets/141781876/6f5214d9-9d37-44a1-9bc8-79f53a89da44">

