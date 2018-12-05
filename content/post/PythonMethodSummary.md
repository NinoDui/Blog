---
title: "Python Built-in Method Summary"
date: 2018-12-05T20:51:47+08:00
draft: false
tag: Python
---

# Python Built-in Method Summary

## Sort

### Sorted

`sorted(iterable[, cmp[, key[, reverse]]])`
- applied to **iterable** objects, e.g. `List`
- `cmp` comparing method
    - `x > y` 1
    - `x < y` -1
    - `x == y` 0
- `key` elements to compare
- `reverse`
    - `False` ascending (default)
    - `True` dropping

### sorted v.s sort

|            | sort |        sorted        |
|:----------:|:----:|:--------------------:|
| applied to | `List` | all **iterable** objects |
|   return   | `None` |      a new list      |
|  in-place  | `True` |         `False`        |

```Python
In [13]: a
Out[13]: [3, 2, 3, 7, 9, 3, 1]

In [14]: b = sorted(a)

In [15]: b
Out[15]: [1, 2, 3, 3, 3, 7, 9]

In [16]: a
Out[16]: [3, 2, 3, 7, 9, 3, 1]

In [18]: c = a.sort()

In [20]: c

In [21]: a
Out[21]: [1, 2, 3, 3, 3, 7, 9]
```

