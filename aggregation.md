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

# **[Top Earners](https://www.hackerrank.com/challenges/earnings-of-employees/problem)**

We define an employee's total earnings to be their monthly salary x months worked, and the maximum total earnings to be the maximum total earnings for any employee in the Employee table. Write a query to find the maximum total earnings for all employees as well as the total number of employees who have maximum total earnings. Then print these values as  space-separated integers.

Input Format

The Employee table containing employee data for a company is described as follows:

|  Column | Type |
|---|---|
| employee_id  | integer |
| name | string |
| months | integer |
| salary | integer |

where employee_id is an employee's ID number, name is their name, months is the total number of months they've been working for the company, and salary is the their monthly salary.

Sample Input

|  employee_id | name | months | salary |
|---|---|---|---|
| 12228 | Rose | 15 | 1968 |
| 33645 | Angela | 1 | 3443 |
| 45692 | Frank | 17 | 1608 |
| 56118 | Patrick | 7 | 1345 |
| 59725 | Lisa | 11 | 2330 |
| 74197 | Kimberly | 16 | 4372 |
| 78454 | Bonnie | 8 | 1771 |
| 83565 | Michael | 6 | 2017 |
| 98607 | Todd | 5 | 3396 |
| 99989 | Joe | 9 | 3573 |

Sample Output

69952 1

Explanation

The table and earnings data is depicted in the following diagram:

|  employee_id | name | months | salary | earnings |
|---|---|---|---|---|
| 12228 | Rose | 15 | 1968 | 29520 |
| 33645 | Angela | 1 | 3443 | 3443 |
| 45692 | Frank | 17 | 1608 | 27336 |
| 56118 | Patrick | 7 | 1345 | 9415 |
| 59725 | Lisa | 11 | 2330 | 25630 |
| 74197 | Kimberly | 16 | 4372 | 69952 |
| 78454 | Bonnie | 8 | 1771 | 14168 |
| 83565 | Michael | 6 | 2017 | 12102| 
| 98607 | Todd | 5 | 3396 | 16980 |
| 99989 | Joe | 9 | 3573 | 32157 |

The maximum earnings value is 69952. The only employee with earnings = 69952 is Kimberly, so we print the maximum earnings value (69952) and a count of the number of employees who have earned $69952 (which is 1) as two space-separated values.

**Solution**
```sql
SELECT (MONTHS * SALARY) AS EARNINGS, COUNT(*) 
FROM EMPLOYEE
WHERE (MONTHS * SALARY) = (SELECT MAX(MONTHS * SALARY) FROM EMPLOYEE)
GROUP BY EARNINGS;
```
