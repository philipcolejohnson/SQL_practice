# SQL_practice

## [SQL Zoo](http://sqlzoo.net/) exercises and quizzes

### SELECT Basics
1.
```sql
SELECT population FROM world
  WHERE name = 'Germany'
```
2.
```sql
SELECT name, population FROM world
  WHERE name IN ('Ireland', 'Iceland', 'Denmark')
```
3.
```sql
SELECT name, area FROM world
  WHERE area BETWEEN 200000 AND 250000
```

### SELECT from WORLD
1.
```sql
SELECT name, continent, population FROM world
```
2.
```sql
SELECT name FROM world
WHERE population>200000000
```
3.
```sql
SELECT name,
  gdp / population as per_capita_gdp
FROM world
WHERE population>200000000
```
4.
```sql
SELECT name,
  population / 1000000 as population_in_millions 
FROM world
WHERE continent = 'South America'
```
5.
```sql
SELECT name, population 
FROM world
WHERE name in ('France', 'Germany', 'Italy')
```
6.
```sql
SELECT name
FROM world
WHERE name LIKE '%United%'
```
7.
```sql
SELECT name, population, area
FROM world
WHERE area > 3000000 OR population > 250000000
```
8.
```sql
SELECT name, population, area
FROM world
WHERE area > 3000000 XOR population > 250000000
```
9.
```sql
SELECT
  name,
  ROUND(population / 1000000, 2) as population_in_millions,
  ROUND(gdp / 1000000000, 2) as gdp_in_billions
FROM world
WHERE continent = 'South America'
```
10.
```sql
SELECT name,
ROUND(gdp / population, -3)
FROM world
WHERE gdp > 1000000000000
```
11.
```sql
SELECT name,
       CASE WHEN continent='Oceania' THEN 'Australasia'
            ELSE continent END
  FROM world
 WHERE name LIKE 'N%'
```
12.
```sql
SELECT name, CASE
WHEN continent = 'Europe' OR continent = 'Asia' THEN 'Eurasia'
WHEN continent = 'North America' OR continent = 'South America' OR continent = 'Caribbean' THEN 'America'
ELSE continent
END
FROM world
WHERE name LIKE 'A%' OR name LIKE 'B%'
```
13.
```sql
SELECT name, continent, CASE
WHEN continent = 'Oceania' THEN 'Australasia'
WHEN continent = 'Eurasia' OR name = 'Turkey' THEN 'Europe/Asia'
WHEN continent = 'Caribbean' AND name LIKE 'B%' THEN 'North America'
WHEN continent = 'Caribbean' THEN 'South America'
ELSE continent
END
FROM world
ORDER BY name
```

### SELECT from NOBEL
1.
```sql
SELECT yr, subject, winner
  FROM nobel
 WHERE yr = 1950
```
2.
```sql
SELECT winner
  FROM nobel
 WHERE yr = 1962
   AND subject = 'Literature'
```
3.
```sql
SELECT yr, subject
  FROM nobel
 WHERE winner = 'Albert Einstein'
```
4.
```sql
SELECT winner
  FROM nobel
 WHERE subject = 'Peace' AND yr > 1999
```
5.
```sql
SELECT *
  FROM nobel
 WHERE subject = 'Literature' AND yr BETWEEN 1980 AND 1989
```
6.
```sql
SELECT *
FROM nobel
WHERE winner IN ('Theodore Roosevelt',
                  'Woodrow Wilson',
                  'Jimmy Carter')
```
7.
```sql
SELECT winner
FROM nobel
WHERE winner LIKE 'John%'
```
8.
```sql
SELECT *
FROM nobel
WHERE (subject = 'Physics' AND yr = 1980) OR
  (subject = 'Chemistry' AND yr = 1984)
```
9.
```sql
SELECT *
FROM nobel
WHERE yr = 1980 AND subject <> 'Chemistry'AND subject <> 'Medicine'
```
10.
```sql
SELECT *
FROM nobel
WHERE (yr < 1910 AND subject = 'Medicine')
  OR (yr > 2003 AND subject = 'Literature')
```
11.
```sql
SELECT *
FROM nobel
WHERE winner = 'Peter Grünberg'
```
12.
```sql
SELECT *
FROM nobel
WHERE winner = 'Eugene O''Neill'
```
13.
```sql
SELECT winner, yr, subject
FROM nobel
WHERE winner LIKE 'Sir%'
ORDER BY yr DESC, winner
```
14.
```sql
SELECT winner, subject
  FROM nobel
 WHERE yr=1984
 ORDER BY  subject IN ('Physics','Chemistry'), subject, winner
```

### JOIN
1.
```sql
SELECT matchid, player FROM goal 
  WHERE teamid='GER'
```
2.
```sql
SELECT id,stadium,team1,team2
  FROM game
  WHERE id = 1012
```
3.
```sql
SELECT player, teamid, stadium, mdate
  FROM game JOIN goal ON (id=matchid)
  WHERE teamid = 'GER'
```
4.
```sql
SELECT team1, team2, player
  FROM game JOIN goal ON (id=matchid)
  WHERE player LIKE 'Mario%'
```
5.
```sql
SELECT player, teamid, coach, gtime
  FROM goal JOIN eteam on teamid=id
 WHERE gtime<=10
```
6.
```sql
SELECT mdate, teamname
FROM game JOIN eteam ON team1=eteam.id
WHERE coach='Fernando Santos'
```
7.
```sql
SELECT player
FROM game JOIN goal ON id = matchid
WHERE stadium = 'National Stadium, Warsaw'
```
8.
```sql
SELECT DISTINCT player
  FROM game JOIN goal ON matchid = id 
    WHERE (team1='GER' OR team2='GER') AND teamid <> 'GER'
```
9.
```sql

```
10.
```sql

```
11.
```sql

```
12.
```sql

```
13.
```sql

```
