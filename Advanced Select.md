## Type of Triangle

#### Problem link - https://www.hackerrank.com/challenges/what-type-of-triangle/problem

     SELECT CASE 
       WHEN (A + B <= C) OR (B + C <= A) OR(A + C <= B) THEN 'Not A Triangle'
       WHEN (A = B) AND (B = C) THEN 'Equilateral'
       WHEN (A =B) OR (C = A) OR (B = C) THEN 'Isosceles'
       ELSE 'Scalene' 
     END 
     FROM TRIANGLES;

## The PADS

#### Problem link - https://www.hackerrank.com/challenges/the-pads/problem

     SELECT (name || '(' || SUBSTR(occupation,1,1) || ')') FROM occupations ORDER BY name;
     SELECT ('There are a total of ' || COUNT(occupation) || ' ' || LOWER(occupation) || 's' || '.')  FROM occupations 
     GROUP BY occupation 
     ORDER BY COUNT(occupation), occupation ASC;

## Occupations

#### Problem link - https://www.hackerrank.com/challenges/occupations/problem

     SELECT MIN(Doctor), MIN(Professor), MIN(Singer), MIN(Actor)
     FROM
     (SELECT  RANK() OVER(PARTITION BY occupation ORDER BY name) rank,
       case OCCUPATION when 'Doctor' then NAME end AS Doctor,
       case OCCUPATION when 'Professor' then NAME end AS Professor,   
       case OCCUPATION when 'Singer' then NAME end AS Singer, 
       case OCCUPATION when 'Actor' then NAME end AS Actor
     FROM occupations)
     GROUP BY rank
     ORDER BY rank;

## Binary Tree Nodes

#### Problem link - https://www.hackerrank.com/challenges/binary-search-tree-1/problem

     SELECT N, CASE 
             WHEN P IS NULL                  THEN 'Root'
             WHEN N IN (SELECT P FROM BST)   THEN 'Inner'
             ELSE 'Leaf'
         END
     FROM BST
     ORDER BY N;
     
## New Companies

#### Problem link - https://www.hackerrank.com/challenges/the-company/problem

     SELECT c.company_code, c.founder, 
             COUNT(DISTINCT l.lead_manager_code),
             COUNT(DISTINCT s.senior_manager_code),
             COUNT(DISTINCT m.manager_code), 
             COUNT(DISTINCT e.employee_code)   
     FROM Company c, Lead_Manager l, Senior_Manager s, Manager m, Employee e
     WHERE c.company_code        = l.company_code            AND 
           l.lead_manager_code   = s.lead_manager_code       AND
           s.senior_manager_code = m.senior_manager_code     AND
           m.manager_code        = e.manager_code
     GROUP BY c.company_code, c.founder ORDER BY c.company_code ASC;
