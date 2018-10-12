---
title: "Python Referrence Summary"
date: 2018-10-12T17:13:08+08:00
draft: false
tag:
    - leetcode
    - alrorithm
    - Python
---

# Python Referrence Summary

## In-place modification

```Python
nums[:] = nums[::-1]    # Right. Reverse the list, in-place
nums = nums[::-1]       # Wrong, nums refer to a newly created list

nums[k:] = nums[-1:k-1:-1]  # Right. Reverse part of the list, in-place.
```

For example:
```Python
In [24]: c = [i for i in range(0, 5)]

In [25]: c
Out[25]: [0, 1, 2, 3, 4]

In [26]: id(c)
Out[26]: 4572965320

In [27]: c[:] = c[::-1]

In [28]: id(c)
Out[28]: 4572965320

In [29]: c
Out[29]: [4, 3, 2, 1, 0]

In [30]: c = c[::-1]

In [31]: id(c)
Out[31]: 4569862664

In [32]: c
Out[32]: [0, 1, 2, 3, 4]
```

## Multiple Dimensional List

```Python
A = [] * 3              
# Wrong. Equal to A * 3 ==> [A, A, A]
# A.append(3) -> [[3], [3], [3]]
# Elements refer to the same list.

A = [[] for i in range(0, 3)]
# Right. Create new list each time
```


