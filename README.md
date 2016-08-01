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
