# **[Revising Aggregations - The Count Function](https://www.hackerrank.com/challenges/revising-aggregations-the-count-function/problem)**

Query a count of the number of cities in CITY having a Population larger than 100,000.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT COUNT(*)
FROM CITY
WHERE POPULATION > 100000;
```

# **[Revising Aggregations - The Sum Function](https://www.hackerrank.com/challenges/revising-aggregations-sum/problem)**

Query the total population of all cities in CITY where District is California.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT SUM(POPULATION)
FROM CITY 
WHERE DISTRICT = 'CALIFORNIA';
```

# **[Revising Aggregations - Averages](https://www.hackerrank.com/challenges/revising-aggregations-the-average-function/problem)**

Query the average population of all cities in CITY where District is California.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT AVG(POPULATION)
FROM CITY
WHERE DISTRICT= 'CALIFORNIA';
```


# **[Average Population](https://www.hackerrank.com/challenges/average-population/problem)**

Query the average population for all cities in CITY, rounded down to the nearest integer.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT ROUND(AVG(POPULATION))
FROM CITY;
```

# **[Japan Population](https://www.hackerrank.com/challenges/japan-population/problem)**

Query the average population for all cities in CITY, rounded down to the nearest integer.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
# **[Population Density Difference](https://www.hackerrank.com/challenges/population-density-difference/problem)**

Query the difference between the maximum and minimum populations in CITY.

Input Format

|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

**Solution**
```sql
SELECT MAX(POPULATION) - MIN(POPULATION)
FROM CITY;
```
