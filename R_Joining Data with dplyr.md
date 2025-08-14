# Joining Data with dplyr
---
### Joining parts and part categories
1. Add the correct joining verb, the name of the second table, and the joining column for the second table.
```r
# Add the correct verb, table, and joining column
parts %>% 
  inner_join(part_categories, by = c("part_cat_id" = "id"))
```
2. Now, use the suffix argument to add "_part" and "_category" suffixes to replace the name.x and name.y fields.
```r
# Use the suffix argument to replace .x and .y suffixes
parts %>% 
  inner_join(part_categories, by = c("part_cat_id" = "id"), suffix = c("_part", "_category"))
```
---
### Joining parts and inventories
* Connect the parts and inventory_parts tables by their part numbers using an inner join.
```r
# Combine the parts and inventory_parts tables
parts %>%
  inner_join(inventory_parts, by= "part_num")
```
### Joining in either direction
* Connect the inventory_parts and parts tables by their part numbers using an inner join.
```r
# Combine the parts and inventory_parts tables
inventory_parts %>%
  inner_join(parts, by = "part_num")
```
---
### Joining three tables
* Combine the inventories table with the sets table.
* Next, join the inventory_parts table to the table you created in the previous join by the inventory IDs.
```r
sets %>%
  # Add inventories using an inner join 
  inner_join(inventories, by = "set_num") %>%
  # Add inventory_parts using an inner join 
  inner_join(inventory_parts, by = c("id" = "inventory_id"))
```
### What's the most common color?
1. Inner join the colors table using the color_id column from the previous join and the id column from colors; use the suffixes "_set" and "_color".
```r
# Add an inner join for the colors table
sets %>%
  inner_join(inventories, by = "set_num") %>%
  inner_join(inventory_parts, by = c("id" = "inventory_id")) %>%
  inner_join(colors, by = c("color_id" = "id"), suffix = c("_set", "_color"))
```
2. Count the name_color column and sort the results so the most prominent colors appear first.
```r
# Count the number of colors and sort
sets %>%
  inner_join(inventories, by = "set_num") %>%
  inner_join(inventory_parts, by = c("id" = "inventory_id")) %>%
  inner_join(colors, by = c("color_id" = "id"), suffix = c("_set", "_color")) %>%
  count(name_color, sort = TRUE)
```
