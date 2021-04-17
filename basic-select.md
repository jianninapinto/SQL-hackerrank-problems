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

# **[Revising the Select Query II](https://www.hackerrank.com/challenges/revising-the-select-query-2/problem)**

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
FROM CITY;
```

# **[Select By ID](https://www.hackerrank.com/challenges/select-by-id/problem)**

Query all columns for a city in CITY with the ID 1661.

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
FROM CITY 
WHERE ID=1661; 
```

# **[Japanese Cities' Attributes](https://www.hackerrank.com/challenges/japanese-cities-attributes/problem)**

Query all attributes of every Japanese city in the CITY table. The COUNTRYCODE for Japan is JPN.

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
FROM CITY
WHERE COUNTRYCODE='JPN'        
```

# **[Japanese Cities' Names](https://www.hackerrank.com/challenges/japanese-cities-name/problem)**

Query the names of all the Japanese cities in the CITY table. The COUNTRYCODE for Japan is JPN.
The CITY table is described as follows:

|  Field | Type |
|---|-------|
| ID  | NUMBER |
| NAME | VARCHAR2(17)   |
| COUNTRY CODE  | VARCHAR2(3)  |
| DISTRICT |  VARCHAR2(20) |
| POPULATION | NUMBER |


**Solution**
```sql
SELECT NAME
FROM CITY 
WHERE COUNTRYCODE='JPN';        
```

# **[Weather Observation Station 1](https://www.hackerrank.com/challenges/weather-observation-station-1/problem)**

Query a list of CITY and STATE from the STATION table.

The STATION table is described as follows:

|  Field | Type |
|---|---|
| ID  | NUMBER |
| CITY | VARCHAR2(21)   |
| STATE  | VARCHAR2(2)  |
| LAT_N |  NUMBER |
| LONG_W | NUMBER |

where LAT_N is the northern latitude and LONG_W is the western longitude.

**Solution**
```sql
SELECT CITY, STATE
FROM STATION;       
```
