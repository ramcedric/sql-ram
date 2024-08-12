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

# SQL Lesson 12: Order of execution of a Query

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

# SQL PD USE CASES

1. A hacked site members' details have surfaced on a darknet forum. Please submit all members' details.
```
SELECT * FROM members;
```

2. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records' details.
```
SELECT * FROM mailing_list;
```

3. An illegal site's servers were seized in a recent operation. Please submit all users emails, number of posts and given names' details.
```
SELECT Email, Posts, GivenName
FROM users;
```

4. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit all records family names and given names' details.
```
SELECT FamilyName, GivenName
FROM mailing_list;
```

5. An illegal site's servers were seized in a recent operation. Please submit all users first names' details. Please make sure there are no duplicates.
```
SELECT DISTINCT FirstName
FROM Users;
```

6. A hacked site subscribers' details have surfaced on a darknet forum. Please submit all subscribers' details sorted by usernames in ascending order.
```
SELECT * FROM subscribers
ORDER BY Username ASC;
```

7. White hat hacker has sent SQLPD exposed subscribers' details of a shady site connected to various persons of interest. Please submit all subscribers' details sorted by subscribed since dates in descending order.
```
SELECT * FROM subscribers
ORDER BY SubscribedSince DESC;
```

8. White hat hacker has sent SQLPD exposed members' details of a shady site connected to various persons of interest. Please submit all members number of purchases, member since dates and hashed passwords' details sorted by member since dates in descending order. Please make sure there are no duplicates.
```
SELECT DISTINCT NumberofPurchases, MemberSince, HashedPassword
From members
ORDER BY Membersince DESC;
```

9. An illegal site's servers were seized in a recent operation. Please submit all users number of posts and access times' details sorted by access times in descending order and then by number of posts in descending order.
```
SELECT Posts, AccessTime
FROM users
ORDER BY AccessTime DESC, Posts DESC;
```

10. A mailing list of an illegal online service was sent to the SQLPD hot-line. Please submit the top 3 records' details when sorted by email addresses in ascending order and then by number of children in descending order.
```
SELECT * FROM mailing_list
ORDER BY EmailAddress ASC, Children DESC
LIMIT 3;
```
