---
layout: default
title: Date
parent: Data Types
grand_parent: Cypher
nav_order: 2
---

# DATE
`DATE` is specified in ISO 8601 format (`YYYY-MM-DD`). 


### `DATE` creation
```
RETURN date('2022-06-06') as x;
```
Output:
```
--------------
| x          |
--------------
| 2022-06-06 |
--------------
```