# **[Revising the Select Query I](https://www.hackerrank.com/challenges/revising-the-select-query/problem)**

Query all columns for all American cities in the CITY table with populations larger than 100000. The CountryCode for America is USA.

The CITY table is described as follows:

|  Field | Type |
|-------|-----|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT * 
FROM CITY
WHERE CountryCode='USA' AND POPULATION > 100000;
```

# **[Revising the Select Query-II](https://www.hackerrank.com/challenges/revising-the-select-query-2/problem)**

Query the NAME field for all American cities in the CITY table with populations larger than 120000. The CountryCode for America is USA.

The CITY table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT NAME
FROM CITY
WHERE COUNTRYCODE= 'USA' AND POPULATION > 120000;
```

# **[Select All](https://www.hackerrank.com/challenges/select-all-sql/problem)**

Query all columns (attributes) for every row in the CITY table.

The CITY table is described as follows:

Input Format

The CITY table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT *
FROM CITY;;
```
