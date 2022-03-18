## Revising the Select Query I

#### Problem link - https://www.hackerrank.com/challenges/revising-the-select-query/problem

     SELECT * FROM city WHERE population > 100000 AND countrycode = 'USA';  

## Revising the Select Query II

#### Problem link - https://www.hackerrank.com/challenges/revising-the-select-query-2/problem

     SELECT name FROM city WHERE countrycode = 'USA' AND population > 120000;

## Select All

#### Problem link - https://www.hackerrank.com/challenges/select-all-sql/problem

     SELECT * FROM city;

## Select By ID

#### Problem link - https://www.hackerrank.com/challenges/select-by-id/problem

     SELECT * FROM city WHERE id = '1661';  

## Japanese Cities' Attributes

#### Problem link - https://www.hackerrank.com/challenges/japanese-cities-attributes/problem

     SELECT * FROM city WHERE countrycode = 'JPN';  

## Japanese Cities' Names

#### Problem link - https://www.hackerrank.com/challenges/japanese-cities-name/problem

     SELECT name FROM city WHERE countrycode = 'JPN';  

## Weather Observation Station 1

#### Problem link - https://www.hackerrank.com/challenges/weather-observation-station-1/problem

     SELECT city, state FROM station;  

## Weather Observation Station 3

#### Problem link - https://www.hackerrank.com/challenges/weather-observation-station-3/problem

     SELECT DISTINCT city FROM station WHERE MOD(id, 2) = 0;  

## Weather Observation Station 4

#### Problem link - https://www.hackerrank.com/challenges/weather-observation-station-4/problem

     SELECT COUNT(city) - COUNT(DISTINCT(city)) FROM station;   

## Weather Observation Station 5

#### Problem link - https://www.hackerrank.com/challenges/weather-observation-station-5/problem

     SELECT * FROM (SELECT DISTINCT city, LENGTH(city) FROM station ORDER BY LENGTH(city) ASC, city ASC) WHERE ROWNUM = 1   
     UNION  
     SELECT * FROM (SELECT DISTINCT city, LENGTH(city) FROM station ORDER BY LENGTH(city) DESC, city ASC) WHERE ROWNUM = 1;  

## Weather Observation Station 6

#### Problem link - https://www.hackerrank.com/challenges/weather-observation-station-6/problem

     SELECT DISTINCT city FROM station WHERE city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%';   

## Weather Observation Station 7

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-7/problem

     SELECT DISTINCT city FROM station WHERE city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u';  

## Weather Observation Station 8

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-8/problem

     SELECT DISTINCT city FROM 
     (SELECT DISTINCT city FROM station WHERE city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%') 
     WHERE city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u';

## Weather Observation Station 9

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-9/problem

     SELECT DISTINCT city FROM station 
     WHERE NOT (city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%');   

## Weather Observation Station 10

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-10/problem

     SELECT DISTINCT city FROM station
     WHERE NOT (city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u');  

## Weather Observation Station 11

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-11/problem

     SELECT DISTINCT city FROM station 
     WHERE (NOT (city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%') 
     OR NOT(city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u'));   

## Weather Observation Station 12

#### Problem link -  https://www.hackerrank.com/challenges/weather-observation-station-12/problem

     SELECT DISTINCT city FROM station 
     WHERE NOT ((city LIKE 'A%' OR city LIKE 'E%' OR city LIKE 'I%' OR city LIKE 'O%' OR city LIKE 'U%')  
     OR (city LIKE '%a' OR city LIKE '%e' OR city LIKE '%i' OR city LIKE '%o' OR city LIKE '%u'));

## Higher Than 75 Marks

#### Problem link - https://www.hackerrank.com/challenges/more-than-75-marks/problem

     SELECT name FROM students WHERE marks > 75 ORDER BY SUBSTR(name, LENGTH(name)-2, 3), id;

## Employee Names

#### Problem link - https://www.hackerrank.com/challenges/name-of-employees/problem

     SELECT name FROM employee ORDER BY name;

## Employee Salaries

#### Problem link - https://www.hackerrank.com/challenges/salary-of-employees/problem

     SELECT name FROM employee WHERE salary > 2000 AND months < 10 ORDER BY employee_id;
