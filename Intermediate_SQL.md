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
