# Intermediate SQL
---
### Learning to COUNT()
1. Count the total number of records in the people table, aliasing the result as count_records.
```sql
-- Count the number of records in the people table
select count(*) as count_records
from people
```
2. Count the number of records with a birthdate in the people table, aliasing the result as count_birthdate.
```sql
-- Count the number of birthdates in the people table
SELECT COUNT(birthdate) as count_birthdate
FROM people
```
3. Count the records for languages and countries in the films table; alias as count_languages and count_countries.
```sql
-- Count the records for languages and countries represented in the films table
SELECT COUNT(language) as count_languages,
COUNT(country) as count_countries
FROM films
```
### SELECT DISTINCT
1. Return the unique countries represented in the films table using DISTINCT.
```sql
-- Return the unique countries from the films table
SELECT DISTINCT country
FROM films;
```
2. Return the number of unique countries represented in the films table, aliased as count_distinct_countries.
```sql
-- Count the distinct countries from the films table
SELECT COUNT(DISTINCT country) as count_distinct_countries
FROM films
```
---
### Debugging errors
1. Debug and fix the SQL query provided.
```sql
-- Debug this code
SELECT certification
FROM films
LIMIT 5;
```
2. Find the two errors in this code; the same error has been repeated twice.
```sql
-- Debug this code
SELECT film_id, imdb_score, num_votes
FROM reviews;
```
3. Find the two bugs in this final query.
```sql
-- Debug this code
SELECT COUNNT(birthdate) AS count_birthdays
FROM people;
```
### Formatting
* Adjust the sample code so that it is in line with standard practices.
```sql
-- Rewrite this query
SELECT person_id, role
FROM roles 
LIMIT 10;
```
