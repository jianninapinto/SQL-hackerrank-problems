# **[Type of Triangle](https://www.hackerrank.com/challenges/what-type-of-triangle/problem)**

Write a query identifying the type of each record in the TRIANGLES table using its three side lengths. Output one of the following statements for each record in the table:

Equilateral: It's a triangle with 3 sides of equal length.
Isosceles: It's a triangle with 2 sides of equal length.
Scalene: It's a triangle with 3 sides of differing lengths.
Not A Triangle: The given values of A, B, and C don't form a triangle.

Input Format

The TRIANGLES table is described as follows:

|  Column | Type |
|-------|-----|
| A  | INTEGER |
| B| INTEGER |
| C | INTEGER |

Each row in the table denotes the lengths of each of a triangle's three sides.

Sample Input

|  A | B | C |
|----|-----|----|
| 20  | 20 | 23 |
| 20| 20 | 20 |
| 20 | 21 | 22 |
| 13 | 14 | 30 |

Sample Output

Isosceles
Equilateral
Scalene
Not A Triangle
Explanation

Values in the tuple (20, 20, 23) form an Isosceles triangle, because A ≡ B.
Values in the tuple (20, 20, 20) form an Equilateral triangle, because A ≡ B ≡ C. Values in the tuple (20, 21, 22) form a Scalene triangle, because A ≠ B ≠ C .
Values in the tuple (13, 14, 30) cannot form a triangle because the combined value of sides A and B is not larger than that of side C.

```sql
SELECT 
    CASE
        WHEN A + B <= C OR A + C <= B OR B + C <= A THEN 'Not A Triangle'
        WHEN A = B AND B = C THEN 'Equilateral'
        WHEN A = B OR A = C OR B = C THEN 'Isosceles'
        WHEN A != B AND A != C AND B != C THEN 'Scalene'
    END
FROM TRIANGLES;
```

# **[The PADS](https://www.hackerrank.com/challenges/the-pads/problem)**

Generate the following two result sets:

Query an alphabetically ordered list of all names in OCCUPATIONS, immediately followed by the first letter of each profession as a parenthetical (i.e.: enclosed in parentheses). For example: AnActorName(A), ADoctorName(D), AProfessorName(P), and ASingerName(S).
Query the number of ocurrences of each occupation in OCCUPATIONS. Sort the occurrences in ascending order, and output them in the following format:

There are a total of [occupation_count] [occupation]s.

where [occupation_count] is the number of occurrences of an occupation in OCCUPATIONS and [occupation] is the lowercase occupation name. If more than one Occupation has the same [occupation_count], they should be ordered alphabetically.

Note: There will be at least two entries in the table for each type of occupation.

Input Format

The OCCUPATIONS table is described as follows:

|  Column | Type |
|-------|-----|
| Name | String |
| Occupation | String |

 Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

Sample Input

An OCCUPATIONS table that contains the following records:

|  Name | Occupation |
|-------|-----|
| Samantha | Doctor |
| Julia | Actor |
| Maria | Actor |
| Meera | Singer |
| Ashely | Professor |
| Ketty | Professor |
| Christeen | Professor |
| Jane | Actor |
| Jenny | Doctor |
| Priya | Singer |

Sample Output

Ashely(P)
Christeen(P)
Jane(A)
Jenny(D)
Julia(A)
Ketty(P)
Maria(A)
Meera(S)
Priya(S)
Samantha(D)
There are a total of 2 doctors.
There are a total of 2 singers.
There are a total of 3 actors.
There are a total of 3 professors.

Explanation

The results of the first query are formatted to the problem description's specifications.
The results of the second query are ascendingly ordered first by number of names corresponding to each profession (2 ≥ 2 ≥ 3 ≥ 3), and then alphabetically by profession (doctor ≥ singer, and actor ≥ professor).

```sql
SELECT CONCAT(NAME, '(', SUBSTR(OCCUPATION, 1, 1), ')')
FROM OCCUPATIONS
ORDER BY NAME ASC;

SELECT CONCAT('There are a total of ', COUNT(OCCUPATION), ' ', LOWER(OCCUPATION), 's.')
FROM OCCUPATIONS
GROUP BY OCCUPATION
ORDER BY COUNT(OCCUPATION) ASC;
```

# **[Occupations](https://www.hackerrank.com/challenges/occupations/problem)**

Pivot the Occupation column in OCCUPATIONS so that each Name is sorted alphabetically and displayed underneath its corresponding Occupation. The output column headers should be Doctor, Professor, Singer, and Actor, respectively.

Note: Print NULL when there are no more names corresponding to an occupation.

Input Format

The OCCUPATIONS table is described as follows:

|  Column | Type |
|-------|-----|
| Name | String |
| Occupation | String |

 Occupation will only contain one of the following values: Doctor, Professor, Singer or Actor.

Sample Input

An OCCUPATIONS table that contains the following records:

|  Name | Occupation |
|-------|-----|
| Samantha | Doctor |
| Julia | Actor |
| Maria | Actor |
| Meera | Singer |
| Ashely | Professor |
| Ketty | Professor |
| Christeen | Professor |
| Jane | Actor |
| Jenny | Doctor |
| Priya | Singer |

Sample Output

Jenny    Ashley     Meera  Jane
Samantha Christeen  Priya  Julia
NULL     Ketty      NULL   Maria
Explanation

The first column is an alphabetically ordered list of Doctor names.
The second column is an alphabetically ordered list of Professor names.
The third column is an alphabetically ordered list of Singer names.
The fourth column is an alphabetically ordered list of Actor names.
The empty cell data for columns with less than the maximum number of names per occupation (in this case, the Professor and Actor columns) are filled with NULL values.


```sql
SET @d=0, @p=0, @s=0, @a=0;
SELECT MIN(Doctor), MIN(Professor), MIN(Singer), MIN(Actor)
FROM(
  SELECT CASE WHEN Occupation='Doctor' THEN (@d:=@d+1)
    WHEN Occupation='Professor' THEN (@p:=@p+1)
    WHEN Occupation='Singer' THEN (@s:=@s+1)
    WHEN Occupation='Actor' THEN (@a:=@a+1) END AS RowNumber,
    CASE WHEN Occupation='Doctor' THEN Name END AS Doctor,
    CASE WHEN Occupation='Professor' THEN Name END AS Professor,
    CASE WHEN Occupation='Singer' THEN Name END AS Singer,
    CASE WHEN Occupation='Actor' THEN Name END AS Actor
  FROM OCCUPATIONS
  ORDER BY Name
) AS Temp
GROUP BY RowNumber;
```
