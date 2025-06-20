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
```sql
-- Select name fields (with alias) and region 
SELECT cities.name AS city, 
countries.name AS country, 
countries.region
FROM cities
INNER JOIN countries
ON cities.country_code = countries.code;
```
### Joining with aliased tables
* Start with your inner join in line 5; join the tables countries AS c (left) with economies (right), aliasing economies AS e.
* Next, use code as your joining field in line 7; do not use the USING command here.
* Lastly, select the following columns in order in line 2: code from the countries table (aliased as country_code), name, year, and inflation_rate.
```sql
-- Select fields with aliases
SELECT c.code AS country_code, name, year, inflation_rate
FROM countries AS c
-- Join to economies (alias e)
INNER JOIN economies AS e
-- Match on code field using table aliases
ON c.code = e.code
```  
### USING in action
* Use the country code field to complete the INNER JOIN with USING; do not change any alias names.
```sql
SELECT c.name AS country, l.name AS language, official
FROM countries AS c
INNER JOIN languages AS l
-- Match using the code column
USING (code)
```
---
### Relationships in our database
1. Select the country name, aliased as country, from the countries table.
```sql

```
