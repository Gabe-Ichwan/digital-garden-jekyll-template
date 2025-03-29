---
tags:
  - published
---
Row major and column major are ways of storing values in [[Matrix|Matrices]] and multidimensional arrays. The usage of which usually matters less than being consistent with accessing them. The differences are as follows:

Row major is ordered moving rightwards before down. 

```c
|1, 2, 3|
|4, 5, 6|
|7, 8, 9|
```

Column major is ordered moving down before right. 

```c
|1, 4, 7|
|2, 5, 8|
|3, 6, 9|
```

In row-major rows are stored contiguously in [[Main Memory (RAM)]] in column-major columns are stored contiguously in memory.