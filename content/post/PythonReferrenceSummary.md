---
title: "Python Summary"
date: 2018-10-12T17:13:08+08:00
draft: false
tag: LeetCode,Alogithm,Python
---

# Python Summary

## String
### Equals

```Python
In [1]: s, t = 'Hello', 'Hello'

In [2]: s == t
Out[2]: True

In [3]: s is t
Out[3]: True

In [4]: v = "".join(["He", "llo"])

In [5]: s == v
Out[5]: True

In [6]: s is v
Out[6]: False

In [7]: id(s), id(t), id(v)
Out[7]: (4564168352, 4564168352, 4564117072)
```

`is` is **identity testing**, `==` is **equality** testing; which means `is` equals to `id(A) == id(B)`.

[StackOverflow - Why does comparing strings in Python using either '==' or 'is' sometimes produce different results](https://stackoverflow.com/questions/1504717/why-does-comparing-strings-in-python-using-either-or-is-sometimes-produce)

## Collection

### Map

#### Check the Map contains a key
using `in`
```Python
In [9]: d = {'1':1, '2':2}

In [10]: '3' in d
Out[10]: False
```

### Set

#### Create a new empty Set
```Python
s = set()
```

## Reference

### In-place modification

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

### Multiple Dimensional List

```Python
A = [] * 3              
# Wrong. Equal to A * 3 ==> [A, A, A]
# A.append(3) -> [[3], [3], [3]]
# Elements refer to the same list.

A = [[] for i in range(0, 3)]
# Right. Create new list each time
```


