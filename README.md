# SQL Review - SIMPLE SELECT Answers

1. List all the Canadian cities and their populations
```
SELECT city, population FROM North_american_cities
WHERE country = 'Canada';
```

3. Order all the cities in the United States by their latitude from north to south
```
SELECT city, latitude FROM North_american_cities
WHERE country = 'United States'
ORDER BY latitude DESC;
```

5. List all the cities west of Chicago, ordered from west to east
```   
SELECT city, longitude FROM North_american_cities
WHERE longitude < -90
ORDER BY longitude ASC;
```
4. List the two largest cities in Mexico (by population)
```
SELECT city, population FROM North_american_cities
WHERE country = 'Mexico'
ORDER BY population DESC
LIMIT 2;
```

7. List the third and fourth largest cities (by population) in the United States and their population
```
SELECT city, population FROM North_american_cities
WHERE country = 'United States'
ORDER BY population DESC
LIMIT 2 OFFSET 2;
```

#SQL Lesson 12: Order of execution of a Query

1. Find the number of movies each director has directed
```
SELECT director, COUNT() FROM movies
GROUP BY director;
```

2. Find the total domestic and international sales that can be attributed to each director
```
SELECT Director,
SUM(boxoffice.domestic_sales) + SUM(boxoffice.international_sales) AS Total_Sales
FROM movies
JOIN boxoffice
ON movies.id = boxoffice.movie_id
GROUP BY Director;
```
