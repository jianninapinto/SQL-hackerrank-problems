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

# **[Weather Observation Station 2](https://www.hackerrank.com/challenges/weather-observation-station-2/problem)**

Query the following two values from the STATION table:

1. The sum of all values in LAT_N rounded to a scale of  decimal places.
2. The sum of all values in LONG_W rounded to a scale of  decimal places.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

Output Format

Your results must be in the form:

lat lon

where lat is the sum of all values in LAT_N and lon is the sum of all values in LONG_W. Both results must be rounded to a scale of 2 decimal places.

**Solution**
```sql
SELECT ROUND(SUM(LAT_N), 2), ROUND(SUM(LONG_W), 2)
FROM STATION;
```

# **[Weather Observation Station 13](https://www.hackerrank.com/challenges/weather-observation-station-13/problem)**

Query the sum of Northern Latitudes (LAT_N) from STATION having values greater than 38.7882 and less than 137.2345. Truncate your answer to 4 decimal places.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT TRUNCATE(SUM(LAT_N), 4)
FROM STATION
WHERE LAT_N BETWEEN 38.7880 AND 137.2345;
```

# **[Weather Observation Station 14](https://www.hackerrank.com/challenges/weather-observation-station-14/problem)**

Query the greatest value of the Northern Latitudes (LAT_N) from STATION that is less than . Truncate your answer to  decimal places.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT TRUNCATE(MAX(LAT_N), 4)
FROM STATION
WHERE LAT_N < 137.2345;
```

# **[Weather Observation Station 15](https://www.hackerrank.com/challenges/weather-observation-station-15/problem)**

Query the Western Longitude (LONG_W) for the largest Northern Latitude (LAT_N) in STATION that is less than 137.2345. Round your answer to 4 decimal places.

Input Format

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT ROUND(LONG_W, 4) 
FROM STATION 
WHERE LAT_N < 137.2345
ORDER BY LAT_N DESC 
LIMIT 1;
```

# **[Weather Observation Station 16](https://www.hackerrank.com/challenges/weather-observation-station-15/problem)**

Query the smallest Northern Latitude (LAT_N) from STATION that is greater than 38.7780. Round your answer to 4 decimal places.

Input Format

The STATION table is described as follows:

**Solution**
```sql
SELECT ROUND(MIN(LAT_N), 4)
FROM STATION
WHERE LAT_N > 38.7780;
```

# **[Weather Observation Station 17](https://www.hackerrank.com/challenges/weather-observation-station-17/problem)**

Query the Western Longitude (LONG_W)where the smallest Northern Latitude (LAT_N) in STATION is greater than 38.7780. Round your answer to 4 decimal places.

Input Format

The STATION table is described as follows:

**Solution**
```sql
SELECT ROUND(LONG_W, 4)
FROM STATION
WHERE LAT_N > 38.7780
ORDER BY LAT_N
LIMIT 1;
```

# **[Population Census](https://www.hackerrank.com/challenges/asian-population/problem)**

Given the CITY and COUNTRY tables, query the sum of the populations of all cities where the CONTINENT is 'Asia'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

CITY
|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

COUNTRY
|  Field | Type |
|---|---|
| CODE  | VARCHAR2(3) |
| NAME | VARCHAR2(44)   |
| CONTINENT | VARCHAR2(13)  |
| REGION |  VARCHAR2(25) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT SUM(CITY.POPULATION)
FROM CITY
JOIN COUNTRY
ON CITY.COUNTRYCODE = COUNTRY.CODE
WHERE CONTINENT = 'ASIA';
```

# **[African Cities](https://www.hackerrank.com/challenges/african-cities/problem)**

Given the CITY and COUNTRY tables, query the names of all cities where the CONTINENT is 'Africa'.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

The CITY and COUNTRY tables are described as follows

CITY
|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

COUNTRY
|  Field | Type |
|---|---|
| CODE  | VARCHAR2(3) |
| NAME | VARCHAR2(44)   |
| CONTINENT | VARCHAR2(13)  |
| REGION |  VARCHAR2(25) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT CITY.NAME
FROM CITY
JOIN COUNTRY 
ON CITY.COUNTRYCODE = COUNTRY.CODE
WHERE CONTINENT = 'AFRICA';
```

# **[Average Population of Each Continent](https://www.hackerrank.com/challenges/average-population-of-each-continent/problem)**

Given the CITY and COUNTRY tables, query the names of all the continents (COUNTRY.Continent) and their respective average city populations (CITY.Population) rounded down to the nearest integer.

Note: CITY.CountryCode and COUNTRY.Code are matching key columns.

Input Format

The CITY and COUNTRY tables are described as follows

CITY
|  Field | Type |
|---|---|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRYCODE | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |

COUNTRY
|  Field | Type |
|---|---|
| CODE  | VARCHAR2(3) |
| NAME | VARCHAR2(44)   |
| CONTINENT | VARCHAR2(13)  |
| REGION |  VARCHAR2(25) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION))
FROM COUNTRY
JOIN CITY ON COUNTRY.CODE = CITY.COUNTRYCODE
GROUP BY COUNTRY.CONTINENT;
```
    
    
# **[Weather Observation Station 18](https://www.hackerrank.com/challenges/weather-observation-station-18/problem)**

Consider P1(a,b) and P2(c,d) to be two points on a 2D plane.

a happens to equal the minimum value in Northern Latitude (LAT_N in STATION).
b happens to equal the minimum value in Western Longitude (LONG_W in STATION).
c happens to equal the maximum value in Northern Latitude (LAT_N in STATION).
d happens to equal the maximum value in Western Longitude (LONG_W in STATION).
Query the Manhattan Distance between points P1 and P2 and round it to a scale of 4 decimal places.

Input Format
The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.


**Solution**
```sql
-- The Manhattan Distance is |x1 - x2| + |y1 - y2| = |a - c| + |b - d| --
    
SELECT ROUND(ABS(MIN(LAT_N)-MAX(LAT_N)) + ABS(MIN(LONG_W)-MAX(LONG_W)), 4)
FROM STATION;
```

    
    
# **[Weather Observation Station 19](https://www.hackerrank.com/challenges/weather-observation-station-19/problem)**
    
Consider P1(a,c) and P2(b,d) to be two points on a 2D plane where (a,b) are the respective minimum and maximum values of Northern Latitude (LAT_N) and (c,d) are the respective minimum and maximum values of Western Longitude (LONG_W) in STATION.

Query the Euclidean Distance between points P1 and P2 and format your answer to display 4 decimal digits.

Input Format
The STATION table is described as follows:

STATION
    
|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |
    
where LAT_N is the northern latitude and LONG_W is the western longitude.

    
**Solution**
```sql
-- The Euclidean Distance is sqrt((a-b)2 + (c-d)2) --
    
SELECT ROUND(SQRT(POW(MIN(LAT_N)-MAX(LAT_N), 2)+ POW(MIN(LONG_W)-MAX(LONG_W), 2)), 4)
FROM STATION;
```
