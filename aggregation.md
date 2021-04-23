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

Query the sum of the populations for all Japanese cities in CITY. The COUNTRYCODE for Japan is JPN.

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
WHERE COUNTRYCODE ='JPN';
```

# **[Population Density Difference](https://www.hackerrank.com/challenges/population-density-difference/problem)**

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

# **[The Blunder](https://www.hackerrank.com/challenges/the-blunder/problem)**

Samantha was tasked with calculating the average monthly salaries for all employees in the EMPLOYEES table, but did not realize her keyboard's  key was broken until after completing the calculation. She wants your help finding the difference between her miscalculation (using salaries with any zeros removed), and the actual average salary.

Write a query calculating the amount of error (i.e.:  average monthly salaries), and round it up to the next integer.

Input Format

The EMPLOYEES table is described as follows:

|  COLUMN | TYPE | 
|---|---|
| ID  | INTEGER |
| NAME | STRING |
| SALARY | INTEGER |

Note: Salary is per month.

Constraints

1000 < Salary < 10<sup>5

Sample Input

|  ID | NAME | SALARY |
|---|---|---|
| 1  | KRISTEEN | 1420 |
| 2 | ASHLEY | 2006 |
| 3 | JULIA | 2210 |
| 4 |  MARIA | 3000 |

Sample Output

2061

Explanation

The table below shows the salaries without zeros as they were entered by Samantha:

|  ID | NAME | SALARY |
|---|---|---|
| 1  | KRISTEEN | 142 |
| 2 | ASHLEY | 26 |
| 3 | JULIA | 221 |
| 4 |  MARIA | 3 |


Samantha computes an average salary of . The actual average salary is .

The resulting error between the two calculations is . Since it is equal to the integer , it does not get rounded up.

**Solution**
```sql
SELECT 
    ROUND(AVG(SALARY)) -
    ROUND(AVG(REPLACE(SALARY, '0','')))
FROM EMPLOYEES;
```
