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
