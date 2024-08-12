# SQL Review - SIMPLE SELECT Answers

1. List all the Canadian cities and their populations

SELECT city, population FROM North_american_cities
WHERE country = 'Canada';

2. Order all the cities in the United States by their latitude from north to south

SELECT city, latitude FROM North_american_cities
WHERE country = 'United States'
ORDER BY latitude DESC;

3. List all the cities west of Chicago, ordered from west to east
   
SELECT city, longitude FROM North_american_cities
WHERE longitude < -90
ORDER BY longitude ASC;

4.List the two largest cities in Mexico (by population)

SELECT city, population FROM North_american_cities
WHERE country = 'Mexico'
ORDER BY population DESC
LIMIT 2;

5. List the third and fourth largest cities (by population) in the United States and their population

SELECT city, population FROM North_american_cities
WHERE country = 'United States'
ORDER BY population DESC
LIMIT 2 OFFSET 2;
