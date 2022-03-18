## Population Census

#### Problem link - https://www.hackerrank.com/challenges/asian-population/problem

     SELECT SUM(X.POPULATION) FROM CITY X, COUNTRY Y 
     WHERE X.COUNTRYCODE = Y.CODE AND Y.CONTINENT = 'Asia';
     
## African Cities

#### Problem link - https://www.hackerrank.com/challenges/african-cities/problem

     SELECT CITY.NAME FROM CITY, COUNTRY 
     WHERE CITY.COUNTRYCODE = COUNTRY.CODE AND COUNTRY.CONTINENT = 'Africa';

## Average Population of Each Continent

#### Problem link - https://www.hackerrank.com/challenges/average-population-of-each-continent/problem

     SELECT COUNTRY.CONTINENT, FLOOR(AVG(CITY.POPULATION)) FROM CITY 
     JOIN COUNTRY 
     ON CITY.COUNTRYCODE = COUNTRY.CODE
     GROUP BY COUNTRY.CONTINENT;

## The Report

#### Problem link - https://www.hackerrank.com/challenges/the-report/problem

     SELECT CASE 
             WHEN G.Grade > 7 THEN S.Name 
             ELSE 'NULL' 
             END 
             AS NameOrNull, G.Grade, S.Marks
     FROM Students S
     JOIN Grades G 
     ON S.Marks BETWEEN G.Min_Mark AND G.Max_Mark
     ORDER BY G.Grade DESC, NameOrNull ASC, S.Marks ASC;

## Top Competitors

#### Problem link - https://www.hackerrank.com/challenges/full-score/problem

     SELECT Submissions.hacker_id, Hackers.name from Hackers, Submissions, Challenges, Difficulty
     WHERE Submissions.score = Difficulty.score
     AND Hackers.hacker_id = Submissions.hacker_id 
     AND Submissions.challenge_id = Challenges.challenge_id 
     AND Challenges.difficulty_level = Difficulty.difficulty_level
     GROUP BY Submissions.hacker_id, Hackers.name
     HAVING count(*) > 1 
     ORDER BY count(*) DESC, Submissions.hacker_id ASC;

## Ollivander's Inventory

#### Problem link - https://www.hackerrank.com/challenges/harry-potter-and-wands/problem

     SELECT id, age, coins_needed, power FROM Wands 
     JOIN Wands_Property 
     ON Wands.code = Wands_Property.code
     WHERE (age, coins_needed, power) 
     IN (
	     SELECT age, MIN(coins_needed), power FROM Wands 
       JOIN Wands_Property 
       ON Wands.code = Wands_Property.code
	     WHERE Wands_Property.is_evil = 0
	     GROUP BY age, power)
     ORDER BY power DESC, age DESC;

## Challenges

#### Problem link - https://www.hackerrank.com/challenges/challenges/problem

     WITH a AS(
	      SELECT h.hacker_id, name, count(c.challenge_id) AS nums 
	      FROM hackers h 
        join challenges c 
        ON	h.hacker_id = c.hacker_id 
	      GROUP BY h.hacker_id,h.name) 
     SELECT hacker_id, name, nums 
     FROM a 
     WHERE nums NOT IN 
     (
      SELECT nums FROM a WHERE nums < 
      (SELECT max(nums) FROM a) 
	    GROUP BY nums 
	    HAVING count(nums) > 1 
     ) 
     ORDER BY nums desc, hacker_id;
