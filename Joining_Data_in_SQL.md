# Joining Data in SQL
---
### Your first join
1. Begin by selecting all columns from the cities table, using the SQL shortcut that selects all.
```sql
-- Select all columns from cities
SELECT *
FROM cities
```
2. Perform an inner join with the cities table on the left and the countries table on the right; you do not need to alias tables here.
* Join ON the country_code and code columns, making sure you identify them with the correct table.
```sql
SELECT *
FROM sities
INNER JOIN countries
ON cities.country_code = countries.code
```
3. Complete the SELECT statement to keep three columns: the name of the city, the name of the country, and the region the country is located in (in this order).
* Alias the name of the city AS city and the name of the country AS country.
